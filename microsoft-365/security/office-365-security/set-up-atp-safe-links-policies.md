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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Microsoft Defender for Office 365 中查看、创建、修改和删除安全链接策略和全局安全链接设置。
ms.openlocfilehash: 550be48d5f1cae490c53c8f4a9fcedb0b9f21f73
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572713"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="bd093-103">在 Microsoft Defender for Office 365 中设置安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bd093-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="bd093-104">本文适用于拥有 [Microsoft Defender For Office 365](office-365-atp.md)的商业客户。</span><span class="sxs-lookup"><span data-stu-id="bd093-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="bd093-105">如果您是在 Outlook 中查找有关 Safelinks 的信息的家庭用户，请参阅 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="bd093-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="bd093-106">安全链接是 [Microsoft Defender For Office 365](office-365-atp.md) 中的一项功能，用于在邮件流中提供入站电子邮件的 URL 扫描，以及单击电子邮件中的 url 和链接以及在其他位置中进行验证的时间。</span><span class="sxs-lookup"><span data-stu-id="bd093-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="bd093-107">有关详细信息，请参阅 [Microsoft Defender For Office 365 中的安全链接](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="bd093-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="bd093-108">没有内置的或默认的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="bd093-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="bd093-109">若要获取对 Url 的安全链接扫描，您需要创建一个或多个安全链接策略，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="bd093-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

<span data-ttu-id="bd093-110">您可以使用 Exchange Online 中的邮箱在安全 & 合规性中心或 PowerShell (Exchange Online PowerShell 中配置安全链接策略，以获取符合 Exchange Online 中邮箱的符合条件的 Microsoft 365 组织;独立 EOP PowerShell for 不含 Exchange Online 邮箱的组织，但使用 Microsoft Defender for Office 365 附加订阅) 。</span><span class="sxs-lookup"><span data-stu-id="bd093-110">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="bd093-111">安全链接策略的基本元素为：</span><span class="sxs-lookup"><span data-stu-id="bd093-111">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="bd093-112">**安全链接策略**：启用 "安全链接保护"、"打开实时 URL 扫描"、"在传递邮件前是否等待实时扫描完成"、"为内部邮件启用扫描"、"指定是否跟踪用户单击" url，并指定是否允许用户单击 "trough" 以获取原始 URL。</span><span class="sxs-lookup"><span data-stu-id="bd093-112">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="bd093-113">**安全链接规则**：指定策略应用于) 的优先级和收件人筛选器 (。</span><span class="sxs-lookup"><span data-stu-id="bd093-113">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="bd093-114">当您在安全 & 合规中心中管理安全链接策略时，这两个元素之间的差异并不明显：</span><span class="sxs-lookup"><span data-stu-id="bd093-114">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="bd093-115">创建安全链接策略时，实际上是创建安全链接规则，同时为两者使用相同的名称创建关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="bd093-115">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="bd093-116">修改安全链接策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="bd093-116">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="bd093-117">所有其他设置修改关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="bd093-117">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="bd093-118">删除安全链接策略时，将删除安全链接规则和关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="bd093-118">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="bd093-119">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="bd093-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="bd093-120">有关详细信息，请参阅本文后面的 [使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全链接策略](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 一节。</span><span class="sxs-lookup"><span data-stu-id="bd093-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="bd093-121">您可以在安全链接策略 **之外** 为安全链接保护配置全局设置。</span><span class="sxs-lookup"><span data-stu-id="bd093-121">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="bd093-122">有关说明，请参阅 [在 Microsoft Defender For Office 365 中配置安全链接的全局设置](configure-global-settings-for-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="bd093-122">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bd093-123">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="bd093-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bd093-124">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="bd093-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="bd093-125">若要直接转到 " **安全链接** " 页面，请使用 <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="bd093-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="bd093-126">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bd093-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="bd093-127">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bd093-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="bd093-128">您需要在安全 & 合规性中心中分配权限，然后才能执行本文中的过程：</span><span class="sxs-lookup"><span data-stu-id="bd093-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="bd093-129">若要创建、修改和删除安全链接策略，您必须是 " **组织管理** " 或 " **安全管理员** " 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="bd093-129">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="bd093-130">若要对安全链接策略进行只读访问，您需要是 **全局读取器** 或 **安全读者** 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="bd093-130">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="bd093-131">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="bd093-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="bd093-132">**注意**：</span><span class="sxs-lookup"><span data-stu-id="bd093-132">**Notes**:</span></span>

  - <span data-ttu-id="bd093-133">将用户添加到 Microsoft 365 管理中心中对应的 Azure Active Directory 角色，用户可为用户提供安全 & 合规性中心的必需权限 _以及_ Microsoft 365 中其他功能的权限。</span><span class="sxs-lookup"><span data-stu-id="bd093-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="bd093-134">有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="bd093-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="bd093-135">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 "**仅查看组织管理**" 角色组也提供了对功能的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="bd093-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="bd093-136">有关安全链接策略的推荐设置，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="bd093-136">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="bd093-137">允许使用最长30分钟的时间来应用新的或更新的策略。</span><span class="sxs-lookup"><span data-stu-id="bd093-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="bd093-138">[新功能将不断添加到 Microsoft Defender For Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)中。</span><span class="sxs-lookup"><span data-stu-id="bd093-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="bd093-139">添加新功能时，您可能需要对现有安全链接策略进行调整。</span><span class="sxs-lookup"><span data-stu-id="bd093-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="bd093-140">使用安全 & 合规中心创建安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bd093-140">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="bd093-141">在安全 & 合规中心中创建自定义安全链接策略将同时为两者创建安全链接规则和关联的安全链接策略，同时使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="bd093-141">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="bd093-142">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="bd093-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="bd093-143">在 " **安全链接** " 页上，单击 " **创建**"。</span><span class="sxs-lookup"><span data-stu-id="bd093-143">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="bd093-144">将打开 " **新建安全链接策略** " 向导。</span><span class="sxs-lookup"><span data-stu-id="bd093-144">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="bd093-145">在 " **命名策略** " 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="bd093-145">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="bd093-146">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="bd093-146">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="bd093-147">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="bd093-147">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="bd093-148">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="bd093-148">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="bd093-149">在出现的 " **设置** " 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="bd093-149">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="bd093-150">**选择邮件中未知的潜在恶意 url 的操作**：选择 **"启用"** 以启用电子邮件中的链接的安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="bd093-150">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="bd093-151">**为 Microsoft 团队中的未知或可能存在的恶意 Url 选择操作**：选择 **"打开"** 以启用对团队中的链接的安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="bd093-151">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="bd093-152">**对指向文件的可疑链接和链接应用实时 URL 扫描**：选择此设置可启用对电子邮件中的链接的实时扫描。</span><span class="sxs-lookup"><span data-stu-id="bd093-152">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="bd093-153">**等待 URL 扫描完成后再传递邮件**：选择此设置可等待实时 URL 扫描完成，然后再传递邮件。</span><span class="sxs-lookup"><span data-stu-id="bd093-153">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="bd093-154">**对在组织内发送的电子邮件应用安全链接**：选择此设置可将安全链接策略应用于内部发件人和内部收件人之间的邮件。</span><span class="sxs-lookup"><span data-stu-id="bd093-154">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="bd093-155">不 **跟踪用户单击**：将此设置保留为未选中状态，以启用跟踪用户单击电子邮件中的 url。</span><span class="sxs-lookup"><span data-stu-id="bd093-155">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="bd093-156">**不允许用户单击到原始 url**：选择此设置可阻止用户通过单击 [警告页面](atp-safe-links.md#warning-pages-from-safe-links)中的原始 url。</span><span class="sxs-lookup"><span data-stu-id="bd093-156">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="bd093-157">**请勿重写以下 url**：允许访问安全链接将阻止的指定 url。</span><span class="sxs-lookup"><span data-stu-id="bd093-157">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="bd093-158">在框中，键入所需的 URL 或值，然后单击</span><span class="sxs-lookup"><span data-stu-id="bd093-158">In the box, type the URL or value that you want, and then click</span></span> !["添加按钮" 图标](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="bd093-160">.</span><span class="sxs-lookup"><span data-stu-id="bd093-160">.</span></span>

     <span data-ttu-id="bd093-161">若要删除现有条目，请选择该条目，然后单击</span><span class="sxs-lookup"><span data-stu-id="bd093-161">To remove an existing entry, select it and then click</span></span> !["删除" 按钮图标](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="bd093-163">.</span><span class="sxs-lookup"><span data-stu-id="bd093-163">.</span></span>

     <span data-ttu-id="bd093-164">有关条目语法，请参阅 ["不重写以下 url" 列表中的 "输入语法](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)"。</span><span class="sxs-lookup"><span data-stu-id="bd093-164">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="bd093-165">有关这些设置的详细信息，请参阅 Microsoft 团队的 " [电子邮件安全链接设置](atp-safe-links.md#safe-links-settings-for-email-messages) " 和 " [安全链接设置](atp-safe-links.md#safe-links-settings-for-microsoft-teams)"。</span><span class="sxs-lookup"><span data-stu-id="bd093-165">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="bd093-166">有关标准策略设置和严格策略设置的建议值，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="bd093-166">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="bd093-167">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="bd093-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="bd093-168">在显示的 " **应用于** " 页上，确定该策略应用于的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="bd093-168">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="bd093-169">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="bd093-169">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="bd093-170">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="bd093-170">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="bd093-171">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="bd093-171">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="bd093-172">单击 " **添加条件**"。</span><span class="sxs-lookup"><span data-stu-id="bd093-172">Click **Add a condition**.</span></span> <span data-ttu-id="bd093-173">在出现的下拉列表中，选择 " **应用** 条件：</span><span class="sxs-lookup"><span data-stu-id="bd093-173">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="bd093-174">**收件人为**：指定组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="bd093-174">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="bd093-175">**收件人是的成员**：指定组织中的一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="bd093-175">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="bd093-176">**收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="bd093-176">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="bd093-177">选择条件后，将显示相应的下拉框，其中包含 **其中的任何** 框。</span><span class="sxs-lookup"><span data-stu-id="bd093-177">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="bd093-178">在框中单击并滚动到要选择的值列表。</span><span class="sxs-lookup"><span data-stu-id="bd093-178">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="bd093-179">在框中单击，然后开始键入以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="bd093-179">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="bd093-180">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="bd093-180">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="bd093-181">若要删除单个条目， **Remove** 请单击 ![ ](../../media/scc-remove-icon.png) 值上的 "删除删除" 图标。</span><span class="sxs-lookup"><span data-stu-id="bd093-181">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="bd093-182">若要删除整个条件，请 **Remove** 单击 ![ ](../../media/scc-remove-icon.png) 条件上的 "删除删除" 图标。</span><span class="sxs-lookup"><span data-stu-id="bd093-182">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="bd093-183">若要添加其他条件，请单击 " **添加条件** "，然后选择 " **应用于**" 下的其他值。</span><span class="sxs-lookup"><span data-stu-id="bd093-183">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="bd093-184">若要添加例外，请单击 " **添加条件** "，并在 " **除非**" 下选择例外。</span><span class="sxs-lookup"><span data-stu-id="bd093-184">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="bd093-185">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="bd093-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="bd093-186">完成后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="bd093-186">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="bd093-187">在显示的 " **查看您的设置** " 页上，查看您的设置。</span><span class="sxs-lookup"><span data-stu-id="bd093-187">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="bd093-188">您可以在每个设置上单击 " **编辑** " 以修改它。</span><span class="sxs-lookup"><span data-stu-id="bd093-188">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="bd093-189">完成后，单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="bd093-189">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="bd093-190">使用安全 & 合规中心查看安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bd093-190">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="bd093-191">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="bd093-191">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="bd093-192">在 " **安全链接** " 页上，从列表中选择一个策略，然后单击该策略 (不选中复选框) "。</span><span class="sxs-lookup"><span data-stu-id="bd093-192">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="bd093-193">弹出时显示策略详细信息</span><span class="sxs-lookup"><span data-stu-id="bd093-193">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="bd093-194">使用安全 & 合规中心修改安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bd093-194">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="bd093-195">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="bd093-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="bd093-196">在 " **安全链接** " 页上，从列表中选择一个策略，然后单击该策略 (不选中复选框) "。</span><span class="sxs-lookup"><span data-stu-id="bd093-196">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="bd093-197">在 "策略详细信息" 弹出显示，单击 " **编辑策略**"。</span><span class="sxs-lookup"><span data-stu-id="bd093-197">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="bd093-198">弹出的可用设置与 [使用 Security & 合规中心创建安全链接策略](#use-the-security--compliance-center-to-create-safe-links-policies) 一节中所述的相同。</span><span class="sxs-lookup"><span data-stu-id="bd093-198">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="bd093-199">若要启用或禁用策略或设置策略优先级顺序，请参阅以下各节。</span><span class="sxs-lookup"><span data-stu-id="bd093-199">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="bd093-200">启用或禁用安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bd093-200">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="bd093-201">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="bd093-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="bd093-202">请注意 " **状态** " 列中的值：</span><span class="sxs-lookup"><span data-stu-id="bd093-202">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="bd093-203">将切换开关移动到左侧可禁用策略：</span><span class="sxs-lookup"><span data-stu-id="bd093-203">Move the toggle to the left to disable the policy:</span></span> ![关闭策略](../../media/scc-toggle-off.png)<span data-ttu-id="bd093-205">.</span><span class="sxs-lookup"><span data-stu-id="bd093-205">.</span></span>

   - <span data-ttu-id="bd093-206">将切换开关移动到右侧可启用策略：</span><span class="sxs-lookup"><span data-stu-id="bd093-206">Move the toggle to the right to enable the policy:</span></span> ![启用策略](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="bd093-208">.</span><span class="sxs-lookup"><span data-stu-id="bd093-208">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="bd093-209">设置安全链接策略的优先级</span><span class="sxs-lookup"><span data-stu-id="bd093-209">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="bd093-210">默认情况下，安全链接策略的优先级将根据其在 (较旧策略) 的创建顺序而得到的优先级。</span><span class="sxs-lookup"><span data-stu-id="bd093-210">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="bd093-211">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="bd093-211">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="bd093-212">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="bd093-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="bd093-213">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="bd093-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="bd093-214">安全链接策略按其处理的顺序显示 (第一个策略的 **优先级** 值为 0) 。</span><span class="sxs-lookup"><span data-stu-id="bd093-214">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="bd093-215">**注意**：在安全 & 合规性中心中，您只能在创建安全链接策略之后更改其优先级。</span><span class="sxs-lookup"><span data-stu-id="bd093-215">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="bd093-216">在 PowerShell 中，您可以在创建安全链接规则时替代默认优先级， (这会影响现有规则) 的优先级。</span><span class="sxs-lookup"><span data-stu-id="bd093-216">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="bd093-217">若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。</span><span class="sxs-lookup"><span data-stu-id="bd093-217">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="bd093-218">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="bd093-218">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="bd093-219">在 " **安全链接** " 页上，从列表中选择一个策略，然后单击该策略 (不选中复选框) "。</span><span class="sxs-lookup"><span data-stu-id="bd093-219">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="bd093-220">在 "策略详细信息" 弹出显示时，单击 "可用优先级" 按钮：</span><span class="sxs-lookup"><span data-stu-id="bd093-220">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="bd093-221">**优先级** 值为 **0** 的安全链接策略仅有 "**降低优先级**" 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="bd093-221">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="bd093-222">具有最低 **优先级** 值的安全链接策略 (例如， **3**) 仅有 " **提高优先级** " 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="bd093-222">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="bd093-223">如果您具有三个或更多安全链接策略，则在最高和最低优先级值之间的策略将具有 " **增加优先级** " 和 " **降低优先级** " 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="bd093-223">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="bd093-224">单击 " **提高优先级** " 或 " **降低优先级** " 以更改 **优先级** 值。</span><span class="sxs-lookup"><span data-stu-id="bd093-224">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="bd093-225">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="bd093-225">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="bd093-226">使用安全 & 合规性中心删除安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bd093-226">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="bd093-227">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="bd093-227">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="bd093-228">在 " **安全链接** " 页上，从列表中选择一个策略，然后单击该策略 (不选中复选框) "。</span><span class="sxs-lookup"><span data-stu-id="bd093-228">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="bd093-229">在 "策略详细信息" 弹出显示的内容中，单击 " **删除策略**"，然后在出现的警告对话框中单击 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="bd093-229">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="bd093-230">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bd093-230">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="bd093-231">如前面所述，安全链接策略由安全链接策略和安全链接规则组成。</span><span class="sxs-lookup"><span data-stu-id="bd093-231">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="bd093-232">在 PowerShell 中，安全链接策略和安全链接规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="bd093-232">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="bd093-233">您可以使用 **\* -SafeLinksPolicy** cmdlet 管理安全链接策略，并使用 **\* -SafeLinksRule** cmdlet 管理安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="bd093-233">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="bd093-234">在 PowerShell 中，首先创建安全链接策略，然后创建安全链接规则，以标识应用该规则的策略。</span><span class="sxs-lookup"><span data-stu-id="bd093-234">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="bd093-235">在 PowerShell 中，可以单独修改 "安全链接策略" 和 "安全链接" 规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="bd093-235">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="bd093-236">从 PowerShell 中删除安全链接策略时，不会自动删除相应的安全链接规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="bd093-236">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="bd093-237">使用 PowerShell 创建安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bd093-237">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="bd093-238">在 PowerShell 中创建安全链接策略的过程分为两个步骤：</span><span class="sxs-lookup"><span data-stu-id="bd093-238">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="bd093-239">创建安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="bd093-239">Create the safe links policy.</span></span>
2. <span data-ttu-id="bd093-240">创建安全链接规则，该规则指定应用该规则的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="bd093-240">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="bd093-241">**注意**：</span><span class="sxs-lookup"><span data-stu-id="bd093-241">**Notes**:</span></span>

- <span data-ttu-id="bd093-242">您可以创建新的安全链接规则，并向其分配现有的未关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="bd093-242">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="bd093-243">安全链接规则不能与多个安全链接策略相关联。</span><span class="sxs-lookup"><span data-stu-id="bd093-243">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="bd093-244">您可以在 PowerShell 中的新 "安全链接策略" 中配置以下设置，这些设置在 "安全 & 合规性中心" 中不可用，直到您创建了策略：</span><span class="sxs-lookup"><span data-stu-id="bd093-244">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="bd093-245">将新策略创建为 _Enabled_ `$false` **SafeLinksRule** cmdlet) 上启用的禁用 (。</span><span class="sxs-lookup"><span data-stu-id="bd093-245">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="bd093-246">在 _Priority_ _\<Number\>_ **SafeLinksRule** Cmdlet) 上创建 (优先级) 时设置策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="bd093-246">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="bd093-247">在 PowerShell 中创建的新安全链接策略在安全 & 合规性中心中不可见，除非您将策略分配给安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="bd093-247">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="bd093-248">步骤1：使用 PowerShell 创建安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bd093-248">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="bd093-249">若要创建安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bd093-249">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="bd093-250">**注意**：</span><span class="sxs-lookup"><span data-stu-id="bd093-250">**Notes**:</span></span>

- <span data-ttu-id="bd093-251">有关用于 _DoNotRewriteUrls_ 参数的条目语法的详细信息，请参阅 ["不重写以下 url" 列表中的 "输入语法](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)"。</span><span class="sxs-lookup"><span data-stu-id="bd093-251">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="bd093-252">有关使用 **SafeLinksPolicy** cmdlet 修改现有安全链接策略时可用于 _DoNotRewriteUrls_ 参数的其他语法，请参阅本文后面的 [使用 PowerShell 修改安全链接策略](#use-powershell-to-modify-safe-links-policies)一节。</span><span class="sxs-lookup"><span data-stu-id="bd093-252">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="bd093-253">本示例创建一个名为 "Contoso All" 的安全链接策略，其中包含以下值：</span><span class="sxs-lookup"><span data-stu-id="bd093-253">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="bd093-254">启用电子邮件中的 URL 扫描和重写。</span><span class="sxs-lookup"><span data-stu-id="bd093-254">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="bd093-255">打开 "团队中的 URL 扫描" (点击 "仅预览") 。</span><span class="sxs-lookup"><span data-stu-id="bd093-255">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="bd093-256">启用单击的 Url 的实时扫描，包括指向文件的单击链接。</span><span class="sxs-lookup"><span data-stu-id="bd093-256">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="bd093-257">等待 URL 扫描完成后再传递邮件。</span><span class="sxs-lookup"><span data-stu-id="bd093-257">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="bd093-258">启用内部邮件的 URL 扫描和重写。</span><span class="sxs-lookup"><span data-stu-id="bd093-258">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="bd093-259">跟踪与安全链接保护相关的用户单击 (我们不使用 _DoNotTrackUserClicks_ 参数，默认值为 $false，这意味着将) 跟踪用户单击。</span><span class="sxs-lookup"><span data-stu-id="bd093-259">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="bd093-260">不允许用户单击到原始 URL。</span><span class="sxs-lookup"><span data-stu-id="bd093-260">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="bd093-261">有关语法和参数的详细信息，请参阅 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="bd093-261">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="bd093-262">步骤2：使用 PowerShell 创建安全链接规则</span><span class="sxs-lookup"><span data-stu-id="bd093-262">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="bd093-263">若要创建安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bd093-263">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="bd093-264">本示例将创建一个名为 "Contoso All" 的安全链接规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="bd093-264">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="bd093-265">规则与名为 "Contoso All" 的安全链接策略相关联。</span><span class="sxs-lookup"><span data-stu-id="bd093-265">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="bd093-266">该规则应用于 contoso.com 域中的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="bd093-266">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="bd093-267">由于我们不使用 _Priority_ 参数，因此使用默认的优先级。</span><span class="sxs-lookup"><span data-stu-id="bd093-267">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="bd093-268"> (我们不使用 _enabled_ 参数，并且默认值为) ，则启用该规则 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="bd093-268">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="bd093-269">有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bd093-269">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="bd093-270">使用 PowerShell 查看安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bd093-270">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="bd093-271">若要查看现有的安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bd093-271">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="bd093-272">本示例返回所有安全链接策略的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="bd093-272">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="bd093-273">本示例返回名为 "Contoso 行政主管" 的安全链接策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bd093-273">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="bd093-274">有关语法和参数的详细信息，请参阅 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="bd093-274">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="bd093-275">使用 PowerShell 查看安全链接规则</span><span class="sxs-lookup"><span data-stu-id="bd093-275">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="bd093-276">若要查看现有安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bd093-276">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="bd093-277">本示例返回所有安全链接规则的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="bd093-277">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="bd093-278">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bd093-278">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="bd093-279">本示例返回名为 "Contoso 行政主管" 的安全链接规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bd093-279">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="bd093-280">有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bd093-280">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="bd093-281">使用 PowerShell 修改安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bd093-281">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="bd093-282">无法重命名 (PowerShell 中的安全链接策略 **SafeLinksPolicy** Cmdlet 没有 _名称_ 参数) 。</span><span class="sxs-lookup"><span data-stu-id="bd093-282">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="bd093-283">重命名安全 & 合规性中心中的 "安全链接" 策略时，只是重命名安全链接 _规则_。</span><span class="sxs-lookup"><span data-stu-id="bd093-283">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="bd093-284">修改 PowerShell 中的安全链接策略的唯一另一个注意事项是 _DoNotRewriteUrls_ 参数的可用语法， (["不重写以下 url" 列表](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)) ：</span><span class="sxs-lookup"><span data-stu-id="bd093-284">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="bd093-285">若要添加将替换任何现有条目的值，请使用以下语法： `"Entry1","Entry2,..."EntryN"` 。</span><span class="sxs-lookup"><span data-stu-id="bd093-285">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="bd093-286">若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="bd093-286">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="bd093-287">否则，在创建安全链接策略时，可以使用相同的设置，如本文前面的 [步骤1：使用 PowerShell 创建安全链接策略](#step-1-use-powershell-to-create-a-safe-links-policy) 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="bd093-287">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="bd093-288">若要修改安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bd093-288">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="bd093-289">有关语法和参数的详细信息，请参阅 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="bd093-289">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="bd093-290">使用 PowerShell 修改安全链接规则</span><span class="sxs-lookup"><span data-stu-id="bd093-290">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="bd093-291">在 PowerShell 中修改安全链接规则时，唯一不可用的设置是允许您创建禁用规则的 _启用_ 参数。</span><span class="sxs-lookup"><span data-stu-id="bd093-291">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="bd093-292">若要启用或禁用现有安全链接规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="bd093-292">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="bd093-293">否则，在创建规则时，可以使用相同的设置，如本文前面的 [步骤2：使用 PowerShell 创建安全链接规则](#step-2-use-powershell-to-create-a-safe-links-rule) 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="bd093-293">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="bd093-294">若要修改安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bd093-294">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="bd093-295">有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bd093-295">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="bd093-296">使用 PowerShell 启用或禁用安全链接规则</span><span class="sxs-lookup"><span data-stu-id="bd093-296">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="bd093-297">启用或禁用 PowerShell 中的安全链接规则可启用或禁用 "安全链接" 规则和 "分配的安全链接" 策略) 的整个安全链接策略 (。</span><span class="sxs-lookup"><span data-stu-id="bd093-297">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="bd093-298">若要在 PowerShell 中启用或禁用安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bd093-298">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="bd093-299">本示例禁用名为 "Marketing 部门" 的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="bd093-299">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="bd093-300">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="bd093-300">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="bd093-301">有关语法和参数的详细信息，请参阅 [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) 和 [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bd093-301">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="bd093-302">使用 PowerShell 设置安全链接规则的优先级</span><span class="sxs-lookup"><span data-stu-id="bd093-302">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="bd093-303">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="bd093-303">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="bd093-304">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="bd093-304">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="bd093-305">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="bd093-305">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="bd093-306">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="bd093-306">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="bd093-307">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="bd093-307">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="bd093-308">若要在 PowerShell 中设置安全链接规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bd093-308">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="bd093-309">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="bd093-309">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="bd093-310">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="bd093-310">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="bd093-311">**注意**：若要在创建新规则时设置其优先级，请改用 **SafeLinksRule** cmdlet 上的 _priority_ 参数。</span><span class="sxs-lookup"><span data-stu-id="bd093-311">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="bd093-312">有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bd093-312">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="bd093-313">使用 PowerShell 删除安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bd093-313">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="bd093-314">当您使用 PowerShell 删除安全链接策略时，不会删除相应的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="bd093-314">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="bd093-315">若要删除 PowerShell 中的安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bd093-315">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="bd093-316">本示例将删除名为 "Marketing 部门" 的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="bd093-316">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="bd093-317">有关语法和参数的详细信息，请参阅 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="bd093-317">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="bd093-318">使用 PowerShell 删除安全链接规则</span><span class="sxs-lookup"><span data-stu-id="bd093-318">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="bd093-319">当您使用 PowerShell 删除安全链接规则时，不会删除相应的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="bd093-319">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="bd093-320">若要删除 PowerShell 中的安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bd093-320">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="bd093-321">本示例将删除名为 "Marketing 部门" 的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="bd093-321">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="bd093-322">有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bd093-322">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="bd093-323">若要验证安全链接是否正在扫描邮件，请查看可用的 Microsoft Defender for Office 365 报告。</span><span class="sxs-lookup"><span data-stu-id="bd093-323">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="bd093-324">有关详细信息，请参阅 [查看适用于 Office 365 的 Defender 报告](view-reports-for-atp.md) 和 [使用安全 & 合规性中心中的资源管理器](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="bd093-324">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="bd093-325">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="bd093-325">How do you know these procedures worked?</span></span>

<span data-ttu-id="bd093-326">若要验证是否已成功创建、修改或删除了安全链接策略，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="bd093-326">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="bd093-327">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="bd093-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="bd093-328">验证策略列表、策略的 **状态** 值及其 **优先级** 值。</span><span class="sxs-lookup"><span data-stu-id="bd093-328">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="bd093-329">若要查看更多详细信息，请从列表中选择策略，并在 "飞出" 中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="bd093-329">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="bd093-330">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，将替换 \<Name\> 为策略或规则的名称，运行以下命令，并验证设置：</span><span class="sxs-lookup"><span data-stu-id="bd093-330">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
