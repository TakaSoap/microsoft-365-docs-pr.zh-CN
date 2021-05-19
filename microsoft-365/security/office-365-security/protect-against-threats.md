---
title: 抵御威胁
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以在 Microsoft 365 中学习威胁防护并为组织配置使用方法。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3381ce66433f1f4e32f0251c45601e3cb84865b6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538719"
---
# <a name="protect-against-threats"></a><span data-ttu-id="a92a3-103">抵御威胁</span><span class="sxs-lookup"><span data-stu-id="a92a3-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a92a3-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="a92a3-104">**Applies to**</span></span>
- [<span data-ttu-id="a92a3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a92a3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a92a3-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="a92a3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a92a3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a92a3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a92a3-108">这是一个快速的指南，它将 Defender for Office 365 的配置分成块。</span><span class="sxs-lookup"><span data-stu-id="a92a3-108">Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks.</span></span> <span data-ttu-id="a92a3-109">如果你对 Microsoft Office 365 中的威胁防护功能不了解，不知道从哪里开始，或者你喜欢通过 *上手* 来学习，使用这个指南作为一个清单和开始。</span><span class="sxs-lookup"><span data-stu-id="a92a3-109">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a92a3-110">**包括了适合每种策略的初步推荐设置；然后，很多选项都可用，你可以调整设置以满足具体的组织需要**。</span><span class="sxs-lookup"><span data-stu-id="a92a3-110">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="a92a3-111">预留大概 30 分钟以让你的策略或更改在你的数据中心中正常工作。</span><span class="sxs-lookup"><span data-stu-id="a92a3-111">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="a92a3-112">要求</span><span class="sxs-lookup"><span data-stu-id="a92a3-112">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="a92a3-113">订阅</span><span class="sxs-lookup"><span data-stu-id="a92a3-113">Subscriptions</span></span>

<span data-ttu-id="a92a3-114">威胁防护功能含在 *所有* Microsoft 或 Office 365 订阅中；然而，一些订阅有高级功能。</span><span class="sxs-lookup"><span data-stu-id="a92a3-114">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="a92a3-115">下面的表格列出了包含在此文章中的防护功能，以及最低订阅要求。</span><span class="sxs-lookup"><span data-stu-id="a92a3-115">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="a92a3-116">注意，在打开审核之外，还包含开启反恶意软件、反钓鱼、反垃圾邮件的 *步骤*，这些是 Office 365 Exchange Online Protection (**EOP**) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a92a3-116">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="a92a3-117">在你记住 (**Defender for Office 365**) 包含内容、基础、EOP 之前，这可能在 Defender for Office 365 的文章里看起来很奇怪。</span><span class="sxs-lookup"><span data-stu-id="a92a3-117">This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.</span></span>

****

|<span data-ttu-id="a92a3-118">防护类型</span><span class="sxs-lookup"><span data-stu-id="a92a3-118">Protection type</span></span>|<span data-ttu-id="a92a3-119">订阅要求</span><span class="sxs-lookup"><span data-stu-id="a92a3-119">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="a92a3-120">审核日志（出于报告的目的）</span><span class="sxs-lookup"><span data-stu-id="a92a3-120">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="a92a3-121">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a92a3-121">Exchange Online</span></span>](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="a92a3-122">反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="a92a3-122">Anti-malware protection</span></span>|<span data-ttu-id="a92a3-123">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span><span class="sxs-lookup"><span data-stu-id="a92a3-123">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="a92a3-124">防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="a92a3-124">Anti-phishing protection</span></span>|[<span data-ttu-id="a92a3-125">EOP</span><span class="sxs-lookup"><span data-stu-id="a92a3-125">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="a92a3-126">反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="a92a3-126">Anti-spam protection</span></span>|[<span data-ttu-id="a92a3-127">EOP</span><span class="sxs-lookup"><span data-stu-id="a92a3-127">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="a92a3-128">零时差自动清除 (电子邮件)</span><span class="sxs-lookup"><span data-stu-id="a92a3-128">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="a92a3-129">EOP</span><span class="sxs-lookup"><span data-stu-id="a92a3-129">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="a92a3-130">保护电子邮件和附件文档中的恶意 URL 和Office (保险箱链接保险箱附件) </span><span class="sxs-lookup"><span data-stu-id="a92a3-130">Protection from malicious URLs and files in email and Office documents (Safe Links and Safe Attachments)</span></span>|[<span data-ttu-id="a92a3-131">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a92a3-131">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="a92a3-132">打开保险箱、SharePoint OneDrive和Microsoft Teams附件</span><span class="sxs-lookup"><span data-stu-id="a92a3-132">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>|[<span data-ttu-id="a92a3-133">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a92a3-133">Microsoft Defender for Office 365</span></span>](turn-on-mdo-for-spo-odb-and-teams.md)|
|<span data-ttu-id="a92a3-134">高级反钓鱼防护</span><span class="sxs-lookup"><span data-stu-id="a92a3-134">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="a92a3-135">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a92a3-135">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="a92a3-136">角色和权限</span><span class="sxs-lookup"><span data-stu-id="a92a3-136">Roles and permissions</span></span>

<span data-ttu-id="a92a3-137">若要配置 Defender for Office 365 策略，必须在[安全与合规中心](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)分配给你一个适当的角色。</span><span class="sxs-lookup"><span data-stu-id="a92a3-137">To configure Defender for Office 365 policies, you must be assigned an appropriate role in the [Security & Compliance Center](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="a92a3-138">看看下面的表格，了解可以执行这些操作的角色。</span><span class="sxs-lookup"><span data-stu-id="a92a3-138">Take a look at the table below for roles that can do these actions.</span></span>

****

|<span data-ttu-id="a92a3-139">角色或角色组</span><span class="sxs-lookup"><span data-stu-id="a92a3-139">Role or role group</span></span>|<span data-ttu-id="a92a3-140">在哪里了解更多信息</span><span class="sxs-lookup"><span data-stu-id="a92a3-140">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="a92a3-141">全局管理员</span><span class="sxs-lookup"><span data-stu-id="a92a3-141">global administrator</span></span>|[<span data-ttu-id="a92a3-142">关于 Microsoft 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="a92a3-142">About Microsoft 365 admin roles</span></span>](../../admin/add-users/about-admin-roles.md)|
|<span data-ttu-id="a92a3-143">安全管理员</span><span class="sxs-lookup"><span data-stu-id="a92a3-143">Security Administrator</span></span>|[<span data-ttu-id="a92a3-144">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="a92a3-144">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="a92a3-145">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="a92a3-145">Exchange Online Organization Management</span></span>|[<span data-ttu-id="a92a3-146">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="a92a3-146">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo) <p> <span data-ttu-id="a92a3-147">和</span><span class="sxs-lookup"><span data-stu-id="a92a3-147">and</span></span> <p> [<span data-ttu-id="a92a3-148">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="a92a3-148">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="a92a3-149">若要了解详细信息，请参阅 [安全与合规中心的访问权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a92a3-149">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="a92a3-150">开始前，打开报告和调查的审核日志</span><span class="sxs-lookup"><span data-stu-id="a92a3-150">Before you begin, turn on Audit logging for reporting and investigation</span></span>

<span data-ttu-id="a92a3-151">早点开始审核日志。</span><span class="sxs-lookup"><span data-stu-id="a92a3-151">Start your audit logging early.</span></span> <span data-ttu-id="a92a3-152">你将需要“**打开**”审核，以执行下面的一些步骤。</span><span class="sxs-lookup"><span data-stu-id="a92a3-152">You'll need auditing to be **ON** for certain of the steps that follow.</span></span> <span data-ttu-id="a92a3-153">审核日志在包括[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="a92a3-153">Audit logging is available in subscriptions that include [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="a92a3-154">为了查看威胁防护报告中的数据，比如 [安全性仪表板](security-dashboard.md)、[电子邮件安全报告](view-email-security-reports.md)、[Explorer](threat-explorer.md)，审核日志必须“*打开*”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-154">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="a92a3-155">有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="a92a3-155">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="a92a3-156">第一部分 - 反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="a92a3-156">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="a92a3-157">[反恶意软件防护](anti-malware-protection.md)在包含 [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="a92a3-157">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="a92a3-158">在 [安全与合规中心](https://protection.office.com)中， 选择“**威胁管理**” \> “**策略**” \> “**反恶意软件**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-158">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-malware**.</span></span>

2. <span data-ttu-id="a92a3-159">双击“**默认**”策略，然后选择“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-159">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="a92a3-160">指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="a92a3-160">Specify the following settings:</span></span>

    - <span data-ttu-id="a92a3-161">在“**反恶意软件检测响应**”中，保持默认设置“**不**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-161">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="a92a3-162">在“**常见附件类型筛选器**”中，选择“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-162">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="a92a3-163">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-163">Click **Save**.</span></span>

<span data-ttu-id="a92a3-164">了解更多关于反恶意软件策略选项的信息，请参阅[配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a92a3-164">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection"></a><span data-ttu-id="a92a3-165">第二部分 - 防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="a92a3-165">Part 2 - Anti-phishing protection</span></span>

<span data-ttu-id="a92a3-166">[反钓鱼软件防护](anti-phishing-protection.md)在包含 [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="a92a3-166">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="a92a3-167">高级反钓鱼保护在 [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 中可用。</span><span class="sxs-lookup"><span data-stu-id="a92a3-167">Advanced anti-phishing protection is available in [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="a92a3-168">下列过程介绍了如何在 Microsoft Defender for Office 365 中配置反钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="a92a3-168">The following procedure describes how to configure an anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a92a3-169">这些步骤与在 EOP 中配置反钓鱼策略相似。</span><span class="sxs-lookup"><span data-stu-id="a92a3-169">The steps are similar for configuring an anti-phishing policy in EOP.</span></span>

1. <span data-ttu-id="a92a3-170">在安全 [&中心，](https://protection.office.com)选择 **"威胁管理** \> **策略** \> **""防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="a92a3-170">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="a92a3-171">单机“**默认策略**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-171">Click **Default policy**.</span></span>

3. <span data-ttu-id="a92a3-172">在“**模拟**”中，单击“**编辑**”，然后指定下列设置：</span><span class="sxs-lookup"><span data-stu-id="a92a3-172">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="a92a3-173">在“**添加保护用户**”选项卡中，“*打开*”防护。</span><span class="sxs-lookup"><span data-stu-id="a92a3-173">On the **Add users to protect** tab, turn *On* protection.</span></span> <span data-ttu-id="a92a3-174">然后添加用户，比如组织的董事会成员、CEO、CFO 和其他高级官员。</span><span class="sxs-lookup"><span data-stu-id="a92a3-174">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="a92a3-175">（你可以键入个人的电子邮件账号，或单击显示一个列表。）</span><span class="sxs-lookup"><span data-stu-id="a92a3-175">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="a92a3-176">在“**添加保护域**”选项卡中，开大“**自动包含我拥有的域**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-176">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="a92a3-177">如果你有自定义的域，添加它们。</span><span class="sxs-lookup"><span data-stu-id="a92a3-177">If you have custom domains, add them now.</span></span>

   - <span data-ttu-id="a92a3-178">在“**操作**”选项卡中，选择“**隔离消息**”，对“**模拟用户**”和“**模拟域**”选项适用。</span><span class="sxs-lookup"><span data-stu-id="a92a3-178">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="a92a3-179">同时，打开模拟安全提示。</span><span class="sxs-lookup"><span data-stu-id="a92a3-179">Also, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="a92a3-180">在“**邮箱智能**”选项卡中，确保邮箱智能打开，且打开邮箱基于智能的模拟防护。</span><span class="sxs-lookup"><span data-stu-id="a92a3-180">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on and turn on mailbox intelligence-based impersonation protection.</span></span> <span data-ttu-id="a92a3-181">在“**如果模拟用户发送电子邮件**” 列表中，选择“**隔离此消息**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-181">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="a92a3-182">在“**添加信任的发送者和域**”选项卡中，指定任何你想添加的信任的发送者和域。</span><span class="sxs-lookup"><span data-stu-id="a92a3-182">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="a92a3-183">检查设置后，在“**检查你的设置**”选项卡中，“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-183">**Save** on the **Review your settings** tab after you've reviewed your settings.</span></span>

4. <span data-ttu-id="a92a3-184">在“**欺骗**”中，单击“**编辑**”，然后指定下列设置：</span><span class="sxs-lookup"><span data-stu-id="a92a3-184">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="a92a3-185">在“**欺骗筛选器设置**”选项卡中，确保反欺骗保护已开启。</span><span class="sxs-lookup"><span data-stu-id="a92a3-185">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="a92a3-186">在“**操作**”选项卡中，选择“**隔离此消息**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-186">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="a92a3-187">检查更改后，在“**检查你的设置**”选项卡中，“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-187">**Save** on the **Review your settings** tab after you have reviewed your changes.</span></span> <span data-ttu-id="a92a3-188">（如果你没有做出任何更改，“**取消**。”）</span><span class="sxs-lookup"><span data-stu-id="a92a3-188">(If you didn't make any changes, **Cancel**.)</span></span>

5. <span data-ttu-id="a92a3-189">关闭默认策略设置页面。</span><span class="sxs-lookup"><span data-stu-id="a92a3-189">Close the default policy settings page.</span></span>

<span data-ttu-id="a92a3-190">若要了解关于反钓鱼策略选项详细信息，请参阅[在 Microsoft Defender for Office 365 中配置防钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a92a3-190">To learn more about your anti-phishing policy options, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection"></a><span data-ttu-id="a92a3-191">第三部分 - 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="a92a3-191">Part 3 - Anti-spam protection</span></span>

<span data-ttu-id="a92a3-192">[反垃圾邮件软件防护](anti-spam-protection.md)在包含 [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="a92a3-192">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="a92a3-193">在 [安全与合规中心](https://protection.office.com)内，依次转到“**威胁管理**”\>“**策略**”\>“**反垃圾邮件**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-193">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="a92a3-194">在“**自定义**”选项卡中，打开自定义设置。</span><span class="sxs-lookup"><span data-stu-id="a92a3-194">On the **Custom** tab, turn on Custom settings.</span></span>

3. <span data-ttu-id="a92a3-195">展开“**默认垃圾邮件筛选器策略**”，单击“**编辑策略**”，然后指定下列设置：</span><span class="sxs-lookup"><span data-stu-id="a92a3-195">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="a92a3-196">在“**垃圾邮件和批量操作**”中，设置值的阈值为 5 或 6。</span><span class="sxs-lookup"><span data-stu-id="a92a3-196">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="a92a3-197">在“**允许列表**”中，检查（和/或编辑）你的受信任发送者和域。</span><span class="sxs-lookup"><span data-stu-id="a92a3-197">In the **Allow lists** section, review (and/or edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="a92a3-198">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-198">Click **Save**.</span></span>

<span data-ttu-id="a92a3-199">了解更多关于反垃圾邮件策略选项的信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a92a3-199">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a><span data-ttu-id="a92a3-200">第四部分 - 防护恶意 URL 和文件带来的威胁（Defender for Office 365 中的安全链接和安全附件）</span><span class="sxs-lookup"><span data-stu-id="a92a3-200">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)</span></span>

<span data-ttu-id="a92a3-201">抵御恶意 URL 和文件的单击时防护在包含 [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="a92a3-201">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="a92a3-202">通过 “[安全附件](safe-attachments.md)”和“[安全链接](safe-links.md)”策略设置。</span><span class="sxs-lookup"><span data-stu-id="a92a3-202">It's set up through [Safe Attachments](safe-attachments.md) and [Safe Links](safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="a92a3-203">在 Defender for Office 365 中的安全附件策略</span><span class="sxs-lookup"><span data-stu-id="a92a3-203">Safe Attachments policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="a92a3-204">要设置[安全附件](safe-attachments.md)，创建至少一个安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a92a3-204">To set up [Safe Attachments](safe-attachments.md), create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="a92a3-205">在 [安全与合规中心](https://protection.office.com)中， 选择“**威胁管理**” \> “**策略**” \> “**ATP 安全附件**”，然后单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-205">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Create**.</span></span>

2. <span data-ttu-id="a92a3-206">在出现的 **新安全附件策略** 向导中，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="a92a3-206">In the **New Safe Attachments policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a92a3-207">在“**名称**”框中，键入 `Block malware`，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-207">In the **Name** box, type `Block malware`, and then click **Next**.</span></span>

   - <span data-ttu-id="a92a3-208">在“**设置**”页上，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="a92a3-208">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="a92a3-209">在“**安全附件未知恶意软件响应**”中，选择“**阻止**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-209">In the **Safe attachments unknown malware response** section, choose **Block**.</span></span>
     - <span data-ttu-id="a92a3-210">在“**重定向附件**”中，选择“**启用重定向**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-210">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="a92a3-211">为组织中检查检测到的文件的安全管理员或操作员指定电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a92a3-211">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

     <span data-ttu-id="a92a3-212">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-212">Click **Next**.</span></span>

3. <span data-ttu-id="a92a3-213">在“**应用到**”页面， 单击“**添加条件**”，选择“**应用条件：收件人域为**”， 单击“**添加**”，选择域，单击“**添加**”， 单击“**完成**”， 然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-213">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

4. <span data-ttu-id="a92a3-214">检查设置，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-214">Review your settings and then click **Finish**.</span></span>

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="a92a3-215">在 Defender for Office 365 中设置安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a92a3-215">Safe Links policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="a92a3-216">要设置“[安全链接](safe-links.md)”，检查并编辑你的安全链接全局设置，然后创建至少一个安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="a92a3-216">To set up [Safe Links](safe-links.md), review and edit your global settings for Safe Links, and create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="a92a3-217">在“[安全与合规中心](https://protection.office.com)“中，选择“**威胁管理**” \> “**策略**” \> **ATP 安全链接**，然后单击“**全局设置**”，然后配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="a92a3-217">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Links**, and click **Global settings**, and then configure the following settings:</span></span>

   - <span data-ttu-id="a92a3-218">验证“**使用安全链接于：Office 365 应用**”已经“![打开](../../media/scc-toggle-on.png)”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-218">Verify **Use Safe Links in: Office 365 applications** is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="a92a3-219">“**用户单击安全链接时不要跟踪**”：关闭来跟踪用户单击操作：“![关闭](../../media/scc-toggle-off.png)”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-219">**Do not track when users click Safe Links**: Turn this setting off to track user clicks: ![Toggle off](../../media/scc-toggle-off.png).</span></span>
   - <span data-ttu-id="a92a3-220">“**不允许用户单击安全链接至初始 URL**“：验证此设置打开：”![打开](../../media/scc-toggle-on.png)“。</span><span class="sxs-lookup"><span data-stu-id="a92a3-220">**Do not let users click through safe links to original URL**: Verify this setting is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="a92a3-221">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-221">When you're finished, click **Save**.</span></span>

2. <span data-ttu-id="a92a3-222">回到安全链接主界面，单击”**创建**“。</span><span class="sxs-lookup"><span data-stu-id="a92a3-222">Back on the main Safe Links page, click **Create**.</span></span>

3. <span data-ttu-id="a92a3-223">在出现的 **创建安全链接策略** 向导中，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="a92a3-223">In the **Create Safe Links policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a92a3-224">在“**名称**”框中，键入名称（如 `Safe Links`），然后单击”**下一步**“。</span><span class="sxs-lookup"><span data-stu-id="a92a3-224">In the **Name** box, type a name, such as `Safe Links`, and then click **Next**.</span></span>

   - <span data-ttu-id="a92a3-225">在“**设置**”页上，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="a92a3-225">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="a92a3-226">对于“**选择要对邮件中的未知潜在恶意 URL 执行的操作**”，选择“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-226">**Select the action for unknown potentially malicious URLs in messages**: Choose **On**.</span></span>
     - <span data-ttu-id="a92a3-227">对于“**选择要对 Microsoft Teams 中的未知或潜在恶意 URL 执行的操作**”，选择“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-227">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Choose **On**.</span></span>
     - <span data-ttu-id="a92a3-228">**对组织内发送的电子邮件应用安全链接**</span><span class="sxs-lookup"><span data-stu-id="a92a3-228">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="a92a3-229">**等待 URL 扫描完成，然后再传递邮件**</span><span class="sxs-lookup"><span data-stu-id="a92a3-229">**Wait for URL scanning to complete before delivering the message**</span></span>
     - <span data-ttu-id="a92a3-230">**对组织内发送的电子邮件应用安全链接**</span><span class="sxs-lookup"><span data-stu-id="a92a3-230">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="a92a3-231">**不允许用户单击至初始 URL**</span><span class="sxs-lookup"><span data-stu-id="a92a3-231">**Do not allow users to click through to original URL**</span></span>

     <span data-ttu-id="a92a3-232">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-232">Click **Next**</span></span>

4. <span data-ttu-id="a92a3-233">在“**应用到**”页面， 单击“**添加条件**”，选择“**应用条件：收件人域为**”， 单击“**添加**”，选择域，单击“**添加**”， 单击“**完成**”， 然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-233">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

5. <span data-ttu-id="a92a3-234">检查设置，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-234">Review your settings and then click **Finish**.</span></span>

<span data-ttu-id="a92a3-235">若要了解详细信息，请参阅“[设置安全链接策略](set-up-safe-links-policies.md)”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-235">To learn more, see [Set up Safe Links policies](set-up-safe-links-policies.md).</span></span>

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a><span data-ttu-id="a92a3-236">第 5 部分 - 保险箱是否SharePoint、OneDrive和Microsoft Teams附件</span><span class="sxs-lookup"><span data-stu-id="a92a3-236">Part 5 - Verify Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is turned on</span></span>

<span data-ttu-id="a92a3-237">SharePoint、OneDrive 和 Teams 这样的工作负载是为协作而构建的。</span><span class="sxs-lookup"><span data-stu-id="a92a3-237">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="a92a3-238">使用 Defender for Office 365 帮助组织和检测在团队站点和文件库中识别为恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="a92a3-238">Using Defender for Office 365 helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="a92a3-239">你可以在[这里](mdo-for-spo-odb-and-teams.md)阅读有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="a92a3-239">You can read more about how that works [here](mdo-for-spo-odb-and-teams.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a92a3-240">**开始此过程前，确保 Microsoft 365 环境的审核日志已打开**。</span><span class="sxs-lookup"><span data-stu-id="a92a3-240">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="a92a3-241">通常是由在 Exchange Online 中分配为审核日志的角色执行。</span><span class="sxs-lookup"><span data-stu-id="a92a3-241">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="a92a3-242">有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)！</span><span class="sxs-lookup"><span data-stu-id="a92a3-242">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="a92a3-243">在 [安全与合规中心](https://protection.office.com)中， 选择“**威胁管理**” \> “**策略**” \> “**ATP 安全附件**”，然后单击“**全局设置**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-243">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="a92a3-244">验证打开 **Defender for Office 365 for SharePoint、OneDrive** 和 Microsoft Teams 开关是否位于右侧：打开切换，然后单击 ![ ](../../media/scc-toggle-on.png) 保存。 </span><span class="sxs-lookup"><span data-stu-id="a92a3-244">Verify the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle is to the right: ![Toggle on](../../media/scc-toggle-on.png), and then click **Save**.</span></span>

3. <span data-ttu-id="a92a3-245">检查（并合适地编辑）组织的[安全附件策略](set-up-safe-attachments-policies.md)和[安全链接策略](set-up-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a92a3-245">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-safe-attachments-policies.md) and [Safe Links policies](set-up-safe-links-policies.md).</span></span>

4. <span data-ttu-id="a92a3-246">（推荐）作为全局管理员或 SharePoint 在线管理员，在 _DisallowInfectedFileDownload_ 参数设置为 `$true` 时运行 **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a92a3-246">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="a92a3-247">`$true`阻止所有检测到文件的操作（除了删除）。</span><span class="sxs-lookup"><span data-stu-id="a92a3-247">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="a92a3-248">人员不能打开、移动、复制或共享检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="a92a3-248">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="a92a3-249">`$false`阻止所有除删除和下载的操作。</span><span class="sxs-lookup"><span data-stu-id="a92a3-249">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="a92a3-250">人员可以选择接受风险并下载检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="a92a3-250">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="a92a3-251">了解更多用 Microsoft 365 使用 PowerShell 的信息，请参阅[使用 PowerShell 管理 Microsoft 365](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="a92a3-251">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).</span></span>

5. <span data-ttu-id="a92a3-252">预留至多 30 分钟以让更改传播到所有 Microsoft 365 数据中心。</span><span class="sxs-lookup"><span data-stu-id="a92a3-252">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="a92a3-253">现在为检测到的文件设置警报</span><span class="sxs-lookup"><span data-stu-id="a92a3-253">Now set up alerts for detected files</span></span>

<span data-ttu-id="a92a3-254">若要当 SharePoint Oline、OneDrive for Business 或Microsoft Teams 中的文件识别为恶意文件时收到通知，你可以设置警报。</span><span class="sxs-lookup"><span data-stu-id="a92a3-254">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="a92a3-255">在 [安全与合规中心](https://protection.office.com)内，依次转到“**警报**\>“**管理警报**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-255">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="a92a3-256">选择“**新建警报策略**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-256">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="a92a3-257">指定警报名称。</span><span class="sxs-lookup"><span data-stu-id="a92a3-257">Specify a name for the alert.</span></span> <span data-ttu-id="a92a3-258">比如，你可以在库中键入恶意文件。</span><span class="sxs-lookup"><span data-stu-id="a92a3-258">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="a92a3-259">键入警报说明。</span><span class="sxs-lookup"><span data-stu-id="a92a3-259">Type a description for the alert.</span></span> <span data-ttu-id="a92a3-260">比如，当恶意文件在 SharePoint Online、OneDrive 或 Microsoft Teams 中检测到时，你可以键入通知管理员。</span><span class="sxs-lookup"><span data-stu-id="a92a3-260">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="a92a3-261">在“**当...时发送此警报**”中，设置：</span><span class="sxs-lookup"><span data-stu-id="a92a3-261">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="a92a3-262">a.</span><span class="sxs-lookup"><span data-stu-id="a92a3-262">a.</span></span> <span data-ttu-id="a92a3-263">在“**活动**”列表，选择“**文件中检测到的恶意软件**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-263">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="a92a3-264">b.</span><span class="sxs-lookup"><span data-stu-id="a92a3-264">b.</span></span> <span data-ttu-id="a92a3-265">留空 **用户** 字段。</span><span class="sxs-lookup"><span data-stu-id="a92a3-265">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="a92a3-266">在 **将此警报发送至...** 中，选择一个或多个全局管理员，安全管理员，或安全读取者，他们会在监测到恶意软件时接收通知。</span><span class="sxs-lookup"><span data-stu-id="a92a3-266">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="a92a3-267">**保存**。</span><span class="sxs-lookup"><span data-stu-id="a92a3-267">**Save**.</span></span>

<span data-ttu-id="a92a3-268">了解更多关于警报的信息，请参阅[在安全与合规中心中创建活动警报](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="a92a3-268">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a92a3-269">当你完成配置时，使用这些链接开始工作负载调查：</span><span class="sxs-lookup"><span data-stu-id="a92a3-269">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="a92a3-270">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="a92a3-270">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="a92a3-271">使用安全与合规中心管理隔离文件</span><span class="sxs-lookup"><span data-stu-id="a92a3-271">Use the Security & Compliance Center to manage quarantined files</span></span>](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [<span data-ttu-id="a92a3-272">在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到恶意文件需采取的操作</span><span class="sxs-lookup"><span data-stu-id="a92a3-272">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="a92a3-273">在 Microsoft 365 中以管理员身份管理已隔离邮件和文件</span><span class="sxs-lookup"><span data-stu-id="a92a3-273">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="a92a3-274">第六部分 - 配置额外设置</span><span class="sxs-lookup"><span data-stu-id="a92a3-274">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="a92a3-275">除了配置恶意软件防护，恶意 URL 和文件、钓鱼软件和垃圾邮件之外，我们推荐你配置零时差自动清除。</span><span class="sxs-lookup"><span data-stu-id="a92a3-275">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="a92a3-276">EOP 中电子邮件零时差自动清除</span><span class="sxs-lookup"><span data-stu-id="a92a3-276">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="a92a3-277">[零时差自动清除](zero-hour-auto-purge.md)在包含 [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="a92a3-277">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="a92a3-278">此防护默认开启；但是，防护有效的前提是下列情况满足：</span><span class="sxs-lookup"><span data-stu-id="a92a3-278">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="a92a3-279">在“[反垃圾邮件策略](anti-spam-protection.md)”中调整垃圾邮件设置为“**将消息移到垃圾邮件文件夹**”。</span><span class="sxs-lookup"><span data-stu-id="a92a3-279">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="a92a3-280">用户保持默认的[垃圾邮件设置](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)，且没有关闭垃圾邮件保护。</span><span class="sxs-lookup"><span data-stu-id="a92a3-280">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="a92a3-281">若要详细了解，请参阅[零时差自动清除 - 抵御垃圾邮件和恶意软件](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="a92a3-281">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="a92a3-282">安装后任务和接下来的步骤</span><span class="sxs-lookup"><span data-stu-id="a92a3-282">Post-setup tasks and next steps</span></span>

<span data-ttu-id="a92a3-283">配置威胁防护功能之后，确保监控这些功能的运行情况！</span><span class="sxs-lookup"><span data-stu-id="a92a3-283">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="a92a3-284">检查并修改你的策略，让它们按你的需求运行。</span><span class="sxs-lookup"><span data-stu-id="a92a3-284">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="a92a3-285">同时，关注可以增加价值的新功能和服务。</span><span class="sxs-lookup"><span data-stu-id="a92a3-285">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="a92a3-286">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="a92a3-286">What to do</span></span>|<span data-ttu-id="a92a3-287">了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="a92a3-287">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="a92a3-288">通过查看报告了解威胁防护功能如何为你的阻止工作</span><span class="sxs-lookup"><span data-stu-id="a92a3-288">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="a92a3-289">安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="a92a3-289">Security dashboard</span></span>](security-dashboard.md) <p> [<span data-ttu-id="a92a3-290">电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="a92a3-290">Email security reports</span></span>](view-email-security-reports.md) <p> [<span data-ttu-id="a92a3-291">Microsoft Defender for Office 365 报告</span><span class="sxs-lookup"><span data-stu-id="a92a3-291">Reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md) <p> [<span data-ttu-id="a92a3-292">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="a92a3-292">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="a92a3-293">定期检查和修改你的威胁防护策略（如有需要）</span><span class="sxs-lookup"><span data-stu-id="a92a3-293">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="a92a3-294">安全功能分数</span><span class="sxs-lookup"><span data-stu-id="a92a3-294">Secure Score</span></span>](../defender/microsoft-secure-score.md) <p> [<span data-ttu-id="a92a3-295">智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="a92a3-295">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md) <p> [<span data-ttu-id="a92a3-296">Microsoft 365 威胁调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="a92a3-296">Microsoft 365 threat investigation and response features</span></span>](./office-365-ti.md)|
|<span data-ttu-id="a92a3-297">关注新功能和服务更新</span><span class="sxs-lookup"><span data-stu-id="a92a3-297">Watch for new features and service updates</span></span>|[<span data-ttu-id="a92a3-298">标准和目标发布选项</span><span class="sxs-lookup"><span data-stu-id="a92a3-298">Standard and Targeted release options</span></span>](../../admin/manage/release-options-in-office-365.md) <p> [<span data-ttu-id="a92a3-299">消息中心</span><span class="sxs-lookup"><span data-stu-id="a92a3-299">Message Center</span></span>](../../admin/manage/message-center.md) <p> [<span data-ttu-id="a92a3-300">Microsoft 365 路线图</span><span class="sxs-lookup"><span data-stu-id="a92a3-300">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [<span data-ttu-id="a92a3-301">服务说明</span><span class="sxs-lookup"><span data-stu-id="a92a3-301">Service Descriptions</span></span>](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="a92a3-302">了解配置 EOP 和 Defender for Office 365 的标准和严格安全配置推荐的详细信息</span><span class="sxs-lookup"><span data-stu-id="a92a3-302">Learn the details about recommended Standard and Strict security configurations for EOP and Defender for Office 365</span></span>|[<span data-ttu-id="a92a3-303">用于配置 EOP 和 Defender for Office 365 安全性的建议设置</span><span class="sxs-lookup"><span data-stu-id="a92a3-303">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)|
