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
description: 了解如何定义安全附件策略来保护组织免受电子邮件中的恶意文件的攻击。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9343ce222f1deb84e900f0d6f18e7d55daa73372
ms.sourcegitcommit: 4f40f5be140a23bacff6fd7b85536de14fc7d499
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084609"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2d963-103">在 Microsoft Defender for Office 365 中设置安全附件策略</span><span class="sxs-lookup"><span data-stu-id="2d963-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="2d963-104">本文适用于拥有 [Microsoft Defender for Office 365](office-365-atp.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="2d963-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="2d963-105">如果你是一位家庭用户，正在查找有关 Outlook 中的附件扫描的信息，请参阅高级Outlook.com [安全](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="2d963-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="2d963-106">安全附件是 Microsoft [Defender for Office 365](office-365-atp.md) 中的一项功能，它使用虚拟环境在 Exchange Online Protection [ (EOP) ](anti-malware-protection.md)中扫描入站电子邮件中的附件之后，在发送给收件人之前检查这些附件。</span><span class="sxs-lookup"><span data-stu-id="2d963-106">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="2d963-107">有关详细信息，请参阅 [Microsoft Defender for Office 365 中的安全附件](atp-safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="2d963-107">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="2d963-108">没有内置或默认安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="2d963-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="2d963-109">若要对电子邮件附件进行安全附件扫描，需要创建一个或多个安全附件策略，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="2d963-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="2d963-110">可以在 &安全与合规中心或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置安全附件策略;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell，但具有适用于 Office 365 加载项订阅的 Defender) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="2d963-111">安全附件策略的基本元素包括：</span><span class="sxs-lookup"><span data-stu-id="2d963-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="2d963-112">**安全附件** 策略：指定未知恶意软件检测的操作、是否将带有恶意软件附件的邮件发送到指定的电子邮件地址，以及是否传递安全附件扫描无法完成的邮件。</span><span class="sxs-lookup"><span data-stu-id="2d963-112">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="2d963-113">**安全附件规则**：指定策略应用于 (的优先级和收件人) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-113">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="2d963-114">在安全与合规中心内管理安全附件策略时，这两个元素&不明显：</span><span class="sxs-lookup"><span data-stu-id="2d963-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="2d963-115">创建安全附件策略时，实际上是同时使用同一名称创建安全附件规则和相关的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="2d963-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="2d963-116">修改安全附件策略时，与名称、优先级、已启用或禁用以及收件人筛选器相关的设置将修改安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="2d963-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="2d963-117">所有其他设置修改关联的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="2d963-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="2d963-118">删除安全附件策略时，安全附件规则和相关的安全附件策略将被删除。</span><span class="sxs-lookup"><span data-stu-id="2d963-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="2d963-119">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="2d963-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="2d963-120">有关详细信息，请参阅本文稍后介绍的"使用 Exchange Online PowerShell 或独立 [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) 配置安全附件策略"部分。</span><span class="sxs-lookup"><span data-stu-id="2d963-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="2d963-121">在安全附件设置的全局设置区域中，配置不依赖于安全附件策略的功能。</span><span class="sxs-lookup"><span data-stu-id="2d963-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="2d963-122">有关说明，请参阅在[Microsoft 365 E5](safe-docs.md)中打开[SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)和安全文档的安全附件。</span><span class="sxs-lookup"><span data-stu-id="2d963-122">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2d963-123">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="2d963-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2d963-124">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="2d963-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2d963-125">若要直接转到"安全 **附件"** 页，请使用 <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="2d963-125">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="2d963-126">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2d963-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2d963-127">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2d963-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2d963-128">您需获得权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="2d963-128">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="2d963-129">若要创建、修改和删除安全附件策略，您需要是 &安全与合规中心内组织管理或安全管理员角色组的成员和 Exchange Online 中的组织管理角色组的成员。 </span><span class="sxs-lookup"><span data-stu-id="2d963-129">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="2d963-130">若要对安全附件策略进行只读访问，你需要是安全与合规中心内全局读者或安全读者角色&的成员。</span><span class="sxs-lookup"><span data-stu-id="2d963-130">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="2d963-131">有关详细信息，请参阅 [安全与合规](permissions-in-the-security-and-compliance-center.md) 中心&和 [Exchange Online 中的权限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="2d963-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="2d963-132">**注意**：</span><span class="sxs-lookup"><span data-stu-id="2d963-132">**Notes**:</span></span>

  - <span data-ttu-id="2d963-133">向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。</span><span class="sxs-lookup"><span data-stu-id="2d963-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2d963-134">有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="2d963-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="2d963-135">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。</span><span class="sxs-lookup"><span data-stu-id="2d963-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="2d963-136">有关安全附件策略的建议设置，请参阅 [安全附件设置](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="2d963-136">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="2d963-137">允许应用新策略或更新策略的时间最多为 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="2d963-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="2d963-138">使用安全&中心创建安全附件策略</span><span class="sxs-lookup"><span data-stu-id="2d963-138">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="2d963-139">在安全与合规中心&安全附件策略会同时使用同一名称创建安全附件规则和相关的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="2d963-139">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="2d963-140">在安全&中心，转到 **"威胁管理** \> **策略** \> **ATP 安全附件"。**</span><span class="sxs-lookup"><span data-stu-id="2d963-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="2d963-141">在"**安全附件"** 页上，单击"**创建"。**</span><span class="sxs-lookup"><span data-stu-id="2d963-141">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="2d963-142">将 **打开"新建安全附件策略** "向导。</span><span class="sxs-lookup"><span data-stu-id="2d963-142">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="2d963-143">在 **"为策略命名"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="2d963-143">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="2d963-144">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="2d963-144">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="2d963-145">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="2d963-145">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="2d963-146">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="2d963-146">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="2d963-147">在 **出现的** "设置"页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="2d963-147">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2d963-148">**安全附件未知恶意软件响应**：选择下列值之一：</span><span class="sxs-lookup"><span data-stu-id="2d963-148">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="2d963-149">**关闭**：通常，不建议使用此值。</span><span class="sxs-lookup"><span data-stu-id="2d963-149">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="2d963-150">**监视器**</span><span class="sxs-lookup"><span data-stu-id="2d963-150">**Monitor**</span></span>
     - <span data-ttu-id="2d963-151">**Block**： 这是默认值，以及标准版和严格预设安全策略 [中的建议值](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2d963-151">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="2d963-152">**Replace**</span><span class="sxs-lookup"><span data-stu-id="2d963-152">**Replace**</span></span>
     - <span data-ttu-id="2d963-153">**动态传递 (预览功能)**</span><span class="sxs-lookup"><span data-stu-id="2d963-153">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="2d963-154">这些值在安全附件 [策略设置中进行了解释](atp-safe-attachments.md#safe-attachments-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="2d963-154">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="2d963-155">将附件发送到以下电子邮件地址：对于操作值Block、Monitor或 **Replace，** 可以选择"启用重定向"，将包含恶意软件附件的邮件发送到指定的内部或外部电子邮件地址，以便进行分析和调查。</span><span class="sxs-lookup"><span data-stu-id="2d963-155">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="2d963-156">对于"标准"和"严格"策略设置的建议是启用重定向。</span><span class="sxs-lookup"><span data-stu-id="2d963-156">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="2d963-157">有关详细信息，请参阅安全 [附件设置](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="2d963-157">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="2d963-158">**如果附件** 的恶意软件扫描次数或出现错误，则应用上述选择：即使安全附件扫描无法完成，对邮件执行安全附件未知恶意软件响应指定的操作。</span><span class="sxs-lookup"><span data-stu-id="2d963-158">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="2d963-159">如果选择此选项，请始终选择"**已启用重定向"。**</span><span class="sxs-lookup"><span data-stu-id="2d963-159">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="2d963-160">否则，邮件可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="2d963-160">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="2d963-161">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="2d963-161">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2d963-162">在 **出现的"应用于** "页上，标识策略所适用的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="2d963-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="2d963-163">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="2d963-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="2d963-164">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="2d963-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="2d963-165">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="2d963-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="2d963-166">单击 **"添加条件"。**</span><span class="sxs-lookup"><span data-stu-id="2d963-166">Click **Add a condition**.</span></span> <span data-ttu-id="2d963-167">In the dropdown that appears， select a condition under **Applied if**：</span><span class="sxs-lookup"><span data-stu-id="2d963-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="2d963-168">**收件人为**：指定组织中一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="2d963-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="2d963-169">**收件人是：** 指定组织中一个或多个组的成员。</span><span class="sxs-lookup"><span data-stu-id="2d963-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="2d963-170">**收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="2d963-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="2d963-171">选择条件后，将显示相应的下拉列表，其中显示其中 **任何** 一个框。</span><span class="sxs-lookup"><span data-stu-id="2d963-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="2d963-172">在框中单击并滚动要选择的值列表。</span><span class="sxs-lookup"><span data-stu-id="2d963-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="2d963-173">在框中单击并开始键入以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="2d963-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="2d963-174">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="2d963-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="2d963-175">若要删除单个条目 **，请单击值** ![ 上的" ](../../media/scc-remove-icon.png) 删除"图标。</span><span class="sxs-lookup"><span data-stu-id="2d963-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="2d963-176">若要删除整个条件 **，请单击** ![ 条件上的" ](../../media/scc-remove-icon.png) 删除"图标。</span><span class="sxs-lookup"><span data-stu-id="2d963-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="2d963-177">若要添加其他条件，请单击" **添加条件** "，然后选择"应用的条件" **下的其余值**。</span><span class="sxs-lookup"><span data-stu-id="2d963-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="2d963-178">若要添加例外，请单击 **"添加条件** "，然后选择"例外" **下的例外**。</span><span class="sxs-lookup"><span data-stu-id="2d963-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="2d963-179">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="2d963-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="2d963-180">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="2d963-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="2d963-181">在 **出现的"查看设置** "页上，查看设置。</span><span class="sxs-lookup"><span data-stu-id="2d963-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="2d963-182">可以单击 **每个设置** 上的"编辑"来修改它。</span><span class="sxs-lookup"><span data-stu-id="2d963-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="2d963-183">完成后，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="2d963-183">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="2d963-184">使用安全&中心查看安全附件策略</span><span class="sxs-lookup"><span data-stu-id="2d963-184">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="2d963-185">在安全&中心，转到 **"威胁管理** \> **策略** \> **ATP 安全附件"。**</span><span class="sxs-lookup"><span data-stu-id="2d963-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="2d963-186">在 **"安全附件** "页上，从列表中选择一个策略， (选中该策略，) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-186">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="2d963-187">策略详细信息以飞出方式显示</span><span class="sxs-lookup"><span data-stu-id="2d963-187">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="2d963-188">使用安全&中心修改安全附件策略</span><span class="sxs-lookup"><span data-stu-id="2d963-188">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="2d963-189">在安全&中心，转到 **"威胁管理** \> **策略** \> **ATP 安全附件"。**</span><span class="sxs-lookup"><span data-stu-id="2d963-189">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="2d963-190">在 **"安全附件** "页上，从列表中选择一个策略， (选中该策略，) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-190">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="2d963-191">在出现的策略详细信息飞出中，单击 **"编辑策略"。**</span><span class="sxs-lookup"><span data-stu-id="2d963-191">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="2d963-192">在飞出中显示可用的设置与"使用安全与合规中心创建安全附件&部分中 [介绍的设置相同](#use-the-security--compliance-center-to-create-safe-attachments-policies) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-192">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="2d963-193">若要启用或禁用策略或设置策略优先级顺序，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="2d963-193">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="2d963-194">启用或禁用安全附件策略</span><span class="sxs-lookup"><span data-stu-id="2d963-194">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="2d963-195">在安全&中心，转到 **"威胁管理** \> **策略** \> **ATP 安全附件"。**</span><span class="sxs-lookup"><span data-stu-id="2d963-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="2d963-196">请注意" **状态"列中** 的值：</span><span class="sxs-lookup"><span data-stu-id="2d963-196">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="2d963-197">将切换开关向左移动</span><span class="sxs-lookup"><span data-stu-id="2d963-197">Move the toggle to the left</span></span> ![关闭策略](../../media/scc-toggle-off.png) <span data-ttu-id="2d963-199">以禁用策略。</span><span class="sxs-lookup"><span data-stu-id="2d963-199">to disable the policy.</span></span>

   - <span data-ttu-id="2d963-200">将开关向右移动</span><span class="sxs-lookup"><span data-stu-id="2d963-200">Move the toggle to the right</span></span> ![打开策略](../../media/scc-toggle-on.png) <span data-ttu-id="2d963-202">以启用策略。</span><span class="sxs-lookup"><span data-stu-id="2d963-202">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="2d963-203">设置安全附件策略的优先级</span><span class="sxs-lookup"><span data-stu-id="2d963-203">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="2d963-204">默认情况下，安全附件策略的优先级基于它们在新策略中创建的顺序 (策略的优先级低于旧策略) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-204">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="2d963-205">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="2d963-205">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="2d963-206">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="2d963-206">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="2d963-207">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="2d963-207">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="2d963-208">安全附件策略按处理策略的顺序显示 (优先级值为 0) 。 </span><span class="sxs-lookup"><span data-stu-id="2d963-208">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="2d963-209">**注意**：在安全&合规中心，只能在创建安全附件策略后更改该策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="2d963-209">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="2d963-210">在 PowerShell 中，可以在创建可影响现有规则优先级的安全附件规则 (替代默认优先级) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-210">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="2d963-211">若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。</span><span class="sxs-lookup"><span data-stu-id="2d963-211">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="2d963-212">在安全&中心，转到 **"威胁管理** \> **策略** \> **ATP 安全附件"。**</span><span class="sxs-lookup"><span data-stu-id="2d963-212">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="2d963-213">在 **"安全附件** "页上，从列表中选择一个策略， (选中该策略，) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-213">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="2d963-214">在出现的策略详细信息飞出中，单击可用的优先级按钮。</span><span class="sxs-lookup"><span data-stu-id="2d963-214">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="2d963-215">优先级值为 **0** **的安全附件** 策略仅提供"**减少优先级"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="2d963-215">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="2d963-216">优先级值最低的安全附件策略 (例如 **，3**) 只有"增加优先级 **"按钮** 可用。</span><span class="sxs-lookup"><span data-stu-id="2d963-216">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="2d963-217">如果你有三个或多个安全附件策略，则最高优先级和最低优先级值之间的策略同时具有"增加 **优先级** "和" **减少优先级"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="2d963-217">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="2d963-218">单击 **"增加优先级** " **或"降低优先级** "可更改 **"优先级"** 值。</span><span class="sxs-lookup"><span data-stu-id="2d963-218">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="2d963-219">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="2d963-219">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="2d963-220">使用安全&中心删除安全附件策略</span><span class="sxs-lookup"><span data-stu-id="2d963-220">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="2d963-221">在安全&中心，转到 **"威胁管理** \> **策略** \> **ATP 安全附件"。**</span><span class="sxs-lookup"><span data-stu-id="2d963-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="2d963-222">在 **"安全附件** "页上，从列表中选择一个策略， (选中该策略，) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-222">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="2d963-223">在出现的策略详细信息飞出中，单击"删除策略"，然后在出现的警告对话框中单击"是"。</span><span class="sxs-lookup"><span data-stu-id="2d963-223">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="2d963-224">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全附件策略</span><span class="sxs-lookup"><span data-stu-id="2d963-224">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="2d963-225">如前所述，安全附件策略由安全附件策略和安全附件规则组成。</span><span class="sxs-lookup"><span data-stu-id="2d963-225">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="2d963-226">在 PowerShell 中，安全附件策略和安全附件规则的区别很明显。</span><span class="sxs-lookup"><span data-stu-id="2d963-226">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="2d963-227">您可以使用 **\* -SafeAttachmentPolicy** cmdlet 管理安全附件策略，然后使用 **\* -SafeAttachmentRule** cmdlet 管理安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="2d963-227">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="2d963-228">在 PowerShell 中，首先创建安全附件策略，然后创建安全附件规则，以标识该规则所适用的策略。</span><span class="sxs-lookup"><span data-stu-id="2d963-228">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="2d963-229">在 PowerShell 中，分别修改安全附件策略和安全附件规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="2d963-229">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="2d963-230">从 PowerShell 删除安全附件策略时，不会自动删除相应的安全附件规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="2d963-230">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="2d963-231">使用 PowerShell 创建安全附件策略</span><span class="sxs-lookup"><span data-stu-id="2d963-231">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="2d963-232">在 PowerShell 中创建安全附件策略的过程分两步完成：</span><span class="sxs-lookup"><span data-stu-id="2d963-232">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="2d963-233">创建安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="2d963-233">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="2d963-234">创建指定规则所适用的安全附件策略的安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="2d963-234">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="2d963-235">**注意**：</span><span class="sxs-lookup"><span data-stu-id="2d963-235">**Notes**:</span></span>

- <span data-ttu-id="2d963-236">你可以创建新的安全附件规则，并为其分配现有的未关联的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="2d963-236">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="2d963-237">安全附件规则不能与多个安全附件策略关联。</span><span class="sxs-lookup"><span data-stu-id="2d963-237">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="2d963-238">可以在 PowerShell 中的新安全附件策略上配置以下设置，这些策略在创建策略之前&安全与合规中心内不可用：</span><span class="sxs-lookup"><span data-stu-id="2d963-238">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="2d963-239">在 `$false` **New-SafeAttachmentRule** cmdlet (上创建禁用的新) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-239">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="2d963-240">在 _\<Number\>_ **New-SafeAttachmentRule** cmdlet (设置策略) 优先级) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-240">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="2d963-241">在 PowerShell 中创建的新安全附件策略在安全与合规中心&，除非将策略分配给安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="2d963-241">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="2d963-242">步骤 1：使用 PowerShell 创建安全附件策略</span><span class="sxs-lookup"><span data-stu-id="2d963-242">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="2d963-243">若要创建安全附件策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2d963-243">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="2d963-244">此示例创建一个名为 Contoso All 的安全附件策略，并具有以下值：</span><span class="sxs-lookup"><span data-stu-id="2d963-244">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="2d963-245">阻止通过安全文档扫描发现包含恶意软件的邮件 (我们未使用 _Action_ 参数，并且默认值为 `Block`) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-245">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="2d963-246">启用重定向，并且发现包含恶意软件的邮件将发送到sec-ops@contoso.com进行分析和调查。</span><span class="sxs-lookup"><span data-stu-id="2d963-246">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="2d963-247">如果安全附件扫描不可用或遇到错误，请不要传递 (因为我们没有使用 _ActionOnError_ 参数，并且默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-247">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="2d963-248">有关语法和参数的详细信息，请参阅 [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="2d963-248">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="2d963-249">步骤 2：使用 PowerShell 创建安全附件规则</span><span class="sxs-lookup"><span data-stu-id="2d963-249">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="2d963-250">若要创建安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2d963-250">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="2d963-251">本示例创建一个名为"Contoso All"的安全附件规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="2d963-251">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="2d963-252">该规则与名为 Contoso All 的安全附件策略相关联。</span><span class="sxs-lookup"><span data-stu-id="2d963-252">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="2d963-253">该规则适用于域域中contoso.com收件人。</span><span class="sxs-lookup"><span data-stu-id="2d963-253">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="2d963-254">因为我们没有使用 _Priority_ 参数，所以使用默认优先级。</span><span class="sxs-lookup"><span data-stu-id="2d963-254">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="2d963-255">如果规则 (Enabled 参数，则启用该规则，默认值为 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-255">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="2d963-256">有关语法和参数的详细信息，请参阅[New-SafeAttachmentRule。](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="2d963-256">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="2d963-257">使用 PowerShell 查看安全附件策略</span><span class="sxs-lookup"><span data-stu-id="2d963-257">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="2d963-258">若要查看现有安全附件策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2d963-258">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="2d963-259">本示例返回所有安全附件策略的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="2d963-259">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="2d963-260">此示例返回名为 Contoso Executives 的安全附件策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2d963-260">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="2d963-261">有关语法和参数的详细信息，请参阅[Get-SafeAttachmentPolicy。](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="2d963-261">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="2d963-262">使用 PowerShell 查看安全附件规则</span><span class="sxs-lookup"><span data-stu-id="2d963-262">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="2d963-263">若要查看现有安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2d963-263">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="2d963-264">本示例返回所有安全附件规则的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="2d963-264">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="2d963-265">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2d963-265">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="2d963-266">本示例返回名为 Contoso Executives 的安全附件规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2d963-266">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="2d963-267">有关语法和参数的详细信息，请参阅[Get-SafeAttachmentRule。](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="2d963-267">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="2d963-268">使用 PowerShell 修改安全附件策略</span><span class="sxs-lookup"><span data-stu-id="2d963-268">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="2d963-269">如果 **Set-SafeAttachmentPolicy** cmdlet 没有 Name 参数，则 (_PowerShell_ 中重命名安全附件) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-269">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="2d963-270">在安全与合规中心内重命名安全&策略时，你仅重命名安全附件 _规则_。</span><span class="sxs-lookup"><span data-stu-id="2d963-270">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="2d963-271">否则，当您创建安全附件策略时，可以使用如本文前面步骤 1 中所述的相同设置：使用 [PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) 创建安全附件策略部分。</span><span class="sxs-lookup"><span data-stu-id="2d963-271">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="2d963-272">若要修改安全附件策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2d963-272">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="2d963-273">有关语法和参数的详细信息，请参阅 [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="2d963-273">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="2d963-274">使用 PowerShell 修改安全附件规则</span><span class="sxs-lookup"><span data-stu-id="2d963-274">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="2d963-275">在 PowerShell 中修改安全附件规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。</span><span class="sxs-lookup"><span data-stu-id="2d963-275">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="2d963-276">若要启用或禁用现有安全附件规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="2d963-276">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="2d963-277">否则，当您创建规则时，如本文前面所述的步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) 创建安全附件规则部分，这些设置也可用。</span><span class="sxs-lookup"><span data-stu-id="2d963-277">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="2d963-278">若要修改安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2d963-278">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="2d963-279">有关语法和参数的详细信息，请参阅[Set-SafeAttachmentRule。](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="2d963-279">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="2d963-280">使用 PowerShell 启用或禁用安全附件规则</span><span class="sxs-lookup"><span data-stu-id="2d963-280">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="2d963-281">在 PowerShell 中启用或禁用安全附件规则可启用或禁用整个安全附件 (安全附件策略和分配的安全附件策略) 。</span><span class="sxs-lookup"><span data-stu-id="2d963-281">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="2d963-282">若要在 PowerShell 中启用或禁用安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2d963-282">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="2d963-283">本示例禁用名为"Marketing Department"的安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="2d963-283">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="2d963-284">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="2d963-284">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="2d963-285">有关语法和参数的详细信息，请参阅[Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule)和[Disable-SafeAttachmentRule。](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="2d963-285">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="2d963-286">使用 PowerShell 设置安全附件规则的优先级</span><span class="sxs-lookup"><span data-stu-id="2d963-286">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="2d963-287">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="2d963-287">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="2d963-288">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="2d963-288">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="2d963-289">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="2d963-289">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="2d963-290">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="2d963-290">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="2d963-291">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="2d963-291">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="2d963-292">若要在 PowerShell 中设置安全附件规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2d963-292">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="2d963-293">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="2d963-293">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="2d963-294">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="2d963-294">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="2d963-295">**注意**：若要在创建新规则时设置规则的优先级，请改为对 **New-SafeAttachmentRule** cmdlet 使用 _Priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="2d963-295">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="2d963-296">有关语法和参数的详细信息，请参阅[Set-SafeAttachmentRule。](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="2d963-296">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="2d963-297">使用 PowerShell 删除安全附件策略</span><span class="sxs-lookup"><span data-stu-id="2d963-297">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="2d963-298">使用 PowerShell 删除安全附件策略时，不会删除相应的安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="2d963-298">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="2d963-299">若要在 PowerShell 中删除安全附件策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2d963-299">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="2d963-300">本示例删除名为"Marketing Department"的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="2d963-300">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="2d963-301">有关语法和参数的详细信息，请参阅 [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="2d963-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="2d963-302">使用 PowerShell 删除安全附件规则</span><span class="sxs-lookup"><span data-stu-id="2d963-302">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="2d963-303">使用 PowerShell 删除安全附件规则时，不会删除相应的安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="2d963-303">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="2d963-304">若要在 PowerShell 中删除安全附件规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2d963-304">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="2d963-305">本示例删除名为"Marketing Department"的安全附件规则。</span><span class="sxs-lookup"><span data-stu-id="2d963-305">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="2d963-306">有关语法和参数的详细信息，请参阅[Remove-SafeAttachmentRule。](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="2d963-306">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="2d963-307">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="2d963-307">How do you know these procedures worked?</span></span>

<span data-ttu-id="2d963-308">若要验证您是否已成功创建、修改或删除安全附件策略，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="2d963-308">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="2d963-309">在安全&中心，转到 **"威胁管理** \> **策略** \> **ATP 安全附件"。**</span><span class="sxs-lookup"><span data-stu-id="2d963-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="2d963-310">验证策略列表、其 **状态** 值及其 **优先级** 值。</span><span class="sxs-lookup"><span data-stu-id="2d963-310">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="2d963-311">若要查看更多详细信息，请从列表中选择策略，然后查看飞出中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2d963-311">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="2d963-312">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，替换为策略或规则的名称，运行以下命令并 \<Name\> 验证设置：</span><span class="sxs-lookup"><span data-stu-id="2d963-312">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="2d963-313">若要验证安全附件是否正在扫描邮件，请检查可用的 Defender for Office 365 报告。</span><span class="sxs-lookup"><span data-stu-id="2d963-313">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="2d963-314">有关详细信息，请参阅查看 [适用于 Office 365 的 Defender](view-reports-for-atp.md) 报告，以及使用安全与合规中心& [资源管理器](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="2d963-314">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
