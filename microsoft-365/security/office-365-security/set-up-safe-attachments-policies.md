---
title: 在 Microsoft Defender 保险箱设置附件策略Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 了解如何定义附件保险箱保护你的组织免受电子邮件中的恶意文件的攻击。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7220140c25ecf457b42514356e41aabdf5481bb
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054335"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fda1e-103">在 Microsoft Defender 保险箱设置附件策略Office 365</span><span class="sxs-lookup"><span data-stu-id="fda1e-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fda1e-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="fda1e-104">**Applies to**</span></span>
- [<span data-ttu-id="fda1e-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="fda1e-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="fda1e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fda1e-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="fda1e-107">本文适用于拥有 [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="fda1e-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="fda1e-108">如果你是一位家庭用户，正在查找有关电子邮件中的附件扫描Outlook，请参阅[Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="fda1e-109">保险箱附件是 Microsoft [Defender for Office 365](whats-new-in-defender-for-office-365.md)中的一项功能，该功能使用虚拟环境在[Exchange Online Protection (EOP) ](anti-malware-protection.md)中经过反恶意软件保护扫描之后，在发送给收件人之前，使用虚拟环境检查入站电子邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="fda1e-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="fda1e-110">有关详细信息，请参阅 microsoft Defender 保险箱[中的附件Office 365。](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="fda1e-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="fda1e-111">附件策略没有内置或默认保险箱。</span><span class="sxs-lookup"><span data-stu-id="fda1e-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="fda1e-112">若要保险箱电子邮件附件的附件扫描，您需要创建一个或多个保险箱附件策略，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="fda1e-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="fda1e-113">可以在 保险箱 Microsoft 365 Defender 门户中或在 PowerShell (Exchange Online PowerShell 中为在 Microsoft 365 中拥有邮箱的合格 Exchange Online 组织配置附件Exchange Online;独立 EOP PowerShell，适用于Exchange Online邮箱，但使用 Defender for Office 365 加载项订阅的组织) 。</span><span class="sxs-lookup"><span data-stu-id="fda1e-113">You can configure Safe Attachments policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="fda1e-114">"附件"策略保险箱元素包括：</span><span class="sxs-lookup"><span data-stu-id="fda1e-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="fda1e-115">安全附件策略：指定未知恶意软件检测的操作、是否将带恶意软件附件的邮件发送到指定的电子邮件地址，以及是否传递保险箱附件扫描无法完成时传递邮件。</span><span class="sxs-lookup"><span data-stu-id="fda1e-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="fda1e-116">**安全附件规则**：指定策略应用于 (的优先级和收件人) 。</span><span class="sxs-lookup"><span data-stu-id="fda1e-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="fda1e-117">当你在邮件门户中管理"附件"保险箱时，这两个元素Microsoft 365 Defender不明显：</span><span class="sxs-lookup"><span data-stu-id="fda1e-117">The difference between these two elements isn't obvious when you manage Safe Attachments policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="fda1e-118">创建附件保险箱策略时，实际上是同时使用同一名称创建安全附件规则和相关的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fda1e-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="fda1e-119">修改附件保险箱时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fda1e-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="fda1e-120">所有其他设置修改关联的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fda1e-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="fda1e-121">删除附件保险箱时，安全附件规则和相关的安全附件策略将被删除。</span><span class="sxs-lookup"><span data-stu-id="fda1e-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="fda1e-122">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="fda1e-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="fda1e-123">有关详细信息，请参阅本文稍后的使用 Exchange Online PowerShell 或独立[EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies)配置 保险箱 附件策略一节。</span><span class="sxs-lookup"><span data-stu-id="fda1e-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="fda1e-124">在"附件"设置的全局保险箱区域中，配置不依赖于"附件"保险箱的功能。</span><span class="sxs-lookup"><span data-stu-id="fda1e-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="fda1e-125">有关[说明，请参阅](turn-on-mdo-for-spo-odb-and-teams.md)在保险箱中打开SharePoint、OneDrive Microsoft Teams和保险箱[文档Microsoft 365 E5。](safe-docs.md)</span><span class="sxs-lookup"><span data-stu-id="fda1e-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fda1e-126">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="fda1e-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fda1e-127">访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。</span><span class="sxs-lookup"><span data-stu-id="fda1e-127">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="fda1e-128">若要直接转到"附件 **保险箱，** 请使用 <https://security.microsoft.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="fda1e-128">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="fda1e-129">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="fda1e-130">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fda1e-131">您需具有权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="fda1e-131">You need permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="fda1e-132">若要创建、修改和删除 保险箱 附件策略，您需要是 Microsoft 365 Defender 门户中组织管理或安全管理员角色组的成员以及 Exchange Online 中的组织管理角色组的成员。 </span><span class="sxs-lookup"><span data-stu-id="fda1e-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="fda1e-133">若要对附件策略保险箱只读访问权限，你需要是该门户中全局读取者或安全读者角色Microsoft 365 Defender的成员。 </span><span class="sxs-lookup"><span data-stu-id="fda1e-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Microsoft 365 Defender portal.</span></span>

  <span data-ttu-id="fda1e-134">有关详细信息，请参阅 Microsoft 365 Defender[门户中的权限](permissions-microsoft-365-security-center.md)和 Exchange Online 中[的权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="fda1e-135">**注意**：</span><span class="sxs-lookup"><span data-stu-id="fda1e-135">**Notes**:</span></span>

  - <span data-ttu-id="fda1e-136">将用户添加到 Azure Active Directory 中的相应 Microsoft 365 管理中心 可为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能Microsoft 365。 </span><span class="sxs-lookup"><span data-stu-id="fda1e-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="fda1e-137">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="fda1e-138">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="fda1e-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="fda1e-139">有关我们针对附件策略保险箱设置，请参阅保险箱[附件设置。](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="fda1e-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="fda1e-140">最多允许应用新策略或更新策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="fda1e-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a><span data-ttu-id="fda1e-141">使用Microsoft 365 Defender门户创建保险箱附件策略</span><span class="sxs-lookup"><span data-stu-id="fda1e-141">Use the Microsoft 365 Defender portal to create Safe Attachments policies</span></span>

<span data-ttu-id="fda1e-142">在 保险箱 门户中创建自定义附件Microsoft 365 Defender会同时使用同一名称创建安全附件规则和相关的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fda1e-142">Creating a custom Safe Attachments policy in the Microsoft 365 Defender portal creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="fda1e-143">In the Microsoft 365 Defender portal， go to **Email & collaboration** Policies & \> **rules** Threat \> **policies** \> **Policies** section \> **保险箱 Attachments**.</span><span class="sxs-lookup"><span data-stu-id="fda1e-143">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="fda1e-144">在 **"保险箱"页上**，单击" ![ 创建"图标" ](../../media/m365-cc-sc-create-icon.png) **创建"。**</span><span class="sxs-lookup"><span data-stu-id="fda1e-144">On the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="fda1e-145">将打开策略向导。</span><span class="sxs-lookup"><span data-stu-id="fda1e-145">The policy wizard opens.</span></span> <span data-ttu-id="fda1e-146">在" **命名策略"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="fda1e-146">On the **Name your policy** page, configure the following settings:</span></span>
   - <span data-ttu-id="fda1e-147">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="fda1e-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="fda1e-148">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="fda1e-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="fda1e-149">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="fda1e-150">在 **出现的"用户** 和域"页上，标识策略应用于以下收件人 (内部) ：</span><span class="sxs-lookup"><span data-stu-id="fda1e-150">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="fda1e-151">**用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="fda1e-151">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="fda1e-152">**组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="fda1e-152">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="fda1e-153">**域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="fda1e-153">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="fda1e-154">单击相应的框，开始键入值，然后从结果中选择所需的值。</span><span class="sxs-lookup"><span data-stu-id="fda1e-154">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="fda1e-155">根据需要多次重复此过程。</span><span class="sxs-lookup"><span data-stu-id="fda1e-155">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="fda1e-156">若要删除现有值，请单击值旁边的</span><span class="sxs-lookup"><span data-stu-id="fda1e-156">To remove an existing value, click remove</span></span> ![删除图标](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="fda1e-158">“删除”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-158">next to the value.</span></span>

   <span data-ttu-id="fda1e-159">对于用户或组，可以使用大多数标识符（姓名、显示名称、别名、电子邮件地址、帐户名称等），但是相应的显示名称会显示在结果中。</span><span class="sxs-lookup"><span data-stu-id="fda1e-159">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="fda1e-160">对于用户，请自行输入星号 (\*) 以查看所有可用值。</span><span class="sxs-lookup"><span data-stu-id="fda1e-160">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="fda1e-161">同一个条件的多个值使用 OR 逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="fda1e-161">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="fda1e-162">不同的条件使用 AND 逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="fda1e-162">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="fda1e-163">**排除这些用户、组和域**：若要为策略应用于的内部收件人添加例外（收件人例外），请选择此选项并配置例外。</span><span class="sxs-lookup"><span data-stu-id="fda1e-163">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="fda1e-164">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="fda1e-164">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="fda1e-165">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-165">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="fda1e-166">在“**设置**”页上，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="fda1e-166">On the **Settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="fda1e-167">**保险箱附件未知恶意软件响应**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="fda1e-167">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>
     - <span data-ttu-id="fda1e-168">**关闭**：通常，不建议使用此值。</span><span class="sxs-lookup"><span data-stu-id="fda1e-168">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="fda1e-169">**监视器**</span><span class="sxs-lookup"><span data-stu-id="fda1e-169">**Monitor**</span></span>
     - <span data-ttu-id="fda1e-170">**Block**：这是默认值，以及 Standard 和 Strict 预设安全策略 [中的建议值](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-170">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="fda1e-171">**Replace**</span><span class="sxs-lookup"><span data-stu-id="fda1e-171">**Replace**</span></span>
     - <span data-ttu-id="fda1e-172">**动态传递 (预览功能)**</span><span class="sxs-lookup"><span data-stu-id="fda1e-172">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="fda1e-173">这些值在附件策略[保险箱中进行了介绍](safe-attachments.md#safe-attachments-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-173">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="fda1e-174">重定向带检测到的附件的邮件：如果选择"启用重定向"，可以在"将包含阻止、监视或替换附件的邮件发送到指定电子邮件地址"框中指定电子邮件地址，以发送包含恶意软件附件的邮件，以便进行分析和调查。 </span><span class="sxs-lookup"><span data-stu-id="fda1e-174">**Redirect messages with detected attachments**: If you select **Enable redirect**, you can specify an email address in the **Send messages that contain blocked, monitored, or replaced attachments to the specified email address** box to send messages that contain malware attachments for analysis and investigation.</span></span>

     <span data-ttu-id="fda1e-175">对于"标准"和"严格"策略设置，建议启用重定向。</span><span class="sxs-lookup"><span data-stu-id="fda1e-175">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="fda1e-176">有关详细信息，请参阅附件[保险箱设置](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-176">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="fda1e-177">如果 **扫描无法完成 (** 超时或错误) ，则应用 保险箱 附件检测响应：即使 **保险箱** 附件扫描无法完成，保险箱 附件未知恶意软件响应也将会对邮件执行该操作。</span><span class="sxs-lookup"><span data-stu-id="fda1e-177">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="fda1e-178">如果选择此选项，请始终选择" **启用重定向** "，并指定电子邮件地址以发送包含恶意软件附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="fda1e-178">If you selected this option, always select **Enable redirect** and specify an email address to send messages that contain malware attachments.</span></span> <span data-ttu-id="fda1e-179">否则，邮件可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="fda1e-179">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="fda1e-180">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="fda1e-181">在出现的“**审阅**”页面上，查看你的设置。</span><span class="sxs-lookup"><span data-stu-id="fda1e-181">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="fda1e-182">可以在每个部分中选择“**编辑**”来修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="fda1e-182">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="fda1e-183">或者，可以单击“**返回**”或选择向导中的特定页面。</span><span class="sxs-lookup"><span data-stu-id="fda1e-183">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="fda1e-184">完成后，单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="fda1e-184">When you're finished, click **Submit**.</span></span>

7. <span data-ttu-id="fda1e-185">在出现的确认页面上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-185">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a><span data-ttu-id="fda1e-186">使用 Microsoft 365 Defender 门户查看保险箱附件策略</span><span class="sxs-lookup"><span data-stu-id="fda1e-186">Use the Microsoft 365 Defender portal to view Safe Attachments policies</span></span>

1. <span data-ttu-id="fda1e-187">In the Microsoft 365 Defender portal， go to **Email & collaboration** Policies & \> **rules** Threat \> **policies** \> **Policies** section \> **保险箱 Attachments**.</span><span class="sxs-lookup"><span data-stu-id="fda1e-187">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="fda1e-188">在 **"保险箱"** 页上，策略列表中将显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="fda1e-188">On the **Safe Attachments** page, the following properties are displayed in the list of policies:</span></span>
   - <span data-ttu-id="fda1e-189">**名称**</span><span class="sxs-lookup"><span data-stu-id="fda1e-189">**Name**</span></span>
   - <span data-ttu-id="fda1e-190">**状态**</span><span class="sxs-lookup"><span data-stu-id="fda1e-190">**Status**</span></span>
   - <span data-ttu-id="fda1e-191">**优先级**</span><span class="sxs-lookup"><span data-stu-id="fda1e-191">**Priority**</span></span>

3. <span data-ttu-id="fda1e-192">当您通过单击该名称选择策略时，策略设置将显示在一个飞出内容中。</span><span class="sxs-lookup"><span data-stu-id="fda1e-192">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a><span data-ttu-id="fda1e-193">使用Microsoft 365 Defender门户修改保险箱附件策略</span><span class="sxs-lookup"><span data-stu-id="fda1e-193">Use the Microsoft 365 Defender portal to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="fda1e-194">In the Microsoft 365 Defender portal， go to **Email & collaboration** Policies & \> **rules** Threat \> **policies** \> **Policies** section \> **保险箱 Attachments**.</span><span class="sxs-lookup"><span data-stu-id="fda1e-194">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="fda1e-195">On the **保险箱 Attachments** page， select a policy from the list by clicking on the name.</span><span class="sxs-lookup"><span data-stu-id="fda1e-195">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="fda1e-196">在出现的策略详细信息浮出控件中，选择每个部分中的“**编辑**”以修改该部分中的设置。</span><span class="sxs-lookup"><span data-stu-id="fda1e-196">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="fda1e-197">有关设置详细信息，请参阅本文前面使用 Microsoft 365 Defender 门户创建保险箱[附件](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies)策略部分。</span><span class="sxs-lookup"><span data-stu-id="fda1e-197">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create Safe Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) section earlier in this article.</span></span>  

<span data-ttu-id="fda1e-198">若要启用或禁用策略或设置策略优先级顺序，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="fda1e-198">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="fda1e-199">启用或禁用保险箱附件策略</span><span class="sxs-lookup"><span data-stu-id="fda1e-199">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="fda1e-200">In the Microsoft 365 Defender portal， go to **Email & collaboration** Policies & \> **rules** Threat \> **policies** \> **Policies** section \> **保险箱 Attachments**.</span><span class="sxs-lookup"><span data-stu-id="fda1e-200">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="fda1e-201">On the **保险箱 Attachments** page， select a policy from the list by clicking on the name.</span><span class="sxs-lookup"><span data-stu-id="fda1e-201">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="fda1e-202">在出现的策略详细信息浮出控件顶部，你将看到以下值之一：</span><span class="sxs-lookup"><span data-stu-id="fda1e-202">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="fda1e-203">**策略关闭**：若要打开策略，请单击![“打开”图标](../../media/m365-cc-sc-turn-on-off-icon.png)“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-203">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="fda1e-204">**策略打开**：若要关闭策略，请单击![“关闭”图标](../../media/m365-cc-sc-turn-on-off-icon.png)“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-204">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="fda1e-205">在出现的确认对话框中，单击“**打开**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-205">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="fda1e-206">单击策略详细信息浮出控件中的“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-206">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="fda1e-207">返回主策略页面，策略的“**状态**”值将为“**打开**”或“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-207">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="fda1e-208">设置"附件保险箱的优先级</span><span class="sxs-lookup"><span data-stu-id="fda1e-208">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="fda1e-209">默认情况下，保险箱附件策略的优先级基于它们在新策略中创建的顺序 (较旧策略的优先级低) 。</span><span class="sxs-lookup"><span data-stu-id="fda1e-209">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="fda1e-210">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="fda1e-210">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="fda1e-211">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="fda1e-211">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="fda1e-212">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-212">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="fda1e-213">保险箱附件策略按其处理顺序显示 (优先级值为 0 的附件) 。 </span><span class="sxs-lookup"><span data-stu-id="fda1e-213">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="fda1e-214">**注意**：在Microsoft 365 Defender门户中，只能在创建附件保险箱更改策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="fda1e-214">**Note**: In the Microsoft 365 Defender portal, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="fda1e-215">在 PowerShell 中，您可以在创建可影响现有规则优先级的安全附件规则 (默认优先级。) 。</span><span class="sxs-lookup"><span data-stu-id="fda1e-215">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="fda1e-216">若要更改策略的优先级，请单击策略属性中的“**提高优先级**”或“**降低优先级**”（不能直接修改 Microsoft 365 Defender 门户中的“**优先级**”数字）。</span><span class="sxs-lookup"><span data-stu-id="fda1e-216">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="fda1e-217">只有当你有多个策略时，更改策略的优先级才有意义。</span><span class="sxs-lookup"><span data-stu-id="fda1e-217">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="fda1e-218">In the Microsoft 365 Defender portal， go to **Email & collaboration** Policies & \> **rules** Threat \> **policies** \> **Policies** section \> **保险箱 Attachments**.</span><span class="sxs-lookup"><span data-stu-id="fda1e-218">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="fda1e-219">On the **保险箱 Attachments** page， select a policy from the list by clicking on the name.</span><span class="sxs-lookup"><span data-stu-id="fda1e-219">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="fda1e-220">在出现的策略详细信息飞出的顶部，你将看到"根据当前优先级值和策略数增加优先级"或"减少优先级"：</span><span class="sxs-lookup"><span data-stu-id="fda1e-220">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of policies:</span></span>
   - <span data-ttu-id="fda1e-221">优先级值为 **0** **的策略** 只有"**减少优先级"** 选项可用。</span><span class="sxs-lookup"><span data-stu-id="fda1e-221">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="fda1e-222">优先级值最低的策略 (例如 **，3**) 只有"增加优先级 **"** 选项可用。</span><span class="sxs-lookup"><span data-stu-id="fda1e-222">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="fda1e-223">如果你有三个或多个策略，则最高优先级值和最低优先级值之间的策略同时具有"增加 **优先级** "和" **减少优先级"** 选项。</span><span class="sxs-lookup"><span data-stu-id="fda1e-223">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="fda1e-224">单击![“提高优先级”图标](../../media/m365-cc-sc-increase-icon.png)“**提高优先级**”或![“降低优先级”图标](../../media/m365-cc-sc-decrease-icon.png)“**降低优先级**”以更改“**优先级**”值。</span><span class="sxs-lookup"><span data-stu-id="fda1e-224">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="fda1e-225">完成后，单击策略详细信息浮出控件中的“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-225">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a><span data-ttu-id="fda1e-226">使用 Microsoft 365 Defender 门户删除保险箱附件策略</span><span class="sxs-lookup"><span data-stu-id="fda1e-226">Use the Microsoft 365 Defender portal to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="fda1e-227">In the Microsoft 365 Defender portal， go to **Email & collaboration** Policies & \> **rules** Threat \> **policies** \> **Policies** section \> **保险箱 Attachments**.</span><span class="sxs-lookup"><span data-stu-id="fda1e-227">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="fda1e-228">On the **保险箱 Attachments** page， select a custom policy from the list by clicking on the name of the policy.</span><span class="sxs-lookup"><span data-stu-id="fda1e-228">On the **Safe Attachments** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="fda1e-229">在出现的策略详细信息浮出控件顶部，单击![“更多操作”图标](../../media/m365-cc-sc-more-actions-icon.png)“**更多操作**”\> ![“删除策略”图标](../../media/m365-cc-sc-delete-icon.png)“**删除策略**”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-229">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="fda1e-230">在出现的确认对话框中，单击“**是**”。</span><span class="sxs-lookup"><span data-stu-id="fda1e-230">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="fda1e-231">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置保险箱附件策略</span><span class="sxs-lookup"><span data-stu-id="fda1e-231">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="fda1e-232">如前所述，附件保险箱由安全附件策略和安全附件规则组成。</span><span class="sxs-lookup"><span data-stu-id="fda1e-232">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="fda1e-233">在 PowerShell 中，安全附件策略和安全附件规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="fda1e-233">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="fda1e-234">您可以使用 **\* -SafeAttachmentPolicy** cmdlet 管理安全附件策略，然后使用 **\* -SafeAttachmentRule** cmdlet 管理安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fda1e-234">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="fda1e-235">在 PowerShell 中，首先创建安全附件策略，然后创建用于标识该规则所适用的策略的安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fda1e-235">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="fda1e-236">在 PowerShell 中，分别修改安全附件策略和安全附件规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="fda1e-236">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="fda1e-237">从 PowerShell 删除安全附件策略时，不会自动删除相应的安全附件规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="fda1e-237">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="fda1e-238">使用 PowerShell 创建保险箱附件策略</span><span class="sxs-lookup"><span data-stu-id="fda1e-238">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="fda1e-239">在 PowerShell 保险箱附件策略的过程包含两个步骤：</span><span class="sxs-lookup"><span data-stu-id="fda1e-239">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="fda1e-240">创建安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fda1e-240">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="fda1e-241">创建安全附件规则，该规则指定应用该规则的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fda1e-241">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="fda1e-242">**注意**：</span><span class="sxs-lookup"><span data-stu-id="fda1e-242">**Notes**:</span></span>

- <span data-ttu-id="fda1e-243">可以创建新的安全附件规则，并为其分配现有的未关联的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fda1e-243">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="fda1e-244">安全附件规则不能与多个安全附件策略关联。</span><span class="sxs-lookup"><span data-stu-id="fda1e-244">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="fda1e-245">可以在 PowerShell 中的新安全附件策略上配置以下设置，这些设置在 Microsoft 365 Defender门户中不可用，直到创建策略之后：</span><span class="sxs-lookup"><span data-stu-id="fda1e-245">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="fda1e-246">在 `$false` **New-SafeAttachmentRule** cmdlet (上创建禁用的新策略) 。</span><span class="sxs-lookup"><span data-stu-id="fda1e-246">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="fda1e-247">在 _\<Number\>_ **New-SafeAttachmentRule** cmdlet (设置策略) 优先级) 。</span><span class="sxs-lookup"><span data-stu-id="fda1e-247">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="fda1e-248">在 PowerShell 中新建的安全附件策略在 Microsoft 365 Defender中不可见，除非将策略分配给安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fda1e-248">A new safe attachment policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="fda1e-249">步骤 1：使用 PowerShell 创建安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fda1e-249">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="fda1e-250">若要创建安全附件策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fda1e-250">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="fda1e-251">此示例创建一个名为 Contoso All 的安全附件策略，并具有以下值：</span><span class="sxs-lookup"><span data-stu-id="fda1e-251">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="fda1e-252">在未使用 _Action_ 参数保险箱文档扫描 (阻止发现包含恶意软件的邮件，默认值为 `Block`) 。</span><span class="sxs-lookup"><span data-stu-id="fda1e-252">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="fda1e-253">启用重定向，发现包含恶意软件的邮件将发送到 sec-ops@contoso.com 进行分析和调查。</span><span class="sxs-lookup"><span data-stu-id="fda1e-253">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="fda1e-254">如果保险箱附件扫描不可用或遇到错误，请不要传递邮件 (我们未使用 _ActionOnError_ 参数，默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="fda1e-254">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="fda1e-255">有关语法和参数的详细信息，请参阅 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-255">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="fda1e-256">步骤 2：使用 PowerShell 创建安全附件规则</span><span class="sxs-lookup"><span data-stu-id="fda1e-256">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="fda1e-257">若要创建安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fda1e-257">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="fda1e-258">本示例创建名为"Contoso All"的安全附件规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="fda1e-258">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="fda1e-259">该规则与名为 Contoso All 的安全附件策略相关联。</span><span class="sxs-lookup"><span data-stu-id="fda1e-259">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="fda1e-260">该规则适用于域中的所有 contoso.com 收件人。</span><span class="sxs-lookup"><span data-stu-id="fda1e-260">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="fda1e-261">因为我们没有使用 _Priority_ 参数，所以使用默认优先级。</span><span class="sxs-lookup"><span data-stu-id="fda1e-261">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="fda1e-262">如果规则 (_Enabled_ 参数，则启用该规则，默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="fda1e-262">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="fda1e-263">有关语法和参数的详细信息，请参阅 [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-263">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="fda1e-264">使用 PowerShell 查看安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fda1e-264">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="fda1e-265">若要查看现有安全附件策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fda1e-265">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fda1e-266">本示例返回所有安全附件策略的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="fda1e-266">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="fda1e-267">本示例返回名为 Contoso Executives 的安全附件策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fda1e-267">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="fda1e-268">有关语法和参数的详细信息，请参阅 [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-268">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="fda1e-269">使用 PowerShell 查看安全附件规则</span><span class="sxs-lookup"><span data-stu-id="fda1e-269">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="fda1e-270">若要查看现有安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fda1e-270">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fda1e-271">本示例返回所有安全附件规则的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="fda1e-271">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="fda1e-272">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fda1e-272">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="fda1e-273">本示例返回名为 Contoso Executives 的安全附件规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fda1e-273">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="fda1e-274">有关语法和参数的详细信息，请参阅 [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-274">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="fda1e-275">使用 PowerShell 修改安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fda1e-275">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="fda1e-276">如果 **Set-SafeAttachmentPolicy** cmdlet 没有 _Name_ 参数，则 (PowerShell 中的安全附件策略) 。</span><span class="sxs-lookup"><span data-stu-id="fda1e-276">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="fda1e-277">当你在 保险箱 门户中重命名Microsoft 365 Defender附件策略时，你仅重命名安全附件 _规则_。</span><span class="sxs-lookup"><span data-stu-id="fda1e-277">When you rename a Safe Attachments policy in the Microsoft 365 Defender portal, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="fda1e-278">否则，创建安全附件策略时可用的设置相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) 创建安全附件策略部分所述。</span><span class="sxs-lookup"><span data-stu-id="fda1e-278">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="fda1e-279">若要修改安全附件策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fda1e-279">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="fda1e-280">有关语法和参数的详细信息，请参阅 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-280">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="fda1e-281">使用 PowerShell 修改安全附件规则</span><span class="sxs-lookup"><span data-stu-id="fda1e-281">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="fda1e-282">在 PowerShell 中修改安全附件规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="fda1e-282">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="fda1e-283">若要启用或禁用现有安全附件规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="fda1e-283">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="fda1e-284">否则，创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) 创建安全附件规则部分中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="fda1e-284">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="fda1e-285">若要修改安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fda1e-285">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="fda1e-286">有关语法和参数的详细信息，请参阅 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-286">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="fda1e-287">使用 PowerShell 启用或禁用安全附件规则</span><span class="sxs-lookup"><span data-stu-id="fda1e-287">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="fda1e-288">在 PowerShell 中启用或禁用安全附件规则可启用或禁用整个 保险箱 附件策略 (安全附件规则以及分配的安全附件策略) 。</span><span class="sxs-lookup"><span data-stu-id="fda1e-288">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="fda1e-289">若要在 PowerShell 中启用或禁用安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fda1e-289">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="fda1e-290">本示例禁用名为"Marketing Department"的安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fda1e-290">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="fda1e-291">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="fda1e-291">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="fda1e-292">有关语法和参数的详细信息，请参阅[Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule)和[Disable-SafeAttachmentRule。](/powershell/module/exchange/disable-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="fda1e-292">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="fda1e-293">使用 PowerShell 设置安全附件规则的优先级</span><span class="sxs-lookup"><span data-stu-id="fda1e-293">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="fda1e-p126">可以设置的规则最高优先级值是 0。可以设置的最小优先级值取决于规则的数量。例如，如果有五个规则，则可以使用的优先级值为 0 到 4。更改现有规则的优先级可对其他规则产生级联效应。例如，假设有五个自定义规则（优先级为 0 到 4），如果将某个规则的优先级更改为 2，则优先级为 2 的现有规则将更改为优先级 3，优先级为 3 的规则将更改为优先级 4。</span><span class="sxs-lookup"><span data-stu-id="fda1e-p126">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="fda1e-299">若要在 PowerShell 中设置安全附件规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fda1e-299">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="fda1e-p127">此示例将名为"Marketing Department"规则的优先级设置为 2：具有小于或等于 2 优先级的所有现有规则的编号将递减 1（它们的优先级编号均递增 1）。</span><span class="sxs-lookup"><span data-stu-id="fda1e-p127">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="fda1e-302">**注意**：若要在创建新规则的优先级时设置它，请改为对 **New-SafeAttachmentRule** cmdlet 使用 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="fda1e-302">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="fda1e-303">有关语法和参数的详细信息，请参阅 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-303">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="fda1e-304">使用 PowerShell 删除安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fda1e-304">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="fda1e-305">使用 PowerShell 删除安全附件策略时，不会删除相应的安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fda1e-305">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="fda1e-306">若要在 PowerShell 中删除安全附件策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fda1e-306">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="fda1e-307">本示例删除名为 Marketing Department 的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fda1e-307">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="fda1e-308">有关语法和参数的详细信息，请参阅 [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-308">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="fda1e-309">使用 PowerShell 删除安全附件规则</span><span class="sxs-lookup"><span data-stu-id="fda1e-309">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="fda1e-310">使用 PowerShell 删除安全附件规则时，不会删除相应的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fda1e-310">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="fda1e-311">若要在 PowerShell 中删除安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fda1e-311">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="fda1e-312">本示例删除名为 Marketing Department 的安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fda1e-312">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="fda1e-313">有关语法和参数的详细信息，请参阅 [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-313">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="fda1e-314">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="fda1e-314">How do you know these procedures worked?</span></span>

<span data-ttu-id="fda1e-315">若要验证您是否已成功创建、修改或删除附件保险箱，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="fda1e-315">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="fda1e-316">In the Microsoft 365 Defender portal， go to **Email & collaboration** Policies & \> **rules** Threat \> **policies** \> **Policies** section \> **保险箱 Attachments**.</span><span class="sxs-lookup"><span data-stu-id="fda1e-316">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span> <span data-ttu-id="fda1e-317">验证策略列表、 **策略的 Status** 值及其 **Priority** 值。</span><span class="sxs-lookup"><span data-stu-id="fda1e-317">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="fda1e-318">若要查看更多详细信息，请通过单击名称从列表中选择策略，然后查看飞出中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fda1e-318">To view more details, select the policy from the list by clicking on the name, and view the details in the fly out.</span></span>

- <span data-ttu-id="fda1e-319">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，将 替换为策略或规则的名称，运行以下命令并 \<Name\> 验证设置：</span><span class="sxs-lookup"><span data-stu-id="fda1e-319">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="fda1e-320">若要验证附件保险箱扫描邮件，请检查可用的 Defender，查看Office 365报告。</span><span class="sxs-lookup"><span data-stu-id="fda1e-320">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="fda1e-321">有关详细信息，请参阅查看 Defender [for Office 365](view-reports-for-mdo.md)报告和在 Microsoft 365 Defender[门户中的使用资源管理器](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="fda1e-321">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>
