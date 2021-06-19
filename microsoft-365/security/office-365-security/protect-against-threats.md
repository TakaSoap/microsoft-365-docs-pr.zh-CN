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
ms.openlocfilehash: 407838c815a85ce7c73322a0de176970ee93e537
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029605"
---
# <a name="protect-against-threats"></a><span data-ttu-id="916b5-103">抵御威胁</span><span class="sxs-lookup"><span data-stu-id="916b5-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="916b5-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="916b5-104">**Applies to**</span></span>
- [<span data-ttu-id="916b5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="916b5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="916b5-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="916b5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="916b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="916b5-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="916b5-108">这是一个快速的指南，它将 Defender for Office 365 的配置分成块。</span><span class="sxs-lookup"><span data-stu-id="916b5-108">Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks.</span></span> <span data-ttu-id="916b5-109">如果你对 Microsoft Office 365 中的威胁防护功能不了解，不知道从哪里开始，或者你喜欢通过 *上手* 来学习，使用这个指南作为一个清单和开始。</span><span class="sxs-lookup"><span data-stu-id="916b5-109">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="916b5-110">**包括了适合每种策略的初步推荐设置；然后，很多选项都可用，你可以调整设置以满足具体的组织需要**。</span><span class="sxs-lookup"><span data-stu-id="916b5-110">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="916b5-111">预留大概 30 分钟以让你的策略或更改在你的数据中心中正常工作。</span><span class="sxs-lookup"><span data-stu-id="916b5-111">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="916b5-112">要求</span><span class="sxs-lookup"><span data-stu-id="916b5-112">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="916b5-113">订阅</span><span class="sxs-lookup"><span data-stu-id="916b5-113">Subscriptions</span></span>

<span data-ttu-id="916b5-114">威胁防护功能含在 *所有* Microsoft 或 Office 365 订阅中；然而，一些订阅有高级功能。</span><span class="sxs-lookup"><span data-stu-id="916b5-114">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="916b5-115">下面的表格列出了包含在此文章中的防护功能，以及最低订阅要求。</span><span class="sxs-lookup"><span data-stu-id="916b5-115">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="916b5-116">注意，在打开审核之外，还包含开启反恶意软件、反钓鱼、反垃圾邮件的 *步骤*，这些是 Office 365 Exchange Online Protection (**EOP**) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="916b5-116">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="916b5-117">在你记住 (**Defender for Office 365**) 包含内容、基础、EOP 之前，这可能在 Defender for Office 365 的文章里看起来很奇怪。</span><span class="sxs-lookup"><span data-stu-id="916b5-117">This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.</span></span>

<br>

****

|<span data-ttu-id="916b5-118">防护类型</span><span class="sxs-lookup"><span data-stu-id="916b5-118">Protection type</span></span>|<span data-ttu-id="916b5-119">订阅要求</span><span class="sxs-lookup"><span data-stu-id="916b5-119">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="916b5-120">审核日志（出于报告的目的）</span><span class="sxs-lookup"><span data-stu-id="916b5-120">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="916b5-121">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="916b5-121">Exchange Online</span></span>](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="916b5-122">反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="916b5-122">Anti-malware protection</span></span>|<span data-ttu-id="916b5-123">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span><span class="sxs-lookup"><span data-stu-id="916b5-123">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="916b5-124">防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="916b5-124">Anti-phishing protection</span></span>|[<span data-ttu-id="916b5-125">EOP</span><span class="sxs-lookup"><span data-stu-id="916b5-125">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="916b5-126">反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="916b5-126">Anti-spam protection</span></span>|[<span data-ttu-id="916b5-127">EOP</span><span class="sxs-lookup"><span data-stu-id="916b5-127">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="916b5-128">零时差自动清除 (电子邮件)</span><span class="sxs-lookup"><span data-stu-id="916b5-128">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="916b5-129">EOP</span><span class="sxs-lookup"><span data-stu-id="916b5-129">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="916b5-130">保护电子邮件和附件文档中的恶意 URL 和Office (保险箱链接保险箱附件) </span><span class="sxs-lookup"><span data-stu-id="916b5-130">Protection from malicious URLs and files in email and Office documents (Safe Links and Safe Attachments)</span></span>|[<span data-ttu-id="916b5-131">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="916b5-131">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="916b5-132">打开保险箱、SharePoint OneDrive和Microsoft Teams附件</span><span class="sxs-lookup"><span data-stu-id="916b5-132">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>|[<span data-ttu-id="916b5-133">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="916b5-133">Microsoft Defender for Office 365</span></span>](turn-on-mdo-for-spo-odb-and-teams.md)|
|<span data-ttu-id="916b5-134">高级反钓鱼防护</span><span class="sxs-lookup"><span data-stu-id="916b5-134">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="916b5-135">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="916b5-135">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="916b5-136">角色和权限</span><span class="sxs-lookup"><span data-stu-id="916b5-136">Roles and permissions</span></span>

<span data-ttu-id="916b5-137">若要配置 Defender for Office 365 策略，必须在[安全与合规中心](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)分配给你一个适当的角色。</span><span class="sxs-lookup"><span data-stu-id="916b5-137">To configure Defender for Office 365 policies, you must be assigned an appropriate role in the [Security & Compliance Center](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="916b5-138">看看下面的表格，了解可以执行这些操作的角色。</span><span class="sxs-lookup"><span data-stu-id="916b5-138">Take a look at the table below for roles that can do these actions.</span></span>

<br>

****

|<span data-ttu-id="916b5-139">角色或角色组</span><span class="sxs-lookup"><span data-stu-id="916b5-139">Role or role group</span></span>|<span data-ttu-id="916b5-140">在哪里了解更多信息</span><span class="sxs-lookup"><span data-stu-id="916b5-140">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="916b5-141">全局管理员</span><span class="sxs-lookup"><span data-stu-id="916b5-141">global administrator</span></span>|[<span data-ttu-id="916b5-142">关于 Microsoft 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="916b5-142">About Microsoft 365 admin roles</span></span>](../../admin/add-users/about-admin-roles.md)|
|<span data-ttu-id="916b5-143">安全管理员</span><span class="sxs-lookup"><span data-stu-id="916b5-143">Security Administrator</span></span>|[<span data-ttu-id="916b5-144">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="916b5-144">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="916b5-145">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="916b5-145">Exchange Online Organization Management</span></span>|[<span data-ttu-id="916b5-146">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="916b5-146">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo) <p> <span data-ttu-id="916b5-147">和</span><span class="sxs-lookup"><span data-stu-id="916b5-147">and</span></span> <p> [<span data-ttu-id="916b5-148">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="916b5-148">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="916b5-149">若要了解详细信息，请参阅 [安全与合规中心的访问权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="916b5-149">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="916b5-150">打开用于报告和调查的审核日志记录</span><span class="sxs-lookup"><span data-stu-id="916b5-150">Turn on Audit logging for reporting and investigation</span></span>

- <span data-ttu-id="916b5-151">早点开始审核日志。</span><span class="sxs-lookup"><span data-stu-id="916b5-151">Start your audit logging early.</span></span> <span data-ttu-id="916b5-152">对于以下步骤中的 **一些步骤** ，你需要将审核功能启用。</span><span class="sxs-lookup"><span data-stu-id="916b5-152">You'll need auditing to be **ON** for some of the following steps.</span></span> <span data-ttu-id="916b5-153">审核日志在包括[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="916b5-153">Audit logging is available in subscriptions that include [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="916b5-154">为了查看威胁防护报告中的数据，比如 [安全性仪表板](security-dashboard.md)、[电子邮件安全报告](view-email-security-reports.md)、[Explorer](threat-explorer.md)，审核日志必须“*打开*”。</span><span class="sxs-lookup"><span data-stu-id="916b5-154">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="916b5-155">有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="916b5-155">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection-in-eop"></a><span data-ttu-id="916b5-156">第 1 部分 - EOP 中的反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="916b5-156">Part 1 - Anti-malware protection in EOP</span></span>

<span data-ttu-id="916b5-157">有关反恶意软件的建议设置详细信息，请参阅 [EOP 反恶意软件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="916b5-157">For more information about the recommended settings for anti-malware, see [EOP anti-malware policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings).</span></span>

1. <span data-ttu-id="916b5-158">打开 <https://security.microsoft.com/antimalwarev2> 。</span><span class="sxs-lookup"><span data-stu-id="916b5-158">Open <https://security.microsoft.com/antimalwarev2>.</span></span>

2. <span data-ttu-id="916b5-159">在 **"反恶意软件"** 页上，通过单击该名称选择名为 **"** 默认策略"的策略。</span><span class="sxs-lookup"><span data-stu-id="916b5-159">On the **Anti-malware** page, select the policy named **Default** policy by clicking on the name.</span></span>

3. <span data-ttu-id="916b5-160">在打开的策略详细信息飞出控件中，单击" **编辑保护设置"，** 然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-160">In the policy details flyout that opens, click **Edit protection settings**, and then configure the following settings:</span></span>
   - <span data-ttu-id="916b5-161">选择 **"启用常用附件筛选器** "以打开常用附件筛选器。</span><span class="sxs-lookup"><span data-stu-id="916b5-161">Select **Enable the common attachments filter** to turn on the common attachments filter.</span></span> <span data-ttu-id="916b5-162">单击 **"自定义文件类型** "以添加更多文件类型。</span><span class="sxs-lookup"><span data-stu-id="916b5-162">Click **Customize file types** to add more file types.</span></span>
   - <span data-ttu-id="916b5-163">验证是否 **选中了"启用恶意软件的零时差自动清除** "。</span><span class="sxs-lookup"><span data-stu-id="916b5-163">Verify that **Enable zero-hour auto purge for malware** is selected.</span></span>
   - <span data-ttu-id="916b5-164">验证"通知"部分未 **选择** 任何设置。</span><span class="sxs-lookup"><span data-stu-id="916b5-164">Verify that none of the settings in the **Notification** section are selected.</span></span>

   <span data-ttu-id="916b5-165">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="916b5-165">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="916b5-166">返回策略详细信息浮出控件，单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-166">Back on the policy details flyout, click **Close**.</span></span>

<span data-ttu-id="916b5-167">有关配置反恶意软件策略的详细说明，请参阅在 EOP 中配置 [反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="916b5-167">For detailed instructions for configuring anti-malware policies, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a><span data-ttu-id="916b5-168">第 2 部分 - EOP 和 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="916b5-168">Part 2 - Anti-phishing protection in EOP and Defender for Office 365</span></span>

<span data-ttu-id="916b5-169">[反钓鱼软件防护](anti-phishing-protection.md)在包含 [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="916b5-169">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="916b5-170">高级反钓鱼保护在 [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 中可用。</span><span class="sxs-lookup"><span data-stu-id="916b5-170">Advanced anti-phishing protection is available in [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="916b5-171">有关反网络钓鱼策略的建议设置详细信息，请参阅[EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)和 Microsoft Defender for Office 365 中的反网络钓鱼[策略设置](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="916b5-171">For more information about the recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) and [Anti-phishing policy settings in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

<span data-ttu-id="916b5-172">以下过程介绍如何配置默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="916b5-172">The following procedure describes how to configure the default anti-phishing policy.</span></span> <span data-ttu-id="916b5-173">设置 Defender for Office 365中提供的信息会进行清晰标记。</span><span class="sxs-lookup"><span data-stu-id="916b5-173">Settings that are only available in Defender for Office 365 are clearly marked.</span></span>

1. <span data-ttu-id="916b5-174">打开 <https://security.microsoft.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="916b5-174">Open <https://security.microsoft.com/antiphishing>.</span></span>

2. <span data-ttu-id="916b5-175">在 **"防钓鱼"** 页面上，单击该名称，选择名为 **"Office365** 反钓鱼默认 (默认) "策略。</span><span class="sxs-lookup"><span data-stu-id="916b5-175">On the **Anti-phishing** page, select the policy named **Office365 AntiPhish Default (Default)** by clicking on the name.</span></span>

3. <span data-ttu-id="916b5-176">在出现的策略详细信息飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-176">In the policy details flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="916b5-177">**网络钓鱼阈值&保护** 部分：单击"编辑保护设置"，然后配置打开的"编辑保护设置"飞出控件中的以下设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-177">**Phishing threshold & protection** section: Click **Edit protection settings** and configure the following settings in the **Edit protection settings** flyout that opens:</span></span>
     - <span data-ttu-id="916b5-178">**网络钓鱼电子邮件阈值**：选择 <sup>\*</sup> **2 - (** 标准) 或 3 - 更主动 (严格 **) 。**</span><span class="sxs-lookup"><span data-stu-id="916b5-178">**Phishing email threshold**<sup>\*</sup>: Select **2 - Aggressive** (Standard) or **3 - More Aggressive** (Strict).</span></span>
     - <span data-ttu-id="916b5-179">**模拟** 部分 <sup>\*</sup> ：配置以下值：</span><span class="sxs-lookup"><span data-stu-id="916b5-179">**Impersonation** section<sup>\*</sup>: Configure the following values:</span></span>
       - <span data-ttu-id="916b5-180">选择"允许用户保护"，单击出现的"管理 **(nn)** 发件人 () "链接，然后添加内部和外部发件人，防止模拟，例如组织的会员、CEO、CFO 和其他高级领导。</span><span class="sxs-lookup"><span data-stu-id="916b5-180">Select **Enable users to protect**, click the **Manage (nn) sender(s)** link that appears, and then add internal and external senders to protect from impersonation, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span>
       - <span data-ttu-id="916b5-181">选择 **"启用域以保护"，** 然后配置出现的以下设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-181">Select **Enable domains to protect**, and then configure the following settings that appear:</span></span>
         - <span data-ttu-id="916b5-182">选择 **"包括我拥有域**"以保护接受域中的内部发件人 (通过单击"查看我的域) 进行模拟"。</span><span class="sxs-lookup"><span data-stu-id="916b5-182">Select **Include domains I own** to protect internal senders in your accepted domains (visible by clicking **View my domains**) from impersonation.</span></span>
         - <span data-ttu-id="916b5-183">若要保护其他域中的发件人，请选择"包括自定义域"，单击出现的"管理 (nn) 自定义域 **() "** 链接，然后添加其他域防止模拟。</span><span class="sxs-lookup"><span data-stu-id="916b5-183">To protect senders in other domains, select **Include custom domains**, click the **Manage (nn) custom domain(s)** link that appears, and then add other domains to protect from impersonation.</span></span>
     - <span data-ttu-id="916b5-184">添加受信任的发件人和域部分：单击"管理 (nn) 受信任发件人 () 和域 <sup>\*</sup> (**) "** 以根据需要将发件人和发件人域例外配置为模拟保护。</span><span class="sxs-lookup"><span data-stu-id="916b5-184">**Add trusted senders and domains** section <sup>\*</sup>: Click **Manage (nn) trusted sender(s) and domains(s)** to configure sender and sender domain exceptions to impersonation protection if needed.</span></span>
     - <span data-ttu-id="916b5-185">邮箱智能设置 <sup>\*</sup> ：验证是否 **选择了"启用邮箱智能\*\*\*\*"和"启用模拟保护的** 智能"。</span><span class="sxs-lookup"><span data-stu-id="916b5-185">Mailbox intelligence settings <sup>\*</sup>: Verify that **Enable mailbox intelligence** and **Enable intelligence for impersonation protection** are selected.</span></span>
     - <span data-ttu-id="916b5-186">**欺骗** 部分：验证 **是否选择了"启用欺骗** 智能"。</span><span class="sxs-lookup"><span data-stu-id="916b5-186">**Spoof** section: Verify **Enable spoof intelligence** is selected.</span></span>

     <span data-ttu-id="916b5-187">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="916b5-187">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="916b5-188">**"** 操作"部分：单击 **"编辑操作** "，然后配置打开的"编辑 **操作** "飞出控件中的以下设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-188">**Actions** section: Click **Edit actions** and configure the following settings in the **Edit actions** flyout that opens:</span></span>
     - <span data-ttu-id="916b5-189">**"邮件** 操作"部分：配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-189">**Message actions** section: Configure the following settings:</span></span>
       - <span data-ttu-id="916b5-190">**如果邮件被检测为模拟用户** <sup>\*</sup> ：请选择 **"隔离邮件"。**</span><span class="sxs-lookup"><span data-stu-id="916b5-190">**If message is detected as an impersonated user**<sup>\*</sup>: Select **Quarantine the message**.</span></span>
       - <span data-ttu-id="916b5-191">**如果邮件被检测为模拟域** <sup>\*</sup> ：选择 **隔离邮件**。</span><span class="sxs-lookup"><span data-stu-id="916b5-191">**If message is detected as an impersonated domain**<sup>\*</sup>: Select **Quarantine the message**.</span></span>
       - <span data-ttu-id="916b5-192">**如果邮箱智能检测到模拟** 用户：选择"将邮件移动到收件人的垃圾邮件文件夹" ("标准) "或"隔离 (<sup>\*</sup> 严格) "。  </span><span class="sxs-lookup"><span data-stu-id="916b5-192">**If mailbox intelligence detects an impersonated user**<sup>\*</sup>: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).</span></span>
       - <span data-ttu-id="916b5-193">**如果邮件被检测** 为欺骗邮件：选择"将邮件移动到收件人的垃圾邮件文件夹" (标准) 或"隔离 (严格) "。 </span><span class="sxs-lookup"><span data-stu-id="916b5-193">**If message is detected as spoof**: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).</span></span>
     - <span data-ttu-id="916b5-194">**安全提示&** 指示器部分：配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-194">**Safety tips & indicators** section: Configure the following settings:</span></span>
       - <span data-ttu-id="916b5-195">**显示第一个联系人安全提示：** 选择 (打开) 。</span><span class="sxs-lookup"><span data-stu-id="916b5-195">**Show first contact safety tip**: Select (turn on).</span></span>
       - <span data-ttu-id="916b5-196">**显示用户模拟安全提示：** <sup>\*</sup> 选择 (启用) 。</span><span class="sxs-lookup"><span data-stu-id="916b5-196">**Show user impersonation safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="916b5-197">**显示域模拟安全提示：** <sup>\*</sup> 选择 (启用) 。</span><span class="sxs-lookup"><span data-stu-id="916b5-197">**Show domain impersonation safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="916b5-198">**显示用户模拟异常字符安全提示：** 选择 <sup>\*</sup> (打开) 。</span><span class="sxs-lookup"><span data-stu-id="916b5-198">**Show user impersonation unusual characters safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="916b5-199">**显示 (？)** 欺骗的未经身份验证的发件人：选择 (打开) 。</span><span class="sxs-lookup"><span data-stu-id="916b5-199">**Show (?) for unauthenticated senders for spoof**: Select (turn on).</span></span>
       - <span data-ttu-id="916b5-200">**显示"via"标记**：选择 (打开) 。</span><span class="sxs-lookup"><span data-stu-id="916b5-200">**Show "via" tag**: Select (turn on).</span></span>

     <span data-ttu-id="916b5-201">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="916b5-201">When you're finished, click **Save**.</span></span>

   <span data-ttu-id="916b5-202"><sup>\*</sup>此设置仅在 Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="916b5-202"><sup>\*</sup> This setting is available only in Defender for Office 365.</span></span>

4. <span data-ttu-id="916b5-203">单击 **"保存"，** 然后单击" **关闭"**</span><span class="sxs-lookup"><span data-stu-id="916b5-203">Click **Save** and then click **Close**</span></span>

<span data-ttu-id="916b5-204">有关配置防钓鱼策略的详细说明，请参阅在[EOP](configure-anti-phishing-policies-eop.md)中配置防钓鱼策略和在 Microsoft Defender 中配置防钓鱼策略[Office 365。](configure-mdo-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="916b5-204">For detailed instructions for configuring anti-phishing policies, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) and [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection-in-eop"></a><span data-ttu-id="916b5-205">第 3 部分 - EOP 中的反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="916b5-205">Part 3 - Anti-spam protection in EOP</span></span>

<span data-ttu-id="916b5-206">有关反垃圾邮件的建议设置详细信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="916b5-206">For more information about the recommended settings for anti-spam, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

1. <span data-ttu-id="916b5-207">打开 <https://security.microsoft.com/antispam> 。</span><span class="sxs-lookup"><span data-stu-id="916b5-207">Open <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="916b5-208">在 **"反垃圾邮件策略**"页上，单击该名称，从 ("默认) "列表中选择名为"反垃圾邮件入站策略"的策略。</span><span class="sxs-lookup"><span data-stu-id="916b5-208">On the **Anti-spam policies** page, select the policy named **Anti-spam inbound policy (Default)** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="916b5-209">在出现的策略详细信息飞出中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="916b5-209">In the policy details flyout that appears, do the following steps:</span></span>
   - <span data-ttu-id="916b5-210">**批量电子邮件阈值&"垃圾邮件属性"** 部分：单击"**编辑垃圾邮件阈值和属性"。**</span><span class="sxs-lookup"><span data-stu-id="916b5-210">**Bulk email threshold & spam properties** section: Click **Edit spam threshold and properties**.</span></span> <span data-ttu-id="916b5-211">在 **出现的垃圾邮件阈值和属性** 飞出控件中，将"批量电子邮件阈值"设置为 5 (Strict) 或 6 (Standard) 。</span><span class="sxs-lookup"><span data-stu-id="916b5-211">In the **spam threshold and properties** flyout that appears, set the **Bulk email threshold** value to 5 (Strict) or 6 (Standard).</span></span> <span data-ttu-id="916b5-212">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="916b5-212">When you're finished, click **Save**.</span></span>
   - <span data-ttu-id="916b5-213">**允许和阻止的发件人和域** 部分：查看或编辑允许的发件人和允许的域。</span><span class="sxs-lookup"><span data-stu-id="916b5-213">**Allowed and blocked senders and domains** section: Review or edit your allowed senders and allowed domains.</span></span>

4. <span data-ttu-id="916b5-214">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="916b5-214">When you're finished, click **Close**.</span></span>

<span data-ttu-id="916b5-215">有关配置反垃圾邮件策略的详细说明，请参阅在 EOP 中配置 [反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="916b5-215">For detailed instructions for configuring anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a><span data-ttu-id="916b5-216">第四部分 - 防护恶意 URL 和文件带来的威胁（Defender for Office 365 中的安全链接和安全附件）</span><span class="sxs-lookup"><span data-stu-id="916b5-216">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)</span></span>

<span data-ttu-id="916b5-217">抵御恶意 URL 和文件的单击时防护在包含 [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="916b5-217">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="916b5-218">通过 “[安全附件](safe-attachments.md)”和“[安全链接](safe-links.md)”策略设置。</span><span class="sxs-lookup"><span data-stu-id="916b5-218">It's set up through [Safe Attachments](safe-attachments.md) and [Safe Links](safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="916b5-219">在 Defender for Office 365 中的安全附件策略</span><span class="sxs-lookup"><span data-stu-id="916b5-219">Safe Attachments policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="916b5-220">要设置[安全附件](safe-attachments.md)，创建至少一个安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="916b5-220">To set up [Safe Attachments](safe-attachments.md), create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="916b5-221">在 [安全与合规中心](https://protection.office.com)中， 选择“**威胁管理**” \> “**策略**” \> “**ATP 安全附件**”，然后单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-221">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Create**.</span></span>

2. <span data-ttu-id="916b5-222">在出现的 **新安全附件策略** 向导中，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-222">In the **New Safe Attachments policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="916b5-223">在“**名称**”框中，键入 `Block malware`，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-223">In the **Name** box, type `Block malware`, and then click **Next**.</span></span>

   - <span data-ttu-id="916b5-224">在“**设置**”页上，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-224">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="916b5-225">在“**安全附件未知恶意软件响应**”中，选择“**阻止**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-225">In the **Safe attachments unknown malware response** section, choose **Block**.</span></span>
     - <span data-ttu-id="916b5-226">在“**重定向附件**”中，选择“**启用重定向**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-226">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="916b5-227">为组织中检查检测到的文件的安全管理员或操作员指定电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="916b5-227">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

     <span data-ttu-id="916b5-228">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-228">Click **Next**.</span></span>

3. <span data-ttu-id="916b5-229">在“**应用到**”页面， 单击“**添加条件**”，选择“**应用条件：收件人域为**”， 单击“**添加**”，选择域，单击“**添加**”， 单击“**完成**”， 然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-229">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

4. <span data-ttu-id="916b5-230">检查设置，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-230">Review your settings and then click **Finish**.</span></span>

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="916b5-231">在 Defender for Office 365 中设置安全链接策略</span><span class="sxs-lookup"><span data-stu-id="916b5-231">Safe Links policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="916b5-232">要设置“[安全链接](safe-links.md)”，检查并编辑你的安全链接全局设置，然后创建至少一个安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="916b5-232">To set up [Safe Links](safe-links.md), review and edit your global settings for Safe Links, and create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="916b5-233">在“[安全与合规中心](https://protection.office.com)“中，选择“**威胁管理**” \> “**策略**” \> **ATP 安全链接**，然后单击“**全局设置**”，然后配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-233">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Links**, and click **Global settings**, and then configure the following settings:</span></span>

   - <span data-ttu-id="916b5-234">验证“**使用安全链接于：Office 365 应用**”已经“![打开](../../media/scc-toggle-on.png)”。</span><span class="sxs-lookup"><span data-stu-id="916b5-234">Verify **Use Safe Links in: Office 365 applications** is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="916b5-235">“**用户单击安全链接时不要跟踪**”：关闭来跟踪用户单击操作：“![关闭](../../media/scc-toggle-off.png)”。</span><span class="sxs-lookup"><span data-stu-id="916b5-235">**Do not track when users click Safe Links**: Turn this setting off to track user clicks: ![Toggle off](../../media/scc-toggle-off.png).</span></span>
   - <span data-ttu-id="916b5-236">“**不允许用户单击安全链接至初始 URL**“：验证此设置打开：”![打开](../../media/scc-toggle-on.png)“。</span><span class="sxs-lookup"><span data-stu-id="916b5-236">**Do not let users click through safe links to original URL**: Verify this setting is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="916b5-237">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-237">When you're finished, click **Save**.</span></span>

2. <span data-ttu-id="916b5-238">回到安全链接主界面，单击”**创建**“。</span><span class="sxs-lookup"><span data-stu-id="916b5-238">Back on the main Safe Links page, click **Create**.</span></span>

3. <span data-ttu-id="916b5-239">在出现的 **创建安全链接策略** 向导中，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-239">In the **Create Safe Links policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="916b5-240">在“**名称**”框中，键入名称（如 `Safe Links`），然后单击”**下一步**“。</span><span class="sxs-lookup"><span data-stu-id="916b5-240">In the **Name** box, type a name, such as `Safe Links`, and then click **Next**.</span></span>

   - <span data-ttu-id="916b5-241">在“**设置**”页上，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-241">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="916b5-242">对于“**选择要对邮件中的未知潜在恶意 URL 执行的操作**”，选择“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-242">**Select the action for unknown potentially malicious URLs in messages**: Choose **On**.</span></span>
     - <span data-ttu-id="916b5-243">对于“**选择要对 Microsoft Teams 中的未知或潜在恶意 URL 执行的操作**”，选择“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-243">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Choose **On**.</span></span>
     - <span data-ttu-id="916b5-244">**对组织内发送的电子邮件应用安全链接**</span><span class="sxs-lookup"><span data-stu-id="916b5-244">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="916b5-245">**等待 URL 扫描完成，然后再传递邮件**</span><span class="sxs-lookup"><span data-stu-id="916b5-245">**Wait for URL scanning to complete before delivering the message**</span></span>
     - <span data-ttu-id="916b5-246">**对组织内发送的电子邮件应用安全链接**</span><span class="sxs-lookup"><span data-stu-id="916b5-246">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="916b5-247">**不允许用户单击至初始 URL**</span><span class="sxs-lookup"><span data-stu-id="916b5-247">**Do not allow users to click through to original URL**</span></span>

     <span data-ttu-id="916b5-248">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-248">Click **Next**</span></span>

4. <span data-ttu-id="916b5-249">在“**应用到**”页面， 单击“**添加条件**”，选择“**应用条件：收件人域为**”， 单击“**添加**”，选择域，单击“**添加**”， 单击“**完成**”， 然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-249">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

5. <span data-ttu-id="916b5-250">检查设置，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-250">Review your settings and then click **Finish**.</span></span>

<span data-ttu-id="916b5-251">若要了解详细信息，请参阅“[设置安全链接策略](set-up-safe-links-policies.md)”。</span><span class="sxs-lookup"><span data-stu-id="916b5-251">To learn more, see [Set up Safe Links policies](set-up-safe-links-policies.md).</span></span>

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a><span data-ttu-id="916b5-252">第 5 部分 - 保险箱是否SharePoint、OneDrive和Microsoft Teams附件</span><span class="sxs-lookup"><span data-stu-id="916b5-252">Part 5 - Verify Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is turned on</span></span>

<span data-ttu-id="916b5-253">SharePoint、OneDrive 和 Teams 这样的工作负载是为协作而构建的。</span><span class="sxs-lookup"><span data-stu-id="916b5-253">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="916b5-254">使用 Defender for Office 365 帮助组织和检测在团队站点和文件库中识别为恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="916b5-254">Using Defender for Office 365 helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="916b5-255">你可以在[这里](mdo-for-spo-odb-and-teams.md)阅读有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="916b5-255">You can read more about how that works [here](mdo-for-spo-odb-and-teams.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="916b5-256">**开始此过程前，确保 Microsoft 365 环境的审核日志已打开**。</span><span class="sxs-lookup"><span data-stu-id="916b5-256">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="916b5-257">通常是由在 Exchange Online 中分配为审核日志的角色执行。</span><span class="sxs-lookup"><span data-stu-id="916b5-257">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="916b5-258">有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)！</span><span class="sxs-lookup"><span data-stu-id="916b5-258">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="916b5-259">在 [安全与合规中心](https://protection.office.com)中， 选择“**威胁管理**” \> “**策略**” \> “**ATP 安全附件**”，然后单击“**全局设置**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-259">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="916b5-260">验证打开 **Defender for Office 365 for SharePoint、OneDrive** 和 Microsoft Teams 开关是否位于右侧：打开切换，然后单击 ![ ](../../media/scc-toggle-on.png) 保存。 </span><span class="sxs-lookup"><span data-stu-id="916b5-260">Verify the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle is to the right: ![Toggle on](../../media/scc-toggle-on.png), and then click **Save**.</span></span>

3. <span data-ttu-id="916b5-261">检查（并合适地编辑）组织的[安全附件策略](set-up-safe-attachments-policies.md)和[安全链接策略](set-up-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="916b5-261">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-safe-attachments-policies.md) and [Safe Links policies](set-up-safe-links-policies.md).</span></span>

4. <span data-ttu-id="916b5-262">（推荐）作为全局管理员或 SharePoint 在线管理员，在 _DisallowInfectedFileDownload_ 参数设置为 `$true` 时运行 **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="916b5-262">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="916b5-263">`$true`阻止所有检测到文件的操作（除了删除）。</span><span class="sxs-lookup"><span data-stu-id="916b5-263">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="916b5-264">人员不能打开、移动、复制或共享检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="916b5-264">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="916b5-265">`$false`阻止所有除删除和下载的操作。</span><span class="sxs-lookup"><span data-stu-id="916b5-265">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="916b5-266">人员可以选择接受风险并下载检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="916b5-266">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="916b5-267">了解更多用 Microsoft 365 使用 PowerShell 的信息，请参阅[使用 PowerShell 管理 Microsoft 365](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="916b5-267">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).</span></span>

5. <span data-ttu-id="916b5-268">预留至多 30 分钟以让更改传播到所有 Microsoft 365 数据中心。</span><span class="sxs-lookup"><span data-stu-id="916b5-268">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="916b5-269">现在为检测到的文件设置警报</span><span class="sxs-lookup"><span data-stu-id="916b5-269">Now set up alerts for detected files</span></span>

<span data-ttu-id="916b5-270">若要当 SharePoint Oline、OneDrive for Business 或Microsoft Teams 中的文件识别为恶意文件时收到通知，你可以设置警报。</span><span class="sxs-lookup"><span data-stu-id="916b5-270">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="916b5-271">在 [安全与合规中心](https://protection.office.com)内，依次转到“**警报**\>“**管理警报**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-271">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="916b5-272">选择“**新建警报策略**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-272">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="916b5-273">指定警报名称。</span><span class="sxs-lookup"><span data-stu-id="916b5-273">Specify a name for the alert.</span></span> <span data-ttu-id="916b5-274">比如，你可以在库中键入恶意文件。</span><span class="sxs-lookup"><span data-stu-id="916b5-274">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="916b5-275">键入警报说明。</span><span class="sxs-lookup"><span data-stu-id="916b5-275">Type a description for the alert.</span></span> <span data-ttu-id="916b5-276">比如，当恶意文件在 SharePoint Online、OneDrive 或 Microsoft Teams 中检测到时，你可以键入通知管理员。</span><span class="sxs-lookup"><span data-stu-id="916b5-276">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="916b5-277">在“**当...时发送此警报**”中，设置：</span><span class="sxs-lookup"><span data-stu-id="916b5-277">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="916b5-278">a.</span><span class="sxs-lookup"><span data-stu-id="916b5-278">a.</span></span> <span data-ttu-id="916b5-279">在“**活动**”列表，选择“**文件中检测到的恶意软件**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-279">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="916b5-280">b.</span><span class="sxs-lookup"><span data-stu-id="916b5-280">b.</span></span> <span data-ttu-id="916b5-281">留空 **用户** 字段。</span><span class="sxs-lookup"><span data-stu-id="916b5-281">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="916b5-282">在 **将此警报发送至...** 中，选择一个或多个全局管理员，安全管理员，或安全读取者，他们会在监测到恶意软件时接收通知。</span><span class="sxs-lookup"><span data-stu-id="916b5-282">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="916b5-283">**保存**。</span><span class="sxs-lookup"><span data-stu-id="916b5-283">**Save**.</span></span>

<span data-ttu-id="916b5-284">了解更多关于警报的信息，请参阅[在安全与合规中心中创建活动警报](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="916b5-284">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="916b5-285">当你完成配置时，使用这些链接开始工作负载调查：</span><span class="sxs-lookup"><span data-stu-id="916b5-285">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="916b5-286">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="916b5-286">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="916b5-287">使用 Microsoft 365 Defender 门户在 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="916b5-287">Use the Microsoft 365 Defender portal to manage quarantined files in Defender for Office 365</span></span>](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [<span data-ttu-id="916b5-288">在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到恶意文件需采取的操作</span><span class="sxs-lookup"><span data-stu-id="916b5-288">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="916b5-289">在 Microsoft 365 中以管理员身份管理已隔离邮件和文件</span><span class="sxs-lookup"><span data-stu-id="916b5-289">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="916b5-290">第六部分 - 配置额外设置</span><span class="sxs-lookup"><span data-stu-id="916b5-290">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="916b5-291">除了配置恶意软件防护，恶意 URL 和文件、钓鱼软件和垃圾邮件之外，我们推荐你配置零时差自动清除。</span><span class="sxs-lookup"><span data-stu-id="916b5-291">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="916b5-292">EOP 中电子邮件零时差自动清除</span><span class="sxs-lookup"><span data-stu-id="916b5-292">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="916b5-293">[零时差自动清除](zero-hour-auto-purge.md)在包含 [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="916b5-293">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="916b5-294">此防护默认开启；但是，防护有效的前提是下列情况满足：</span><span class="sxs-lookup"><span data-stu-id="916b5-294">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="916b5-295">在“[反垃圾邮件策略](anti-spam-protection.md)”中调整垃圾邮件设置为“**将消息移到垃圾邮件文件夹**”。</span><span class="sxs-lookup"><span data-stu-id="916b5-295">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="916b5-296">用户保持默认的[垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)，且没有关闭垃圾邮件保护。</span><span class="sxs-lookup"><span data-stu-id="916b5-296">Users have kept their default [junk email settings](configure-junk-email-settings-on-exo-mailboxes.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="916b5-297">若要详细了解，请参阅[零时差自动清除 - 抵御垃圾邮件和恶意软件](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="916b5-297">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="916b5-298">安装后任务和接下来的步骤</span><span class="sxs-lookup"><span data-stu-id="916b5-298">Post-setup tasks and next steps</span></span>

<span data-ttu-id="916b5-299">配置威胁防护功能之后，确保监控这些功能的运行情况！</span><span class="sxs-lookup"><span data-stu-id="916b5-299">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="916b5-300">检查并修改你的策略，让它们按你的需求运行。</span><span class="sxs-lookup"><span data-stu-id="916b5-300">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="916b5-301">同时，关注可以增加价值的新功能和服务。</span><span class="sxs-lookup"><span data-stu-id="916b5-301">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="916b5-302">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="916b5-302">What to do</span></span>|<span data-ttu-id="916b5-303">了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="916b5-303">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="916b5-304">通过查看报告了解威胁防护功能如何为你的阻止工作</span><span class="sxs-lookup"><span data-stu-id="916b5-304">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="916b5-305">安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="916b5-305">Security dashboard</span></span>](security-dashboard.md) <p> [<span data-ttu-id="916b5-306">电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="916b5-306">Email security reports</span></span>](view-email-security-reports.md) <p> [<span data-ttu-id="916b5-307">Microsoft Defender for Office 365 报告</span><span class="sxs-lookup"><span data-stu-id="916b5-307">Reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md) <p> [<span data-ttu-id="916b5-308">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="916b5-308">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="916b5-309">定期检查和修改你的威胁防护策略（如有需要）</span><span class="sxs-lookup"><span data-stu-id="916b5-309">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="916b5-310">安全功能分数</span><span class="sxs-lookup"><span data-stu-id="916b5-310">Secure Score</span></span>](../defender/microsoft-secure-score.md) <p> [<span data-ttu-id="916b5-311">智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="916b5-311">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md) <p> [<span data-ttu-id="916b5-312">Microsoft 365 威胁调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="916b5-312">Microsoft 365 threat investigation and response features</span></span>](./office-365-ti.md)|
|<span data-ttu-id="916b5-313">关注新功能和服务更新</span><span class="sxs-lookup"><span data-stu-id="916b5-313">Watch for new features and service updates</span></span>|[<span data-ttu-id="916b5-314">标准和目标发布选项</span><span class="sxs-lookup"><span data-stu-id="916b5-314">Standard and Targeted release options</span></span>](../../admin/manage/release-options-in-office-365.md) <p> [<span data-ttu-id="916b5-315">消息中心</span><span class="sxs-lookup"><span data-stu-id="916b5-315">Message Center</span></span>](../../admin/manage/message-center.md) <p> [<span data-ttu-id="916b5-316">Microsoft 365 路线图</span><span class="sxs-lookup"><span data-stu-id="916b5-316">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [<span data-ttu-id="916b5-317">服务说明</span><span class="sxs-lookup"><span data-stu-id="916b5-317">Service Descriptions</span></span>](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="916b5-318">了解配置 EOP 和 Defender for Office 365 的标准和严格安全配置推荐的详细信息</span><span class="sxs-lookup"><span data-stu-id="916b5-318">Learn the details about recommended Standard and Strict security configurations for EOP and Defender for Office 365</span></span>|[<span data-ttu-id="916b5-319">用于配置 EOP 和 Defender for Office 365 安全性的建议设置</span><span class="sxs-lookup"><span data-stu-id="916b5-319">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)|
