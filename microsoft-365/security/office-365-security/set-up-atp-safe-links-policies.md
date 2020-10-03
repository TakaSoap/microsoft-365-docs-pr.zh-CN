---
title: 在 Office 365 ATP 中设置安全链接策略
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
description: 管理员可以了解如何在 Office 365 高级威胁防护 (ATP) 中查看、创建、修改和删除安全链接策略和全局安全链接设置。
ms.openlocfilehash: b6b013364fc763450ac8bef0d06bd2fad8d55daa
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350715"
---
# <a name="set-up-safe-links-policies-in-office-365-atp"></a><span data-ttu-id="a2094-103">在 Office 365 ATP 中设置安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a2094-103">Set up Safe Links policies in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="a2094-104">本文适用于拥有 [Office 365 高级威胁防护](office-365-atp.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="a2094-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="a2094-105">如果您是在 Outlook 中查找有关 Safelinks 的信息的家庭用户，请参阅 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="a2094-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="a2094-106">安全链接是 [Office 365 高级威胁防护 ](office-365-atp.md) 中的一项功能，它提供了在邮件流中对入站电子邮件进行 URL 扫描的 (ATP) ，以及单击电子邮件中的 url 和链接以及在其他位置的验证时间。</span><span class="sxs-lookup"><span data-stu-id="a2094-106">Safe Links is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="a2094-107">有关详细信息，请参阅 [Office 365 ATP 中的安全链接](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="a2094-107">For more information, see [Safe Links in Office 365 ATP](atp-safe-links.md).</span></span>

<span data-ttu-id="a2094-108">没有内置的或默认的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a2094-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="a2094-109">若要获取对 Url 的安全链接扫描，您需要创建一个或多个安全链接策略，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="a2094-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

<span data-ttu-id="a2094-110">您可以使用 Exchange Online 中的邮箱在安全 & 合规性中心或 PowerShell (Exchange Online PowerShell 中配置安全链接策略，以获取符合 Exchange Online 中邮箱的符合条件的 Microsoft 365 组织;独立 EOP PowerShell for 不含 Exchange Online 邮箱的组织，但使用 Office 365 ATP 附加订阅) 。</span><span class="sxs-lookup"><span data-stu-id="a2094-110">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

