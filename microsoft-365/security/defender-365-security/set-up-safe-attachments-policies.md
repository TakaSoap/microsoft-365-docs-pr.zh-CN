---
title: 在 Microsoft Defender for Office 365 中设置安全附件策略
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
description: 了解如何定义安全附件策略以保护你的组织免受电子邮件中的恶意文件的攻击。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e96babff19ea981b953d35929813b1e08c000e32
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055183"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fa9d7-103">在 Microsoft Defender for Office 365 中设置安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fa9d7-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fa9d7-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="fa9d7-104">**Applies to**</span></span>
- [<span data-ttu-id="fa9d7-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="fa9d7-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="fa9d7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fa9d7-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="fa9d7-107">本文适用于拥有 [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="fa9d7-108">如果你是一位家庭用户，正在查找有关 Outlook 中的附件扫描的信息，请参阅高级 Outlook.com [安全](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="fa9d7-109">安全附件是 Microsoft [Defender for Office 365](whats-new-in-defender-for-office-365.md) 中的一项功能，该功能使用虚拟环境在 Exchange Online Protection [ (EOP) ](anti-malware-protection.md)中经过反恶意软件保护扫描之后，在发送给收件人之前，使用虚拟环境检查入站电子邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="fa9d7-110">有关详细信息，请参阅 [Microsoft Defender for Office 365](safe-attachments.md)中的安全附件。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="fa9d7-111">没有内置或默认安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="fa9d7-112">若要获取电子邮件附件的安全附件扫描，需要创建一个或多个安全附件策略，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="fa9d7-113">您可以在安全 &与合规中心或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置安全附件策略;适用于没有 Exchange Online 邮箱，但具有 Defender for Office 365 附加订阅的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-113">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="fa9d7-114">安全附件策略的基本元素包括：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="fa9d7-115">**安全附件策略**：指定未知恶意软件检测的操作、是否将带恶意软件附件的邮件发送到指定的电子邮件地址，以及是否在安全附件扫描无法完成时传递邮件。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="fa9d7-116">**安全附件规则**：指定策略应用于 (的优先级和收件人) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="fa9d7-117">在安全与合规中心内管理安全附件策略时，这两个元素&不明显：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-117">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="fa9d7-118">创建安全附件策略时，实际上是同时使用同一名称创建安全附件规则和相关的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="fa9d7-119">修改安全附件策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="fa9d7-120">所有其他设置修改关联的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="fa9d7-121">删除安全附件策略时，安全附件规则和相关的安全附件策略将被删除。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="fa9d7-122">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="fa9d7-123">有关详细信息，请参阅本文稍后的使用 Exchange Online PowerShell 或独立 [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) 配置安全附件策略部分。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="fa9d7-124">在安全附件设置的全局设置区域中，配置不依赖于安全附件策略的功能。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="fa9d7-125">有关说明，请参阅在[Microsoft 365 E5](safe-docs.md)中打开[SharePoint、OneDrive](turn-on-mdo-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件和安全文档。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fa9d7-126">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="fa9d7-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fa9d7-127">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fa9d7-128">若要直接转到"安全 **附件"页** ，请使用 <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-128">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="fa9d7-129">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="fa9d7-130">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fa9d7-131">您需获得权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="fa9d7-132">若要创建、修改和删除安全附件策略，您需要是安全 & 合规中心组织管理或安全管理员角色组的成员以及 Exchange Online 中的组织管理角色组的成员。  </span><span class="sxs-lookup"><span data-stu-id="fa9d7-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="fa9d7-133">若要对安全附件策略进行只读访问，你需要是安全与合规中心内全局读者或安全读者角色&的成员。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="fa9d7-134">有关详细信息，请参阅安全 [与合规](permissions-in-the-security-and-compliance-center.md) 中心&和 [Exchange Online 中的权限](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="fa9d7-135">**注意**：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-135">**Notes**:</span></span>

  - <span data-ttu-id="fa9d7-136">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="fa9d7-137">有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="fa9d7-138">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="fa9d7-139">有关安全附件策略的建议设置，请参阅 [安全附件设置](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="fa9d7-140">最多允许应用新策略或更新策略 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="fa9d7-141">使用安全&中心创建安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fa9d7-141">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="fa9d7-142">在安全与合规中心内创建自定义安全附件策略&使用相同的名称同时创建安全附件规则和相关的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-142">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="fa9d7-143">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="fa9d7-144">在"安全 **附件"页上**，单击"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="fa9d7-144">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="fa9d7-145">将 **打开"新建安全附件"策略** 向导。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-145">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="fa9d7-146">在" **命名策略"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-146">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="fa9d7-147">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="fa9d7-148">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="fa9d7-149">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="fa9d7-150">在出现的 **"** 设置"页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-150">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fa9d7-151">**安全附件未知恶意软件响应**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-151">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="fa9d7-152">**关闭**：通常，不建议使用此值。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-152">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="fa9d7-153">**监视器**</span><span class="sxs-lookup"><span data-stu-id="fa9d7-153">**Monitor**</span></span>
     - <span data-ttu-id="fa9d7-154">**Block**：这是默认值，以及 Standard 和 Strict 预设安全策略 [中的建议值](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-154">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="fa9d7-155">**Replace**</span><span class="sxs-lookup"><span data-stu-id="fa9d7-155">**Replace**</span></span>
     - <span data-ttu-id="fa9d7-156">**动态传递 (预览功能)**</span><span class="sxs-lookup"><span data-stu-id="fa9d7-156">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="fa9d7-157">这些值在安全附件 [策略设置中进行了介绍](safe-attachments.md#safe-attachments-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-157">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="fa9d7-158">将附件发送到以下电子邮件地址：对于操作值 **Block** **、Monitor** 或 **Replace**，可以选择"启用重定向"，将包含恶意软件附件的邮件发送到指定的内部或外部电子邮件地址，以便进行分析和调查。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-158">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="fa9d7-159">对于"标准"和"严格"策略设置，建议启用重定向。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-159">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="fa9d7-160">有关详细信息，请参阅安全 [附件设置](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-160">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="fa9d7-161">**如果附件的恶意软件** 扫描出现次数或出现错误，则应用上述选择：即使安全附件扫描无法完成，对邮件执行安全附件未知恶意软件响应指定的操作。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-161">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="fa9d7-162">如果选择此选项，请始终选择"已启用 **重定向"。**</span><span class="sxs-lookup"><span data-stu-id="fa9d7-162">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="fa9d7-163">否则，邮件可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-163">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="fa9d7-164">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-164">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="fa9d7-165">在 **出现的"应用于** "页上，标识策略应用于的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-165">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="fa9d7-166">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-166">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="fa9d7-167">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-167">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="fa9d7-168">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-168">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="fa9d7-169">单击 **"添加条件"。**</span><span class="sxs-lookup"><span data-stu-id="fa9d7-169">Click **Add a condition**.</span></span> <span data-ttu-id="fa9d7-170">In the dropdown that appears， select a condition under **Applied if**：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-170">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="fa9d7-171">**收件人为**：指定您的组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-171">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="fa9d7-172">**收件人是 ：指定** 组织中一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-172">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="fa9d7-173">**收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-173">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="fa9d7-174">选择条件后，将显示相应的下拉列表，其中显示其中 **任何** 一个框。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-174">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="fa9d7-175">在框中单击并滚动要选择的值列表。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-175">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="fa9d7-176">在框中单击并开始键入以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-176">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="fa9d7-177">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-177">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="fa9d7-178">若要删除单个条目，请单击值 **上的"** ![ 删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-178">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="fa9d7-179">若要删除整个条件，请单击条件 ![ 上的"删除 ](../../media/scc-remove-icon.png) ""删除"图标。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-179">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="fa9d7-180">若要添加其他条件，请单击" **添加条件** "，然后选择"应用的条件 **"下的其余值**。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-180">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="fa9d7-181">若要添加例外，请单击" **添加条件"，** 然后选择"例外条件 **"下的例外**。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-181">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="fa9d7-182">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-182">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="fa9d7-183">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-183">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="fa9d7-184">在出现的 **"查看设置** "页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-184">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="fa9d7-185">可以单击每个 **设置** 上的"编辑"来修改它。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-185">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="fa9d7-186">完成后，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="fa9d7-186">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="fa9d7-187">使用安全&中心查看安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fa9d7-187">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="fa9d7-188">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-188">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="fa9d7-189">在" **安全附件** "页上，从列表中选择一个策略， (不要选中"安全附件") 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-189">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="fa9d7-190">策略详细信息以飞出方式显示</span><span class="sxs-lookup"><span data-stu-id="fa9d7-190">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="fa9d7-191">使用安全&中心修改安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fa9d7-191">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="fa9d7-192">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-192">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="fa9d7-193">在" **安全附件** "页上，从列表中选择一个策略， (不要选中"安全附件") 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-193">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="fa9d7-194">在出现的策略详细信息飞出中，单击"编辑 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="fa9d7-194">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="fa9d7-195">飞出中的可用设置与使用安全与合规中心创建安全附件策略& [中所述的设置相同](#use-the-security--compliance-center-to-create-safe-attachments-policies) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-195">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="fa9d7-196">若要启用或禁用策略或设置策略优先级顺序，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-196">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="fa9d7-197">启用或禁用安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fa9d7-197">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="fa9d7-198">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="fa9d7-199">请注意"状态" **列中** 的值：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-199">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="fa9d7-200">将切换开关向左移动</span><span class="sxs-lookup"><span data-stu-id="fa9d7-200">Move the toggle to the left</span></span> ![关闭策略](../../media/scc-toggle-off.png) <span data-ttu-id="fa9d7-202">禁用策略。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-202">to disable the policy.</span></span>

   - <span data-ttu-id="fa9d7-203">将切换开关向右移动</span><span class="sxs-lookup"><span data-stu-id="fa9d7-203">Move the toggle to the right</span></span> ![打开策略](../../media/scc-toggle-on.png) <span data-ttu-id="fa9d7-205">启用策略。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-205">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="fa9d7-206">设置安全附件策略的优先级</span><span class="sxs-lookup"><span data-stu-id="fa9d7-206">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="fa9d7-207">默认情况下，安全附件策略的优先级基于这些策略在较新策略中创建的顺序 (策略的优先级低于较旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-207">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="fa9d7-208">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-208">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="fa9d7-209">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-209">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="fa9d7-210">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-210">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="fa9d7-211">第一个策略的优先级值为 0 时，安全附件策略 (其处理顺序) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-211">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="fa9d7-212">**注意**：在安全&合规中心，只能在创建安全附件策略后更改策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-212">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="fa9d7-213">在 PowerShell 中，您可以在创建可影响现有规则优先级的安全附件规则 (默认优先级。) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-213">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="fa9d7-214">若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-214">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="fa9d7-215">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-215">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="fa9d7-216">在" **安全附件** "页上，从列表中选择一个策略， (不要选中"安全附件") 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-216">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="fa9d7-217">在出现的策略详细信息飞出中，单击可用的优先级按钮。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-217">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="fa9d7-218">优先级值为 **0** **的安全** 附件策略只有"**减少优先级"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-218">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="fa9d7-219">优先级值最低的安全附件策略 (例如 **，3**) 只有"增加 **优先级"** 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-219">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="fa9d7-220">如果你有三个或多个安全附件策略，则优先级最高和最低值之间的策略同时具有"增加 **优先级** "和" **减少优先级"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-220">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="fa9d7-221">单击 **"增加优先级** " **或"减少优先级** "可更改 **"优先级"** 值。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-221">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="fa9d7-222">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-222">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="fa9d7-223">使用安全&中心删除安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fa9d7-223">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="fa9d7-224">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="fa9d7-225">在" **安全附件** "页上，从列表中选择一个策略， (不要选中"安全附件") 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-225">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="fa9d7-226">在随即出现的策略详细信息飞出中，单击"删除 **策略**"，然后在出现的警告对话框中单击"是"。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="fa9d7-227">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fa9d7-227">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="fa9d7-228">如前所述，安全附件策略由安全附件策略和安全附件规则组成。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-228">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="fa9d7-229">在 PowerShell 中，安全附件策略和安全附件规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-229">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="fa9d7-230">您可以使用 **\* -SafeAttachmentPolicy** cmdlet 管理安全附件策略，然后使用 **\* -SafeAttachmentRule** cmdlet 管理安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-230">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="fa9d7-231">在 PowerShell 中，首先创建安全附件策略，然后创建用于标识该规则所适用的策略的安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-231">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="fa9d7-232">在 PowerShell 中，分别修改安全附件策略和安全附件规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-232">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="fa9d7-233">从 PowerShell 删除安全附件策略时，不会自动删除相应的安全附件规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-233">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="fa9d7-234">使用 PowerShell 创建安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fa9d7-234">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="fa9d7-235">在 PowerShell 中创建安全附件策略的过程包含两个步骤：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-235">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="fa9d7-236">创建安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-236">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="fa9d7-237">创建安全附件规则，该规则指定应用该规则的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-237">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="fa9d7-238">**注意**：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-238">**Notes**:</span></span>

- <span data-ttu-id="fa9d7-239">可以创建新的安全附件规则，并为其分配现有的未关联的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-239">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="fa9d7-240">安全附件规则不能与多个安全附件策略关联。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-240">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="fa9d7-241">可以在 PowerShell 中的新安全附件策略上配置以下设置，这些设置在安全与合规&中心不可用，除非创建策略：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-241">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="fa9d7-242">在 `$false` **New-SafeAttachmentRule** cmdlet (上创建禁用的新策略) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-242">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="fa9d7-243">在 _\<Number\>_ **New-SafeAttachmentRule** cmdlet (设置策略) 优先级) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-243">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="fa9d7-244">在 PowerShell 中新建的安全附件策略在安全与合规中心&，除非将策略分配给安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-244">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="fa9d7-245">步骤 1：使用 PowerShell 创建安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fa9d7-245">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="fa9d7-246">若要创建安全附件策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-246">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="fa9d7-247">此示例创建一个名为 Contoso All 的安全附件策略，并具有以下值：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-247">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="fa9d7-248">阻止通过安全文档扫描发现包含恶意软件 (我们未使用 _Action_ 参数，并且默认值为 `Block`) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-248">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="fa9d7-249">启用重定向，发现包含恶意软件的邮件将发送到 sec-ops@contoso.com 进行分析和调查。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-249">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="fa9d7-250">如果安全附件扫描不可用或遇到错误，请不要传递邮件 (我们未使用 _ActionOnError_ 参数，默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-250">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="fa9d7-251">有关语法和参数的详细信息，请参阅 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-251">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="fa9d7-252">步骤 2：使用 PowerShell 创建安全附件规则</span><span class="sxs-lookup"><span data-stu-id="fa9d7-252">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="fa9d7-253">若要创建安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-253">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="fa9d7-254">本示例创建名为"Contoso All"的安全附件规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-254">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="fa9d7-255">该规则与名为 Contoso All 的安全附件策略相关联。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-255">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="fa9d7-256">该规则适用于域中的所有 contoso.com 收件人。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-256">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="fa9d7-257">因为我们没有使用 _Priority_ 参数，所以使用默认优先级。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-257">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="fa9d7-258">如果规则 (_Enabled_ 参数，则启用该规则，默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-258">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="fa9d7-259">有关语法和参数的详细信息，请参阅 [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-259">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="fa9d7-260">使用 PowerShell 查看安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fa9d7-260">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="fa9d7-261">若要查看现有安全附件策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-261">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fa9d7-262">本示例返回所有安全附件策略的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-262">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="fa9d7-263">本示例返回名为 Contoso Executives 的安全附件策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-263">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="fa9d7-264">有关语法和参数的详细信息，请参阅 [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-264">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="fa9d7-265">使用 PowerShell 查看安全附件规则</span><span class="sxs-lookup"><span data-stu-id="fa9d7-265">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="fa9d7-266">若要查看现有安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-266">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fa9d7-267">本示例返回所有安全附件规则的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-267">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="fa9d7-268">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-268">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="fa9d7-269">本示例返回名为 Contoso Executives 的安全附件规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-269">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="fa9d7-270">有关语法和参数的详细信息，请参阅 [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-270">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="fa9d7-271">使用 PowerShell 修改安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fa9d7-271">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="fa9d7-272">如果 **Set-SafeAttachmentPolicy** cmdlet 没有 _Name_ 参数，则 (PowerShell 中的安全附件策略) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-272">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="fa9d7-273">在安全与合规中心内重命名安全附件&，只需重命名安全附件 _规则_。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-273">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="fa9d7-274">否则，创建安全附件策略时可用的设置相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) 创建安全附件策略部分所述。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-274">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="fa9d7-275">若要修改安全附件策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-275">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="fa9d7-276">有关语法和参数的详细信息，请参阅 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-276">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="fa9d7-277">使用 PowerShell 修改安全附件规则</span><span class="sxs-lookup"><span data-stu-id="fa9d7-277">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="fa9d7-278">在 PowerShell 中修改安全附件规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-278">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="fa9d7-279">若要启用或禁用现有安全附件规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-279">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="fa9d7-280">否则，创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) 创建安全附件规则部分中所述的设置相同。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-280">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="fa9d7-281">若要修改安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-281">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="fa9d7-282">有关语法和参数的详细信息，请参阅 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-282">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="fa9d7-283">使用 PowerShell 启用或禁用安全附件规则</span><span class="sxs-lookup"><span data-stu-id="fa9d7-283">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="fa9d7-284">在 PowerShell 中启用或禁用安全附件规则可启用或禁用整个安全附件策略 (安全附件规则以及分配的安全附件策略) 。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-284">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="fa9d7-285">若要在 PowerShell 中启用或禁用安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-285">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="fa9d7-286">本示例禁用名为"Marketing Department"的安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-286">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="fa9d7-287">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-287">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="fa9d7-288">有关语法和参数的详细信息，请参阅[Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule)和[Disable-SafeAttachmentRule。](/powershell/module/exchange/disable-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="fa9d7-288">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="fa9d7-289">使用 PowerShell 设置安全附件规则的优先级</span><span class="sxs-lookup"><span data-stu-id="fa9d7-289">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="fa9d7-290">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-290">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="fa9d7-291">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-291">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="fa9d7-292">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-292">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="fa9d7-293">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-293">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="fa9d7-294">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-294">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="fa9d7-295">若要在 PowerShell 中设置安全附件规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-295">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="fa9d7-296">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-296">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="fa9d7-297">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-297">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="fa9d7-298">**注意**：若要在创建新规则的优先级时设置它，请改为对 **New-SafeAttachmentRule** cmdlet 使用 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-298">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="fa9d7-299">有关语法和参数的详细信息，请参阅 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-299">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="fa9d7-300">使用 PowerShell 删除安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fa9d7-300">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="fa9d7-301">使用 PowerShell 删除安全附件策略时，不会删除相应的安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-301">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="fa9d7-302">若要在 PowerShell 中删除安全附件策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-302">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="fa9d7-303">本示例删除名为 Marketing Department 的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-303">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="fa9d7-304">有关语法和参数的详细信息，请参阅 [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-304">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="fa9d7-305">使用 PowerShell 删除安全附件规则</span><span class="sxs-lookup"><span data-stu-id="fa9d7-305">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="fa9d7-306">使用 PowerShell 删除安全附件规则时，不会删除相应的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-306">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="fa9d7-307">若要在 PowerShell 中删除安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-307">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="fa9d7-308">本示例删除名为 Marketing Department 的安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-308">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="fa9d7-309">有关语法和参数的详细信息，请参阅 [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-309">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="fa9d7-310">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="fa9d7-310">How do you know these procedures worked?</span></span>

<span data-ttu-id="fa9d7-311">若要验证您是否已成功创建、修改或删除安全附件策略，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-311">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="fa9d7-312">在安全与&中心，转到威胁 **管理** \> **策略** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-312">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="fa9d7-313">验证策略列表、 **策略的 Status** 值及其 **Priority** 值。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-313">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="fa9d7-314">若要查看更多详细信息，请从列表中选择策略，然后查看飞出中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-314">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="fa9d7-315">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，将 替换为策略或规则的名称，运行 \<Name\> 以下命令并验证设置：</span><span class="sxs-lookup"><span data-stu-id="fa9d7-315">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="fa9d7-316">若要验证安全附件是否正在扫描邮件，请检查可用的 Defender for Office 365 报告。</span><span class="sxs-lookup"><span data-stu-id="fa9d7-316">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="fa9d7-317">有关详细信息，请参阅[查看适用于 Office 365 的 Defender](view-reports-for-mdo.md)报告和使用安全与合规中心&[资源管理器。](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="fa9d7-317">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