<span data-ttu-id="a2094-111">安全链接策略的基本元素为：</span><span class="sxs-lookup"><span data-stu-id="a2094-111">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="a2094-112">**安全链接策略**：启用 "安全链接保护"、"打开实时 URL 扫描"、"在传递邮件前是否等待实时扫描完成"、"为内部邮件启用扫描"、"指定是否跟踪用户单击" url，并指定是否允许用户单击 "trough" 以获取原始 URL。</span><span class="sxs-lookup"><span data-stu-id="a2094-112">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="a2094-113">**安全链接规则**：指定策略应用于) 的优先级和收件人筛选器 (。</span><span class="sxs-lookup"><span data-stu-id="a2094-113">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="a2094-114">当您在安全 & 合规中心中管理安全链接策略时，这两个元素之间的差异并不明显：</span><span class="sxs-lookup"><span data-stu-id="a2094-114">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="a2094-115">创建安全链接策略时，实际上是创建安全链接规则，同时为两者使用相同的名称创建关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a2094-115">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="a2094-116">修改安全链接策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="a2094-116">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="a2094-117">所有其他设置修改关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a2094-117">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="a2094-118">删除安全链接策略时，将删除安全链接规则和关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a2094-118">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="a2094-119">在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。</span><span class="sxs-lookup"><span data-stu-id="a2094-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="a2094-120">有关详细信息，请参阅本文后面的 [使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全链接策略](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 一节。</span><span class="sxs-lookup"><span data-stu-id="a2094-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="a2094-121">您可以在安全链接策略 **之外** 为安全链接保护配置全局设置。</span><span class="sxs-lookup"><span data-stu-id="a2094-121">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="a2094-122">有关说明，请参阅 [在 Office 365 ATP 中配置安全链接的全局设置](configure-global-settings-for-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="a2094-122">For instructions, see [Configure global settings for Safe Links in Office 365 ATP](configure-global-settings-for-safe-links.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a2094-123">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="a2094-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a2094-124">安全与合规中心的打开网址为 <https://protection.office.com/>。</span><span class="sxs-lookup"><span data-stu-id="a2094-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a2094-125">若要直接转到 " **ATP 安全链接** " 页面，请使用 <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="a2094-125">To go directly to the **ATP Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="a2094-126">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a2094-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a2094-127">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a2094-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a2094-128">若要查看、创建、修改和删除安全链接策略，您必须是下列角色组之一的成员：</span><span class="sxs-lookup"><span data-stu-id="a2094-128">To view, create, modify, and delete Safe Links policies, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="a2094-129">[安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。</span><span class="sxs-lookup"><span data-stu-id="a2094-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="a2094-130">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的**组织管理**。</span><span class="sxs-lookup"><span data-stu-id="a2094-130">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="a2094-131">有关安全链接策略的推荐设置，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="a2094-131">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="a2094-132">允许使用最长30分钟的时间来应用新的或更新的策略。</span><span class="sxs-lookup"><span data-stu-id="a2094-132">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="a2094-133">[将新功能连续添加到 ATP](office-365-atp.md#new-features-in-office-365-atp)。</span><span class="sxs-lookup"><span data-stu-id="a2094-133">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="a2094-134">添加新功能时，您可能需要对现有安全链接策略进行调整。</span><span class="sxs-lookup"><span data-stu-id="a2094-134">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="a2094-135">使用安全 & 合规中心创建安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a2094-135">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="a2094-136">在安全 & 合规中心中创建自定义安全链接策略将同时为两者创建安全链接规则和关联的安全链接策略，同时使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="a2094-136">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="a2094-137">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="a2094-137">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a2094-138">在 " **安全链接** " 页上，单击 " **创建**"。</span><span class="sxs-lookup"><span data-stu-id="a2094-138">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="a2094-139">将打开 " **新建安全链接策略** " 向导。</span><span class="sxs-lookup"><span data-stu-id="a2094-139">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="a2094-140">在 " **命名策略** " 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a2094-140">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="a2094-141">**名称**：输入策略的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="a2094-141">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="a2094-142">**说明**：输入策略的可选说明。</span><span class="sxs-lookup"><span data-stu-id="a2094-142">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="a2094-143">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2094-143">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a2094-144">在出现的 " **设置** " 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a2094-144">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a2094-145">**选择邮件中未知的潜在恶意 url 的操作**：选择 **"打开"**。</span><span class="sxs-lookup"><span data-stu-id="a2094-145">**Select the action for unknown potentially malicious URLs in messages**: Select **On**.</span></span>

   - <span data-ttu-id="a2094-146">**选择邮件中未知的潜在恶意 url 的操作**：选择 **"开启"** 或 "保留 **默认值"** "已选中"。</span><span class="sxs-lookup"><span data-stu-id="a2094-146">**Select the action for unknown potentially malicious URLs in messages**: Select **On** or leave the default value **Off** selected.</span></span>

   - <span data-ttu-id="a2094-147">**对指向文件的可疑链接和链接应用实时 URL 扫描**：选择此设置可启用对电子邮件中的链接的实时扫描。</span><span class="sxs-lookup"><span data-stu-id="a2094-147">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="a2094-148">**等待 URL 扫描完成后再传递邮件**：选择此设置可等待实时 URL 扫描完成，然后再传递邮件。</span><span class="sxs-lookup"><span data-stu-id="a2094-148">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="a2094-149">**对在组织内发送的电子邮件应用安全链接**：选择此设置可将安全链接策略应用于内部发件人和内部收件人之间的邮件。</span><span class="sxs-lookup"><span data-stu-id="a2094-149">**Apply safe links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="a2094-150">不**跟踪用户单击**：将此设置保留为未选中状态，以启用跟踪用户单击电子邮件中的 url。</span><span class="sxs-lookup"><span data-stu-id="a2094-150">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="a2094-151">**不允许用户单击到原始 url**：选择此设置可阻止用户通过单击 [警告页面](atp-safe-links.md#warning-pages-from-safe-links)中的原始 url。</span><span class="sxs-lookup"><span data-stu-id="a2094-151">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="a2094-152">**请勿重写以下 url**：允许访问安全链接将阻止的指定 url。</span><span class="sxs-lookup"><span data-stu-id="a2094-152">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="a2094-153">在框中，键入所需的 URL 或值，然后单击</span><span class="sxs-lookup"><span data-stu-id="a2094-153">In the box, type the URL or value that you want, and then click</span></span> !["添加按钮" 图标](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="a2094-155">.</span><span class="sxs-lookup"><span data-stu-id="a2094-155">.</span></span>

     <span data-ttu-id="a2094-156">若要删除现有条目，请选择该条目，然后单击</span><span class="sxs-lookup"><span data-stu-id="a2094-156">To remove an existing entry, select it and then click</span></span> !["删除" 按钮图标](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="a2094-158">.</span><span class="sxs-lookup"><span data-stu-id="a2094-158">.</span></span>

     <span data-ttu-id="a2094-159">有关条目语法，请参阅 ["不重写以下 url" 列表中的 "输入语法](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)"。</span><span class="sxs-lookup"><span data-stu-id="a2094-159">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="a2094-160">有关这些设置的详细信息，请参阅 Microsoft 团队的 " [电子邮件安全链接设置](atp-safe-links.md#safe-links-settings-for-email-messages) " 和 " [安全链接设置](atp-safe-links.md#safe-links-settings-for-microsoft-teams)"。</span><span class="sxs-lookup"><span data-stu-id="a2094-160">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="a2094-161">有关标准策略设置和严格策略设置的建议值，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="a2094-161">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="a2094-162">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2094-162">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a2094-163">在显示的 " **应用于** " 页上，确定该策略应用于的内部收件人。</span><span class="sxs-lookup"><span data-stu-id="a2094-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="a2094-164">只能使用一次条件或例外，但可以为条件或例外指定多个值。</span><span class="sxs-lookup"><span data-stu-id="a2094-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="a2094-165">同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。</span><span class="sxs-lookup"><span data-stu-id="a2094-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a2094-166">不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。</span><span class="sxs-lookup"><span data-stu-id="a2094-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="a2094-167">单击 " **添加条件**"。</span><span class="sxs-lookup"><span data-stu-id="a2094-167">Click **Add a condition**.</span></span> <span data-ttu-id="a2094-168">在出现的下拉列表中，选择 " **应用**条件：</span><span class="sxs-lookup"><span data-stu-id="a2094-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="a2094-169">**收件人为**：指定组织中的一个或多个邮箱、邮件用户或邮件联系人。</span><span class="sxs-lookup"><span data-stu-id="a2094-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="a2094-170">**收件人是的成员**：指定组织中的一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="a2094-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="a2094-171">**收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。</span><span class="sxs-lookup"><span data-stu-id="a2094-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="a2094-172">选择条件后，将显示相应的下拉框，其中包含 **其中的任何** 框。</span><span class="sxs-lookup"><span data-stu-id="a2094-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="a2094-173">在框中单击并滚动到要选择的值列表。</span><span class="sxs-lookup"><span data-stu-id="a2094-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="a2094-174">在框中单击，然后开始键入以筛选列表并选择一个值。</span><span class="sxs-lookup"><span data-stu-id="a2094-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="a2094-175">若要添加其他值，请单击框中的空白区域。</span><span class="sxs-lookup"><span data-stu-id="a2094-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="a2094-176">若要删除单个条目， **Remove**请单击 ![ ](../../media/scc-remove-icon.png) 值上的 "删除删除" 图标。</span><span class="sxs-lookup"><span data-stu-id="a2094-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="a2094-177">若要删除整个条件，请**Remove**单击 ![ ](../../media/scc-remove-icon.png) 条件上的 "删除删除" 图标。</span><span class="sxs-lookup"><span data-stu-id="a2094-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="a2094-178">若要添加其他条件，请单击 " **添加条件** "，然后选择 " **应用于**" 下的其他值。</span><span class="sxs-lookup"><span data-stu-id="a2094-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="a2094-179">若要添加例外，请单击 " **添加条件** "，并在 " **除非**" 下选择例外。</span><span class="sxs-lookup"><span data-stu-id="a2094-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="a2094-180">设置和行为与条件完全相同。</span><span class="sxs-lookup"><span data-stu-id="a2094-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="a2094-181">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2094-181">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a2094-182">在显示的 " **查看您的设置** " 页上，查看您的设置。</span><span class="sxs-lookup"><span data-stu-id="a2094-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="a2094-183">您可以在每个设置上单击 " **编辑** " 以修改它。</span><span class="sxs-lookup"><span data-stu-id="a2094-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="a2094-184">完成后，单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="a2094-184">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="a2094-185">使用安全 & 合规中心查看安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a2094-185">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="a2094-186">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="a2094-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a2094-187">在 " **安全链接** " 页上，从列表中选择一个策略，然后单击该策略 (不选中复选框) "。</span><span class="sxs-lookup"><span data-stu-id="a2094-187">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="a2094-188">弹出时显示策略详细信息</span><span class="sxs-lookup"><span data-stu-id="a2094-188">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="a2094-189">使用安全 & 合规中心修改安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a2094-189">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="a2094-190">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="a2094-190">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a2094-191">在 " **安全链接** " 页上，从列表中选择一个策略，然后单击该策略 (不选中复选框) "。</span><span class="sxs-lookup"><span data-stu-id="a2094-191">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="a2094-192">在 "策略详细信息" 弹出显示，单击 " **编辑策略**"。</span><span class="sxs-lookup"><span data-stu-id="a2094-192">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="a2094-193">弹出的可用设置与 [使用 Security & 合规中心创建安全链接策略](#use-the-security--compliance-center-to-create-safe-links-policies) 一节中所述的相同。</span><span class="sxs-lookup"><span data-stu-id="a2094-193">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="a2094-194">若要启用或禁用策略或设置策略优先级顺序，请参阅以下各节。</span><span class="sxs-lookup"><span data-stu-id="a2094-194">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="a2094-195">启用或禁用安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a2094-195">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="a2094-196">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="a2094-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a2094-197">请注意 " **状态** " 列中的值：</span><span class="sxs-lookup"><span data-stu-id="a2094-197">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="a2094-198">将切换开关移动到左侧可禁用策略：</span><span class="sxs-lookup"><span data-stu-id="a2094-198">Move the toggle to the left to disable the policy:</span></span> ![关闭策略](../../media/scc-toggle-off.png)<span data-ttu-id="a2094-200">.</span><span class="sxs-lookup"><span data-stu-id="a2094-200">.</span></span>

   - <span data-ttu-id="a2094-201">将切换开关移动到右侧可启用策略：</span><span class="sxs-lookup"><span data-stu-id="a2094-201">Move the toggle to the right to enable the policy:</span></span> ![启用策略](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="a2094-203">.</span><span class="sxs-lookup"><span data-stu-id="a2094-203">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="a2094-204">设置安全链接策略的优先级</span><span class="sxs-lookup"><span data-stu-id="a2094-204">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="a2094-205">默认情况下，安全链接策略的优先级将根据其在 (较旧策略) 的创建顺序而得到的优先级。</span><span class="sxs-lookup"><span data-stu-id="a2094-205">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="a2094-206">低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。</span><span class="sxs-lookup"><span data-stu-id="a2094-206">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="a2094-207">没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。</span><span class="sxs-lookup"><span data-stu-id="a2094-207">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="a2094-208">有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="a2094-208">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="a2094-209">安全链接策略按其处理的顺序显示 (第一个策略的 **优先级** 值为 0) 。</span><span class="sxs-lookup"><span data-stu-id="a2094-209">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="a2094-210">**注意**：在安全 & 合规性中心中，您只能在创建安全链接策略之后更改其优先级。</span><span class="sxs-lookup"><span data-stu-id="a2094-210">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="a2094-211">在 PowerShell 中，您可以在创建安全链接规则时替代默认优先级， (这会影响现有规则) 的优先级。</span><span class="sxs-lookup"><span data-stu-id="a2094-211">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="a2094-212">若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。</span><span class="sxs-lookup"><span data-stu-id="a2094-212">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="a2094-213">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="a2094-213">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a2094-214">在 " **安全链接** " 页上，从列表中选择一个策略，然后单击该策略 (不选中复选框) "。</span><span class="sxs-lookup"><span data-stu-id="a2094-214">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="a2094-215">在 "策略详细信息" 弹出显示时，单击 "可用优先级" 按钮：</span><span class="sxs-lookup"><span data-stu-id="a2094-215">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="a2094-216">**优先级**值为**0**的安全链接策略仅有 "**降低优先级**" 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="a2094-216">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="a2094-217">具有最低 **优先级** 值的安全链接策略 (例如， **3**) 仅有 " **提高优先级** " 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="a2094-217">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="a2094-218">如果您具有三个或更多安全链接策略，则在最高和最低优先级值之间的策略将具有 " **增加优先级** " 和 " **降低优先级** " 按钮可用。</span><span class="sxs-lookup"><span data-stu-id="a2094-218">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="a2094-219">单击 " **提高优先级** " 或 " **降低优先级** " 以更改 **优先级** 值。</span><span class="sxs-lookup"><span data-stu-id="a2094-219">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="a2094-220">完成后，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2094-220">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="a2094-221">使用安全 & 合规性中心删除安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a2094-221">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="a2094-222">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="a2094-222">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a2094-223">在 " **安全链接** " 页上，从列表中选择一个策略，然后单击该策略 (不选中复选框) "。</span><span class="sxs-lookup"><span data-stu-id="a2094-223">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="a2094-224">在 "策略详细信息" 弹出显示的内容中，单击 " **删除策略**"，然后在出现的警告对话框中单击 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="a2094-224">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="a2094-225">使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a2094-225">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="a2094-226">如前面所述，安全链接策略由安全链接策略和安全链接规则组成。</span><span class="sxs-lookup"><span data-stu-id="a2094-226">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="a2094-227">在 PowerShell 中，安全链接策略和安全链接规则的区别显而易见。</span><span class="sxs-lookup"><span data-stu-id="a2094-227">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="a2094-228">您可以使用\*\* \* -SafeLinksPolicy\*\* cmdlet 管理安全链接策略，并使用\*\* \* -SafeLinksRule\*\* cmdlet 管理安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="a2094-228">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="a2094-229">在 PowerShell 中，首先创建安全链接策略，然后创建安全链接规则，以标识应用该规则的策略。</span><span class="sxs-lookup"><span data-stu-id="a2094-229">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="a2094-230">在 PowerShell 中，可以单独修改 "安全链接策略" 和 "安全链接" 规则中的设置。</span><span class="sxs-lookup"><span data-stu-id="a2094-230">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="a2094-231">从 PowerShell 中删除安全链接策略时，不会自动删除相应的安全链接规则，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a2094-231">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="a2094-232">使用 PowerShell 创建安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a2094-232">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="a2094-233">在 PowerShell 中创建安全链接策略的过程分为两个步骤：</span><span class="sxs-lookup"><span data-stu-id="a2094-233">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="a2094-234">创建安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a2094-234">Create the safe links policy.</span></span>
2. <span data-ttu-id="a2094-235">创建安全链接规则，该规则指定应用该规则的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a2094-235">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="a2094-236">**注意**：</span><span class="sxs-lookup"><span data-stu-id="a2094-236">**Notes**:</span></span>

- <span data-ttu-id="a2094-237">您可以创建新的安全链接规则，并向其分配现有的未关联的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a2094-237">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="a2094-238">安全链接规则不能与多个安全链接策略相关联。</span><span class="sxs-lookup"><span data-stu-id="a2094-238">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="a2094-239">您可以在 PowerShell 中的新 "安全链接策略" 中配置以下设置，这些设置在 "安全 & 合规性中心" 中不可用，直到您创建了策略：</span><span class="sxs-lookup"><span data-stu-id="a2094-239">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="a2094-240">将新策略创建为_Enabled_ `$false` **SafeLinksRule** cmdlet) 上启用的禁用 (。</span><span class="sxs-lookup"><span data-stu-id="a2094-240">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="a2094-241">在_Priority_ _\<Number\>_ **SafeLinksRule** Cmdlet) 上创建 (优先级) 时设置策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="a2094-241">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="a2094-242">在 PowerShell 中创建的新安全链接策略在安全 & 合规性中心中不可见，除非您将策略分配给安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="a2094-242">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="a2094-243">步骤1：使用 PowerShell 创建安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a2094-243">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="a2094-244">若要创建安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a2094-244">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="a2094-245">**注意**：</span><span class="sxs-lookup"><span data-stu-id="a2094-245">**Notes**:</span></span>

- <span data-ttu-id="a2094-246">有关用于 _DoNotRewriteUrls_ 参数的条目语法的详细信息，请参阅 ["不重写以下 url" 列表中的 "输入语法](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)"。</span><span class="sxs-lookup"><span data-stu-id="a2094-246">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="a2094-247">有关使用**SafeLinksPolicy** cmdlet 修改现有安全链接策略时可用于_DoNotRewriteUrls_参数的其他语法，请参阅本文后面的[使用 PowerShell 修改安全链接策略](#use-powershell-to-modify-safe-links-policies)一节。</span><span class="sxs-lookup"><span data-stu-id="a2094-247">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="a2094-248">本示例创建一个名为 "Contoso All" 的安全链接策略，其中包含以下值：</span><span class="sxs-lookup"><span data-stu-id="a2094-248">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="a2094-249">启用电子邮件中的 URL 扫描和重写。</span><span class="sxs-lookup"><span data-stu-id="a2094-249">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="a2094-250">打开 "团队中的 URL 扫描" (点击 "仅预览") 。</span><span class="sxs-lookup"><span data-stu-id="a2094-250">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="a2094-251">启用单击的 Url 的实时扫描，包括指向文件的单击链接。</span><span class="sxs-lookup"><span data-stu-id="a2094-251">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="a2094-252">等待 URL 扫描完成后再传递邮件。</span><span class="sxs-lookup"><span data-stu-id="a2094-252">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="a2094-253">启用内部邮件的 URL 扫描和重写。</span><span class="sxs-lookup"><span data-stu-id="a2094-253">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="a2094-254">跟踪与安全链接保护相关的用户单击 (我们不使用 _DoNotTrackUserClicks_ 参数，默认值为 $false，这意味着将) 跟踪用户单击。</span><span class="sxs-lookup"><span data-stu-id="a2094-254">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="a2094-255">不允许用户单击到原始 URL。</span><span class="sxs-lookup"><span data-stu-id="a2094-255">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="a2094-256">有关语法和参数的详细信息，请参阅 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="a2094-256">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="a2094-257">步骤2：使用 PowerShell 创建安全链接规则</span><span class="sxs-lookup"><span data-stu-id="a2094-257">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="a2094-258">若要创建安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a2094-258">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="a2094-259">本示例将创建一个名为 "Contoso All" 的安全链接规则，并满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="a2094-259">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="a2094-260">规则与名为 "Contoso All" 的安全链接策略相关联。</span><span class="sxs-lookup"><span data-stu-id="a2094-260">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="a2094-261">该规则应用于 contoso.com 域中的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="a2094-261">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="a2094-262">由于我们不使用 _Priority_ 参数，因此使用默认的优先级。</span><span class="sxs-lookup"><span data-stu-id="a2094-262">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="a2094-263"> (我们不使用 _enabled_ 参数，并且默认值为) ，则启用该规则 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="a2094-263">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="a2094-264">有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="a2094-264">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="a2094-265">使用 PowerShell 查看安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a2094-265">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="a2094-266">若要查看现有的安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a2094-266">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a2094-267">本示例返回所有安全链接策略的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="a2094-267">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="a2094-268">本示例返回名为 "Contoso 行政主管" 的安全链接策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a2094-268">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="a2094-269">有关语法和参数的详细信息，请参阅 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="a2094-269">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="a2094-270">使用 PowerShell 查看安全链接规则</span><span class="sxs-lookup"><span data-stu-id="a2094-270">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="a2094-271">若要查看现有安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a2094-271">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a2094-272">本示例返回所有安全链接规则的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="a2094-272">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="a2094-273">若要按已启用或已禁用规则筛选列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a2094-273">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="a2094-274">本示例返回名为 "Contoso 行政主管" 的安全链接规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a2094-274">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="a2094-275">有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="a2094-275">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="a2094-276">使用 PowerShell 修改安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a2094-276">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="a2094-277">无法重命名 (PowerShell 中的安全链接策略 **SafeLinksPolicy** Cmdlet 没有 _名称_ 参数) 。</span><span class="sxs-lookup"><span data-stu-id="a2094-277">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="a2094-278">重命名安全 & 合规性中心中的 "安全链接" 策略时，只是重命名安全链接 _规则_。</span><span class="sxs-lookup"><span data-stu-id="a2094-278">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="a2094-279">修改 PowerShell 中的安全链接策略的唯一另一个注意事项是 _DoNotRewriteUrls_ 参数的可用语法， (["不重写以下 url" 列表](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)) ：</span><span class="sxs-lookup"><span data-stu-id="a2094-279">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="a2094-280">若要添加将替换任何现有条目的值，请使用以下语法： `"Entry1","Entry2,..."EntryN"` 。</span><span class="sxs-lookup"><span data-stu-id="a2094-280">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="a2094-281">若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="a2094-281">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="a2094-282">否则，在创建安全链接策略时，可以使用相同的设置，如本文前面的 [步骤1：使用 PowerShell 创建安全链接策略](#step-1-use-powershell-to-create-a-safe-links-policy) 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="a2094-282">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="a2094-283">若要修改安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a2094-283">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="a2094-284">有关语法和参数的详细信息，请参阅 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="a2094-284">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="a2094-285">使用 PowerShell 修改安全链接规则</span><span class="sxs-lookup"><span data-stu-id="a2094-285">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="a2094-286">在 PowerShell 中修改安全链接规则时，唯一不可用的设置是允许您创建禁用规则的 _启用_ 参数。</span><span class="sxs-lookup"><span data-stu-id="a2094-286">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="a2094-287">若要启用或禁用现有安全链接规则，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="a2094-287">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="a2094-288">否则，在创建规则时，可以使用相同的设置，如本文前面的 [步骤2：使用 PowerShell 创建安全链接规则](#step-2-use-powershell-to-create-a-safe-links-rule) 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="a2094-288">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="a2094-289">若要修改安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a2094-289">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="a2094-290">有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="a2094-290">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="a2094-291">使用 PowerShell 启用或禁用安全链接规则</span><span class="sxs-lookup"><span data-stu-id="a2094-291">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="a2094-292">启用或禁用 PowerShell 中的安全链接规则可启用或禁用 "安全链接" 规则和 "分配的安全链接" 策略) 的整个安全链接策略 (。</span><span class="sxs-lookup"><span data-stu-id="a2094-292">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="a2094-293">若要在 PowerShell 中启用或禁用安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a2094-293">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="a2094-294">本示例禁用名为 "Marketing 部门" 的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="a2094-294">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="a2094-295">下面的示例启用同一规则。</span><span class="sxs-lookup"><span data-stu-id="a2094-295">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="a2094-296">有关语法和参数的详细信息，请参阅 [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) 和 [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="a2094-296">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="a2094-297">使用 PowerShell 设置安全链接规则的优先级</span><span class="sxs-lookup"><span data-stu-id="a2094-297">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="a2094-298">可以设置的规则最高优先级值是 0。</span><span class="sxs-lookup"><span data-stu-id="a2094-298">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="a2094-299">可以设置的最小优先级值取决于规则的数量。</span><span class="sxs-lookup"><span data-stu-id="a2094-299">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="a2094-300">例如，如果有五个规则，则可以使用的优先级值为 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="a2094-300">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="a2094-301">更改现有规则的优先级可对其他规则产生级联效应。</span><span class="sxs-lookup"><span data-stu-id="a2094-301">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="a2094-302">例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。</span><span class="sxs-lookup"><span data-stu-id="a2094-302">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="a2094-303">若要在 PowerShell 中设置安全链接规则的优先级，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a2094-303">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="a2094-304">下面的示例将名为“Marketing Department”的规则的优先级设置为 2。</span><span class="sxs-lookup"><span data-stu-id="a2094-304">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="a2094-305">优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。</span><span class="sxs-lookup"><span data-stu-id="a2094-305">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="a2094-306">**注意**：若要在创建新规则时设置其优先级，请改用**SafeLinksRule** cmdlet 上的_priority_参数。</span><span class="sxs-lookup"><span data-stu-id="a2094-306">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="a2094-307">有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="a2094-307">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="a2094-308">使用 PowerShell 删除安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a2094-308">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="a2094-309">当您使用 PowerShell 删除安全链接策略时，不会删除相应的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="a2094-309">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="a2094-310">若要删除 PowerShell 中的安全链接策略，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a2094-310">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="a2094-311">本示例将删除名为 "Marketing 部门" 的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a2094-311">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="a2094-312">有关语法和参数的详细信息，请参阅 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="a2094-312">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="a2094-313">使用 PowerShell 删除安全链接规则</span><span class="sxs-lookup"><span data-stu-id="a2094-313">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="a2094-314">当您使用 PowerShell 删除安全链接规则时，不会删除相应的安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a2094-314">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="a2094-315">若要删除 PowerShell 中的安全链接规则，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="a2094-315">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="a2094-316">本示例将删除名为 "Marketing 部门" 的安全链接规则。</span><span class="sxs-lookup"><span data-stu-id="a2094-316">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="a2094-317">有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="a2094-317">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="a2094-318">若要验证安全链接是否正在扫描邮件，请检查可用的高级威胁防护报告。</span><span class="sxs-lookup"><span data-stu-id="a2094-318">To verify that Safe Links is scanning messages, check the available Advanced Threat Protection reports.</span></span> <span data-ttu-id="a2094-319">有关详细信息，请参阅 [查看 Office 365 ATP 报告](view-reports-for-atp.md) 和 [使用安全 & 合规性中心中的资源管理器](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="a2094-319">For more information, see [View reports for Office 365 ATP](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="a2094-320">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="a2094-320">How do you know these procedures worked?</span></span>

<span data-ttu-id="a2094-321">若要验证是否已成功创建、修改或删除了安全链接策略，请执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="a2094-321">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="a2094-322">在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="a2094-322">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="a2094-323">验证策略列表、策略的 **状态** 值及其 **优先级** 值。</span><span class="sxs-lookup"><span data-stu-id="a2094-323">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="a2094-324">若要查看更多详细信息，请从列表中选择策略，并在 "飞出" 中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="a2094-324">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="a2094-325">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，将替换 \<Name\> 为策略或规则的名称，运行以下命令，并验证设置：</span><span class="sxs-lookup"><span data-stu-id="a2094-325">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
