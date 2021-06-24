---
title: 在 Microsoft Defender 中抵御威胁Office 365、反恶意软件、反网络钓鱼、反垃圾邮件、保险箱 链接、保险箱 附件、零时差自动清除 (ZAP) 、MDO 安全配置
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 06/22/2021
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
ms.openlocfilehash: 7e37b67dbed75e3283070ba94321fcb03979a5a6
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105388"
---
# <a name="protect-against-threats"></a><span data-ttu-id="14a36-103">抵御威胁</span><span class="sxs-lookup"><span data-stu-id="14a36-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="14a36-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="14a36-104">**Applies to**</span></span>
- [<span data-ttu-id="14a36-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="14a36-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="14a36-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="14a36-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="14a36-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14a36-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="14a36-108">这是一个快速的指南，它将 Defender for Office 365 的配置分成块。</span><span class="sxs-lookup"><span data-stu-id="14a36-108">Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks.</span></span> <span data-ttu-id="14a36-109">如果你对 Microsoft Office 365 中的威胁防护功能不了解，不知道从哪里开始，或者你喜欢通过 *上手* 来学习，使用这个指南作为一个清单和开始。</span><span class="sxs-lookup"><span data-stu-id="14a36-109">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14a36-110">**包括了适合每种策略的初步推荐设置；然后，很多选项都可用，你可以调整设置以满足具体的组织需要**。</span><span class="sxs-lookup"><span data-stu-id="14a36-110">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="14a36-111">预留大概 30 分钟以让你的策略或更改在你的数据中心中正常工作。</span><span class="sxs-lookup"><span data-stu-id="14a36-111">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>
>
> <span data-ttu-id="14a36-112">若要跳过 Defender for Office 365 中的大多数策略的手动配置，可以使用"标准"或"严格"级别的预设安全策略。</span><span class="sxs-lookup"><span data-stu-id="14a36-112">To skip manual configuration of most policies in Defender for Office 365, you can use preset security policies at the Standard or Strict level.</span></span> <span data-ttu-id="14a36-113">有关详细信息，请参阅[Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="14a36-113">For more information, see [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="14a36-114">要求</span><span class="sxs-lookup"><span data-stu-id="14a36-114">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="14a36-115">订阅</span><span class="sxs-lookup"><span data-stu-id="14a36-115">Subscriptions</span></span>

<span data-ttu-id="14a36-116">威胁防护功能含在 *所有* Microsoft 或 Office 365 订阅中；然而，一些订阅有高级功能。</span><span class="sxs-lookup"><span data-stu-id="14a36-116">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="14a36-117">下面的表格列出了包含在此文章中的防护功能，以及最低订阅要求。</span><span class="sxs-lookup"><span data-stu-id="14a36-117">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="14a36-118">请注意，除了启用审核的说明之外，步骤还启动反恶意软件、反网络钓鱼和反垃圾邮件，它们标记为 **EOP** Office 365 Exchange Online Protection (的一) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-118">Notice that beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="14a36-119">在你记住 (**Defender for Office 365**) 包含内容、基础、EOP 之前，这可能在 Defender for Office 365 的文章里看起来很奇怪。</span><span class="sxs-lookup"><span data-stu-id="14a36-119">This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.</span></span>

<br>

****

|<span data-ttu-id="14a36-120">防护类型</span><span class="sxs-lookup"><span data-stu-id="14a36-120">Protection type</span></span>|<span data-ttu-id="14a36-121">订阅要求</span><span class="sxs-lookup"><span data-stu-id="14a36-121">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="14a36-122">审核日志（出于报告的目的）</span><span class="sxs-lookup"><span data-stu-id="14a36-122">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="14a36-123">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="14a36-123">Exchange Online</span></span>](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="14a36-124">反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="14a36-124">Anti-malware protection</span></span>|<span data-ttu-id="14a36-125">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span><span class="sxs-lookup"><span data-stu-id="14a36-125">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="14a36-126">防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="14a36-126">Anti-phishing protection</span></span>|[<span data-ttu-id="14a36-127">EOP</span><span class="sxs-lookup"><span data-stu-id="14a36-127">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="14a36-128">反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="14a36-128">Anti-spam protection</span></span>|[<span data-ttu-id="14a36-129">EOP</span><span class="sxs-lookup"><span data-stu-id="14a36-129">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="14a36-130">保护电子邮件和附件文档中的恶意 URL 和Office (保险箱链接保险箱附件) </span><span class="sxs-lookup"><span data-stu-id="14a36-130">Protection from malicious URLs and files in email and Office documents (Safe Links and Safe Attachments)</span></span>|[<span data-ttu-id="14a36-131">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="14a36-131">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="14a36-132">角色和权限</span><span class="sxs-lookup"><span data-stu-id="14a36-132">Roles and permissions</span></span>

<span data-ttu-id="14a36-133">若要为用户Office 365 Defender，必须分配有适当的角色。</span><span class="sxs-lookup"><span data-stu-id="14a36-133">To configure Defender for Office 365 policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="14a36-134">看看下面的表格，了解可以执行这些操作的角色。</span><span class="sxs-lookup"><span data-stu-id="14a36-134">Take a look at the table below for roles that can do these actions.</span></span>

<br>

****

|<span data-ttu-id="14a36-135">角色或角色组</span><span class="sxs-lookup"><span data-stu-id="14a36-135">Role or role group</span></span>|<span data-ttu-id="14a36-136">在哪里了解更多信息</span><span class="sxs-lookup"><span data-stu-id="14a36-136">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="14a36-137">全局管理员</span><span class="sxs-lookup"><span data-stu-id="14a36-137">global administrator</span></span>|[<span data-ttu-id="14a36-138">关于 Microsoft 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="14a36-138">About Microsoft 365 admin roles</span></span>](../../admin/add-users/about-admin-roles.md)|
|<span data-ttu-id="14a36-139">安全管理员</span><span class="sxs-lookup"><span data-stu-id="14a36-139">Security Administrator</span></span>|[<span data-ttu-id="14a36-140">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="14a36-140">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="14a36-141">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="14a36-141">Exchange Online Organization Management</span></span>|[<span data-ttu-id="14a36-142">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="14a36-142">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)|
|

<span data-ttu-id="14a36-143">若要了解更多信息，请参阅 Microsoft 365 Defender[门户中的权限](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="14a36-143">To learn more, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="14a36-144">打开用于报告和调查的审核日志记录</span><span class="sxs-lookup"><span data-stu-id="14a36-144">Turn on audit logging for reporting and investigation</span></span>

- <span data-ttu-id="14a36-145">早点开始审核日志。</span><span class="sxs-lookup"><span data-stu-id="14a36-145">Start your audit logging early.</span></span> <span data-ttu-id="14a36-146">对于以下步骤中的 **一些步骤** ，你需要将审核功能启用。</span><span class="sxs-lookup"><span data-stu-id="14a36-146">You'll need auditing to be **ON** for some of the following steps.</span></span> <span data-ttu-id="14a36-147">审核日志在包括[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="14a36-147">Audit logging is available in subscriptions that include [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="14a36-148">若要查看威胁防护报告、电子邮件安全报告和 [资源管理器](threat-explorer.md)中 [](view-email-security-reports.md)的数据，审核日志记录必须 *位于" 打开"。*</span><span class="sxs-lookup"><span data-stu-id="14a36-148">In order to view data in threat protection reports, [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="14a36-149">有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="14a36-149">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection-in-eop"></a><span data-ttu-id="14a36-150">第 1 部分 - EOP 中的反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="14a36-150">Part 1 - Anti-malware protection in EOP</span></span>

<span data-ttu-id="14a36-151">有关反恶意软件的建议设置详细信息，请参阅 [EOP 反恶意软件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="14a36-151">For more information about the recommended settings for anti-malware, see [EOP anti-malware policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings).</span></span>

1. <span data-ttu-id="14a36-152">打开 **网站门户中的**"反恶意软件"Microsoft 365 Defender位于 <https://security.microsoft.com/antimalwarev2> 。</span><span class="sxs-lookup"><span data-stu-id="14a36-152">Open the **Anti-malware** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/antimalwarev2>.</span></span>

2. <span data-ttu-id="14a36-153">在 **"反恶意软件"** 页上，单击该名称 **("默认) "** 策略。</span><span class="sxs-lookup"><span data-stu-id="14a36-153">On the **Anti-malware** page, select the policy named **Default (Default)** by clicking on the name.</span></span>

3. <span data-ttu-id="14a36-154">在打开的策略详细信息飞出控件中，单击" **编辑保护设置"，** 然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-154">In the policy details flyout that opens, click **Edit protection settings**, and then configure the following settings:</span></span>
   - <span data-ttu-id="14a36-155">**保护设置** 部分：</span><span class="sxs-lookup"><span data-stu-id="14a36-155">**Protection settings** section:</span></span>
     - <span data-ttu-id="14a36-156">**启用常用附件筛选器**：选择 (启用) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-156">**Enable the common attachments filter**: Select (turn on).</span></span> <span data-ttu-id="14a36-157">单击 **"自定义文件类型** "以添加更多文件类型。</span><span class="sxs-lookup"><span data-stu-id="14a36-157">Click **Customize file types** to add more file types.</span></span>
     - <span data-ttu-id="14a36-158">**启用恶意软件的零时差自动清除**：验证此设置是否被选中。</span><span class="sxs-lookup"><span data-stu-id="14a36-158">**Enable zero-hour auto purge for malware**: Verify this setting is selected.</span></span> <span data-ttu-id="14a36-159">有关恶意软件的 ZAP 详细信息，请参阅恶意软件的零时 ([ZAP](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware)) 清除。</span><span class="sxs-lookup"><span data-stu-id="14a36-159">For more information about ZAP for malware, see [Zero-hour auto purge (ZAP) for malware](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware).</span></span>
   - <span data-ttu-id="14a36-160">**通知** 部分：验证是否未选择任何通知设置。</span><span class="sxs-lookup"><span data-stu-id="14a36-160">**Notification** section: Verify that none of the notification settings are selected.</span></span>

   <span data-ttu-id="14a36-161">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="14a36-161">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="14a36-162">返回策略详细信息浮出控件，单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="14a36-162">Back on the policy details flyout, click **Close**.</span></span>

<span data-ttu-id="14a36-163">有关配置反恶意软件策略的详细说明，请参阅在 EOP 中配置 [反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="14a36-163">For detailed instructions for configuring anti-malware policies, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a><span data-ttu-id="14a36-164">第 2 部分 - EOP 和 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="14a36-164">Part 2 - Anti-phishing protection in EOP and Defender for Office 365</span></span>

<span data-ttu-id="14a36-165">[反钓鱼软件防护](anti-phishing-protection.md)在包含 [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="14a36-165">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="14a36-166">高级反钓鱼保护在 [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 中可用。</span><span class="sxs-lookup"><span data-stu-id="14a36-166">Advanced anti-phishing protection is available in [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="14a36-167">有关反网络钓鱼策略的建议设置详细信息，请参阅[EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)和 Microsoft Defender for Office 365 中的反网络钓鱼[策略设置](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="14a36-167">For more information about the recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) and [Anti-phishing policy settings in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

<span data-ttu-id="14a36-168">以下过程介绍如何配置默认的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="14a36-168">The following procedure describes how to configure the default anti-phishing policy.</span></span> <span data-ttu-id="14a36-169">设置 Defender for Office 365中提供的信息会进行清晰标记。</span><span class="sxs-lookup"><span data-stu-id="14a36-169">Settings that are only available in Defender for Office 365 are clearly marked.</span></span>

1. <span data-ttu-id="14a36-170">打开 **网站门户** 中的"防钓鱼Microsoft 365 Defender页面，位置为 <https://security.microsoft.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="14a36-170">Open the **Anti-phishing** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/antiphishing>.</span></span>

2. <span data-ttu-id="14a36-171">在 **"防钓鱼"** 页面上，单击该名称，选择名为 **"Office365** 反钓鱼默认 (默认) "策略。</span><span class="sxs-lookup"><span data-stu-id="14a36-171">On the **Anti-phishing** page, select the policy named **Office365 AntiPhish Default (Default)** by clicking on the name.</span></span>

3. <span data-ttu-id="14a36-172">在出现的策略详细信息飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-172">In the policy details flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="14a36-173">**网络钓鱼阈值&保护** 部分：单击"编辑保护设置"，在打开的飞出控件中配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-173">**Phishing threshold & protection** section: Click **Edit protection settings** and configure the following settings in the flyout that opens:</span></span>
     - <span data-ttu-id="14a36-174">**网络钓鱼电子邮件阈值**：选择 <sup>\*</sup> **2 - (** 标准) 或 3 - 更主动 (严格 **) 。**</span><span class="sxs-lookup"><span data-stu-id="14a36-174">**Phishing email threshold**<sup>\*</sup>: Select **2 - Aggressive** (Standard) or **3 - More Aggressive** (Strict).</span></span>
     - <span data-ttu-id="14a36-175">**模拟** 部分 <sup>\*</sup> ：配置以下值：</span><span class="sxs-lookup"><span data-stu-id="14a36-175">**Impersonation** section<sup>\*</sup>: Configure the following values:</span></span>
       - <span data-ttu-id="14a36-176">选择"允许用户保护"，单击出现的"管理 **(nn)** 发件人 () "链接，然后添加内部和外部发件人，防止模拟，例如组织的会员、CEO、CFO 和其他高级领导。</span><span class="sxs-lookup"><span data-stu-id="14a36-176">Select **Enable users to protect**, click the **Manage (nn) sender(s)** link that appears, and then add internal and external senders to protect from impersonation, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span>
       - <span data-ttu-id="14a36-177">选择 **"启用域以保护"，** 然后配置出现的以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-177">Select **Enable domains to protect**, and then configure the following settings that appear:</span></span>
         - <span data-ttu-id="14a36-178">选择 **"包括我拥有域**"以保护接受域中的内部发件人 (通过单击"查看我的域) 进行模拟"。</span><span class="sxs-lookup"><span data-stu-id="14a36-178">Select **Include domains I own** to protect internal senders in your accepted domains (visible by clicking **View my domains**) from impersonation.</span></span>
         - <span data-ttu-id="14a36-179">若要保护其他域中的发件人，请选择"包括自定义域"，单击出现的"管理 (nn) 自定义域 **() "** 链接，然后添加其他域防止模拟。</span><span class="sxs-lookup"><span data-stu-id="14a36-179">To protect senders in other domains, select **Include custom domains**, click the **Manage (nn) custom domain(s)** link that appears, and then add other domains to protect from impersonation.</span></span>
     - <span data-ttu-id="14a36-180">添加受信任的发件人和域部分：单击"管理 (nn) 受信任发件人 () 和域 <sup>\*</sup> (**) "** 以根据需要将发件人和发件人域例外配置为模拟保护。</span><span class="sxs-lookup"><span data-stu-id="14a36-180">**Add trusted senders and domains** section <sup>\*</sup>: Click **Manage (nn) trusted sender(s) and domains(s)** to configure sender and sender domain exceptions to impersonation protection if needed.</span></span>
     - <span data-ttu-id="14a36-181">邮箱智能设置 <sup>\*</sup> ：验证是否 **选择了"启用邮箱智能\*\*\*\*"和"启用模拟保护的** 智能"。</span><span class="sxs-lookup"><span data-stu-id="14a36-181">Mailbox intelligence settings <sup>\*</sup>: Verify that **Enable mailbox intelligence** and **Enable intelligence for impersonation protection** are selected.</span></span>
     - <span data-ttu-id="14a36-182">**欺骗** 部分：验证 **是否选择了"启用欺骗** 智能"。</span><span class="sxs-lookup"><span data-stu-id="14a36-182">**Spoof** section: Verify **Enable spoof intelligence** is selected.</span></span>

     <span data-ttu-id="14a36-183">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="14a36-183">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="14a36-184">**"** 操作 **"部分：** 单击"编辑操作"，在打开的飞出控件中配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-184">**Actions** section: Click **Edit actions** and configure the following settings in the flyout that opens:</span></span>
     - <span data-ttu-id="14a36-185">**"邮件** 操作"部分：配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-185">**Message actions** section: Configure the following settings:</span></span>
       - <span data-ttu-id="14a36-186">**如果邮件被检测为模拟用户** <sup>\*</sup> ：请选择 **"隔离邮件"。**</span><span class="sxs-lookup"><span data-stu-id="14a36-186">**If message is detected as an impersonated user**<sup>\*</sup>: Select **Quarantine the message**.</span></span>
       - <span data-ttu-id="14a36-187">**如果邮件被检测为模拟域** <sup>\*</sup> ：选择 **隔离邮件**。</span><span class="sxs-lookup"><span data-stu-id="14a36-187">**If message is detected as an impersonated domain**<sup>\*</sup>: Select **Quarantine the message**.</span></span>
       - <span data-ttu-id="14a36-188">**如果邮箱智能检测到模拟** 用户：选择"将邮件移动到收件人的垃圾邮件文件夹" ("标准) "或"隔离 (<sup>\*</sup> 严格) "。  </span><span class="sxs-lookup"><span data-stu-id="14a36-188">**If mailbox intelligence detects an impersonated user**<sup>\*</sup>: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).</span></span>
       - <span data-ttu-id="14a36-189">**如果邮件被检测** 为欺骗邮件：选择"将邮件移动到收件人的垃圾邮件文件夹" (标准) 或"隔离 (严格) "。 </span><span class="sxs-lookup"><span data-stu-id="14a36-189">**If message is detected as spoof**: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).</span></span>
     - <span data-ttu-id="14a36-190">**安全提示&** 指示器部分：配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-190">**Safety tips & indicators** section: Configure the following settings:</span></span>
       - <span data-ttu-id="14a36-191">**显示第一个联系人安全提示：** 选择 (打开) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-191">**Show first contact safety tip**: Select (turn on).</span></span>
       - <span data-ttu-id="14a36-192">**显示用户模拟安全提示：** <sup>\*</sup> 选择 (启用) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-192">**Show user impersonation safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="14a36-193">**显示域模拟安全提示：** <sup>\*</sup> 选择 (启用) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-193">**Show domain impersonation safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="14a36-194">**显示用户模拟异常字符安全提示：** 选择 <sup>\*</sup> (打开) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-194">**Show user impersonation unusual characters safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="14a36-195">**显示 (？)** 欺骗的未经身份验证的发件人：选择 (打开) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-195">**Show (?) for unauthenticated senders for spoof**: Select (turn on).</span></span>
       - <span data-ttu-id="14a36-196">**显示"via"标记**：选择 (打开) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-196">**Show "via" tag**: Select (turn on).</span></span>

     <span data-ttu-id="14a36-197">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="14a36-197">When you're finished, click **Save**.</span></span>

   <span data-ttu-id="14a36-198"><sup>\*</sup>此设置仅在 Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="14a36-198"><sup>\*</sup> This setting is available only in Defender for Office 365.</span></span>

4. <span data-ttu-id="14a36-199">单击 **"保存"，** 然后单击" **关闭"**</span><span class="sxs-lookup"><span data-stu-id="14a36-199">Click **Save** and then click **Close**</span></span>

<span data-ttu-id="14a36-200">有关配置防钓鱼策略的详细说明，请参阅在[EOP](configure-anti-phishing-policies-eop.md)中配置防钓鱼策略和在 Microsoft Defender 中配置防钓鱼策略[Office 365。](configure-mdo-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="14a36-200">For detailed instructions for configuring anti-phishing policies, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) and [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection-in-eop"></a><span data-ttu-id="14a36-201">第 3 部分 - EOP 中的反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="14a36-201">Part 3 - Anti-spam protection in EOP</span></span>

<span data-ttu-id="14a36-202">有关反垃圾邮件的建议设置详细信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="14a36-202">For more information about the recommended settings for anti-spam, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

1. <span data-ttu-id="14a36-203">打开 **门户中的"反垃圾邮件策略**"Microsoft 365 Defender位于 <https://security.microsoft.com/antispam> 。</span><span class="sxs-lookup"><span data-stu-id="14a36-203">Open the **Anti-spam policies** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="14a36-204">在 **"反垃圾邮件策略**"页上，单击该名称，从 ("默认) "列表中选择名为"反垃圾邮件入站策略"的策略。</span><span class="sxs-lookup"><span data-stu-id="14a36-204">On the **Anti-spam policies** page, select the policy named **Anti-spam inbound policy (Default)** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="14a36-205">在出现的策略详细信息飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-205">In the policy details flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="14a36-206">**批量电子邮件阈值&"垃圾邮件属性"** 部分：单击"**编辑垃圾邮件阈值和属性"。**</span><span class="sxs-lookup"><span data-stu-id="14a36-206">**Bulk email threshold & spam properties** section: Click **Edit spam threshold and properties**.</span></span> <span data-ttu-id="14a36-207">在出现的"飞出"中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-207">In the flyout that appears, configure the following settings:</span></span>
     - <span data-ttu-id="14a36-208">**批量电子邮件阈值**：将此值设置为 5 (Strict) 或 6 (Standard) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-208">**Bulk email threshold**: Set this value to 5 (Strict) or 6 (Standard).</span></span>
     - <span data-ttu-id="14a36-209">将其他设置保留为默认值 **("** 关闭"或"无 **) "。**</span><span class="sxs-lookup"><span data-stu-id="14a36-209">Leave other settings at their default values (**Off** or **None**).</span></span>

     <span data-ttu-id="14a36-210">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="14a36-210">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="14a36-211">**"操作**"部分：单击 **"编辑操作"。**</span><span class="sxs-lookup"><span data-stu-id="14a36-211">**Actions** section: Click **Edit actions**.</span></span> <span data-ttu-id="14a36-212">在出现的"飞出"中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-212">In the flyout that appears, configure the following settings:</span></span>
     - <span data-ttu-id="14a36-213">**"邮件操作** "部分：</span><span class="sxs-lookup"><span data-stu-id="14a36-213">**Message actions** section:</span></span>
       - <span data-ttu-id="14a36-214">**垃圾邮件**：验证"**将** 邮件移动到垃圾邮件文件夹"是否 ("标准) 或选择"隔离邮件 (严格) "。</span><span class="sxs-lookup"><span data-stu-id="14a36-214">**Spam**: Verify **Move message to Junk Email folder** is selected (Standard) or select **Quarantine message** (Strict).</span></span>
       - <span data-ttu-id="14a36-215">**高可信度垃圾邮件**：选择 **"隔离邮件"。**</span><span class="sxs-lookup"><span data-stu-id="14a36-215">**High confidence spam**: Select **Quarantine message**.</span></span>
       - <span data-ttu-id="14a36-216">**网络钓鱼：** 选择隔离 **邮件**。</span><span class="sxs-lookup"><span data-stu-id="14a36-216">**Phishing**:  Select **Quarantine message**.</span></span>
       - <span data-ttu-id="14a36-217">**高可信度网络钓鱼**：验证 **是否选择了** 隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="14a36-217">**High confidence phishing**: Verify **Quarantine messages** is selected.</span></span>
       - <span data-ttu-id="14a36-218">**批量**：验证"**将邮件移动到** 垃圾邮件文件夹"是否 (标准) 或选择"隔离邮件 (严格) "。</span><span class="sxs-lookup"><span data-stu-id="14a36-218">**Bulk**: Verify **Move message to Junk Email folder** is selected (Standard) or select **Quarantine message** (Strict).</span></span>
     - <span data-ttu-id="14a36-219">**将垃圾邮件在隔离邮箱中保留此天数**：验证值 **30** 天。</span><span class="sxs-lookup"><span data-stu-id="14a36-219">**Retain spam in quarantine for this many days**: Verify the value **30** days.</span></span>
     - <span data-ttu-id="14a36-220">**启用垃圾邮件安全提示**：验证此设置是否 (启用) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-220">**Enable spam safety tips**: Verify this setting is selected (turned on).</span></span>
     - <span data-ttu-id="14a36-221">**启用零时差自动清除 (ZAP) ：** 验证此设置是否选中 (启用) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-221">**Enable zero-hour auto purge (ZAP)**: Verify this setting is selected (turned on).</span></span>
       - <span data-ttu-id="14a36-222">**启用网络钓鱼邮件**：验证是否选中此设置 (是否) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-222">**Enable for phishing messages**: Verify this setting is selected (turned on).</span></span> <span data-ttu-id="14a36-223">有关详细信息，请参阅零[时差自动清除 (ZAP) 网页。](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing)</span><span class="sxs-lookup"><span data-stu-id="14a36-223">For more information, see [Zero-hour auto purge (ZAP) for phishing](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing).</span></span>
       - <span data-ttu-id="14a36-224">**启用垃圾邮件**：验证是否选中此设置 (是否) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-224">**Enable for spam messages**:  Verify this setting is selected (turned on).</span></span> <span data-ttu-id="14a36-225">有关详细信息，请参阅 [零时差自动清除 (ZAP](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam)) 垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="14a36-225">For more information, see [Zero-hour auto purge (ZAP) for spam](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam).</span></span>
     - <span data-ttu-id="14a36-226">**通知** 部分：</span><span class="sxs-lookup"><span data-stu-id="14a36-226">**Notifications** section:</span></span>
       - <span data-ttu-id="14a36-227">选择 **"启用最终用户垃圾邮件通知"。**</span><span class="sxs-lookup"><span data-stu-id="14a36-227">Select **Enable end-user spam notifications**.</span></span>
         - <span data-ttu-id="14a36-228">**每两天发送一次最终用户 () ：** 验证值 **3** 天。</span><span class="sxs-lookup"><span data-stu-id="14a36-228">**Send end-user spam notifications every (days)**: Verify the value **3** days.</span></span>
         - <span data-ttu-id="14a36-229">**语言**：验证值 **Default** 或选择语言。</span><span class="sxs-lookup"><span data-stu-id="14a36-229">**Language**: Verify the value **Default** or select a language.</span></span>

     <span data-ttu-id="14a36-230">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="14a36-230">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="14a36-231">**允许和阻止的发件人** 和域部分：查看或编辑允许的发件人和允许的域，如在 [EOP](create-block-sender-lists-in-office-365.md) 中创建阻止的发件人列表或在 EOP 中创建安全发件人 [列表中所述](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="14a36-231">**Allowed and blocked senders and domains** section: Review or edit your allowed senders and allowed domains as described in [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md) or [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

     <span data-ttu-id="14a36-232">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="14a36-232">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="14a36-233">完成后，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="14a36-233">When you're finished, click **Close**.</span></span>

<span data-ttu-id="14a36-234">有关配置反垃圾邮件策略的详细说明，请参阅在 EOP 中配置 [反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="14a36-234">For detailed instructions for configuring anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a><span data-ttu-id="14a36-235">第四部分 - 防护恶意 URL 和文件带来的威胁（Defender for Office 365 中的安全链接和安全附件）</span><span class="sxs-lookup"><span data-stu-id="14a36-235">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)</span></span>

<span data-ttu-id="14a36-236">抵御恶意 URL 和文件的单击时防护在包含 [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="14a36-236">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="14a36-237">通过 “[安全附件](safe-attachments.md)”和“[安全链接](safe-links.md)”策略设置。</span><span class="sxs-lookup"><span data-stu-id="14a36-237">It's set up through [Safe Attachments](safe-attachments.md) and [Safe Links](safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="14a36-238">在 Defender for Office 365 中的安全附件策略</span><span class="sxs-lookup"><span data-stu-id="14a36-238">Safe Attachments policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="14a36-239">有关附件的建议设置保险箱，请参阅 。[保险箱附件设置 。](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="14a36-239">For more information about the recommended settings for Safe Attachments, see .[Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

1. <span data-ttu-id="14a36-240">在 保险箱 **门户** 中打开"Microsoft 365 Defender附件"页 <https://security.microsoft.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="14a36-240">Open the **Safe Attachments** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/safeattachmentv2>.</span></span>

2. <span data-ttu-id="14a36-241">On the **保险箱 Attachments** page， click **Global settings**， and then configure the following settings on the flyout that appears：</span><span class="sxs-lookup"><span data-stu-id="14a36-241">On the **Safe Attachments** page, click **Global settings**, and then configure the following settings on the flyout that appears:</span></span>
   - <span data-ttu-id="14a36-242">**打开 Defender for Office 365 for SharePoint、OneDrive 和 Microsoft Teams：** 在) 上启用此设置 (![ ](../../media/scc-toggle-on.png) 切换。</span><span class="sxs-lookup"><span data-stu-id="14a36-242">**Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams**: Turn on this setting (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="14a36-243">在启用保险箱、SharePoint OneDrive和Microsoft Teams的"附件"之前，请验证审核 **日志记录在组织中是否已打开**。</span><span class="sxs-lookup"><span data-stu-id="14a36-243">**Before you turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, verify that audit logging is turned in your organization**.</span></span> <span data-ttu-id="14a36-244">此操作通常由在审核日志中分配了审核日志角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="14a36-244">This action is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="14a36-245">有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)！</span><span class="sxs-lookup"><span data-stu-id="14a36-245">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

   - <span data-ttu-id="14a36-246">**打开 保险箱 客户端Office** 文档：打开此设置 (![ 切换 ](../../media/scc-toggle-on.png)) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-246">**Turn on Safe Documents for Office clients**: Turn on this setting (![Toggle on](../../media/scc-toggle-on.png)).</span></span> <span data-ttu-id="14a36-247">请注意，此功能仅对许可证Microsoft 365 E5或Microsoft 365 E5 安全性有意义。</span><span class="sxs-lookup"><span data-stu-id="14a36-247">Note that this feature is available and meaningful only with Microsoft 365 E5 or Microsoft 365 E5 Security licenses.</span></span>
   - <span data-ttu-id="14a36-248">**允许用户单击"受保护的** 视图"，即使保险箱文件被标识为恶意文件：验证是否关闭此设置 (![ 关闭 ](../../media/scc-toggle-off.png)) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-248">**Allow people to click through Protected View even if Safe Documents identified the file as malicious**: Verify this setting is turned off (![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="14a36-249">完成后，单击"保存 **"**</span><span class="sxs-lookup"><span data-stu-id="14a36-249">When you're finished, click **Save**</span></span>

3. <span data-ttu-id="14a36-250">返回到"附件 **保险箱页上**，单击" ![ 创建图标 ](../../media/m365-cc-sc-create-icon.png) "。</span><span class="sxs-lookup"><span data-stu-id="14a36-250">Back on the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png).</span></span>

4. <span data-ttu-id="14a36-251">在打开 **的保险箱** 附件策略向导中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-251">In the **Create Safe Attachments policy** wizard that opens, configure the following settings:</span></span>
   - <span data-ttu-id="14a36-252">**命名策略** 页面：</span><span class="sxs-lookup"><span data-stu-id="14a36-252">**Name your policy** page:</span></span>
     - <span data-ttu-id="14a36-253">**名称**：输入唯一的描述性内容。</span><span class="sxs-lookup"><span data-stu-id="14a36-253">**Name**: Enter something unique and descriptive.</span></span>
     - <span data-ttu-id="14a36-254">**说明**：输入可选说明。</span><span class="sxs-lookup"><span data-stu-id="14a36-254">**Description**: Enter an optional description.</span></span>
   - <span data-ttu-id="14a36-255">**用户和域** 页面：因为这是你的第一个策略，你可能想要最大化覆盖范围，请考虑在"域"[](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)框中 **输入接受的** 域。</span><span class="sxs-lookup"><span data-stu-id="14a36-255">**Users and domains** page: Because this is your first policy and you likely want to maximize coverage, consider entering your [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in the **Domains** box.</span></span> <span data-ttu-id="14a36-256">否则，可以使用"用户 **"** 和" **组** "框进行更精细的控制。</span><span class="sxs-lookup"><span data-stu-id="14a36-256">Otherwise, you can use the **Users** and **Groups** boxes for more granular control.</span></span> <span data-ttu-id="14a36-257">可以通过选择"排除这些用户、组和域"并输入值 **来指定例外** 。</span><span class="sxs-lookup"><span data-stu-id="14a36-257">You can specify exceptions by selecting **Exclude these users, groups, and domains** and entering values.</span></span>
   - <span data-ttu-id="14a36-258">**设置** 页：</span><span class="sxs-lookup"><span data-stu-id="14a36-258">**Settings** page:</span></span>
     - <span data-ttu-id="14a36-259">**保险箱附件未知恶意软件响应：** 选择"阻止 **"。**</span><span class="sxs-lookup"><span data-stu-id="14a36-259">**Safe Attachments unknown malware response**: Select **Block**.</span></span>
     - <span data-ttu-id="14a36-260">**重定向包含检测到的附件的** 附件： **启用** 重定向：打开此设置 (选择) 并输入电子邮件地址以接收检测到的邮件。</span><span class="sxs-lookup"><span data-stu-id="14a36-260">**Redirect attachment with detected attachments** : **Enable redirect**: Turn this setting on (select) and enter an email address to receive detected messages.</span></span>
     - <span data-ttu-id="14a36-261">**如果扫描保险箱超时或错误** 无法完成， (应用附件检测) ：验证是否选中了此设置。</span><span class="sxs-lookup"><span data-stu-id="14a36-261">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: Verify this setting is selected.</span></span>

5. <span data-ttu-id="14a36-262">完成后，单击"提交 **"，** 然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="14a36-262">When you're finished, click **Submit**, and then click **Done**.</span></span>

6. <span data-ttu-id="14a36-263"> (建议) 全局管理员或 SharePoint Online 管理员，运行 **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet，在 SharePoint Online PowerShell 中将 _DisallowInfectedFileDownload_ 参数设置为 。 `$true`</span><span class="sxs-lookup"><span data-stu-id="14a36-263">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true` in SharePoint Online PowerShell.</span></span>
   - <span data-ttu-id="14a36-264">`$true`阻止所有检测到文件的操作（除了删除）。</span><span class="sxs-lookup"><span data-stu-id="14a36-264">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="14a36-265">用户无法打开、移动、复制或共享检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="14a36-265">People can't open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="14a36-266">`$false`阻止所有除删除和下载的操作。</span><span class="sxs-lookup"><span data-stu-id="14a36-266">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="14a36-267">人员可以选择接受风险并下载检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="14a36-267">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="14a36-268">预留至多 30 分钟以让更改传播到所有 Microsoft 365 数据中心。</span><span class="sxs-lookup"><span data-stu-id="14a36-268">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

<span data-ttu-id="14a36-269">有关为附件配置保险箱和 保险箱全局设置的详细说明，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="14a36-269">For detailed instructions for configuring Safe Attachments policies and global settings for Safe Attachments, see the following topics:</span></span>

- [<span data-ttu-id="14a36-270">在 Microsoft Defender 保险箱设置附件策略Office 365</span><span class="sxs-lookup"><span data-stu-id="14a36-270">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>](set-up-safe-attachments-policies.md)
- [<span data-ttu-id="14a36-271">为 SharePoint、OneDrive 和 Microsoft Teams 启用安全附件</span><span class="sxs-lookup"><span data-stu-id="14a36-271">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="14a36-272">Microsoft 365 E5 中的安全文档</span><span class="sxs-lookup"><span data-stu-id="14a36-272">Safe Documents in Microsoft 365 E5</span></span>](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="14a36-273">在 Defender for Office 365 中设置安全链接策略</span><span class="sxs-lookup"><span data-stu-id="14a36-273">Safe Links policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="14a36-274">有关链接的建议设置保险箱，请参阅保险箱[链接设置。](recommended-settings-for-eop-and-office365.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="14a36-274">For more information about the recommended settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

1. <span data-ttu-id="14a36-275">在 保险箱 **门户** 中打开"Microsoft 365 Defender链接"页 <https://security.microsoft.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="14a36-275">Open the **Safe Links** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/safelinksv2>.</span></span>

2. <span data-ttu-id="14a36-276">在 **"保险箱"** 页上，单击"全局设置"，然后在出现的飞出页面上配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-276">On the **Safe Links** page, click **Global settings**, and then configure the following settings on the flyout that appears:</span></span>
   - <span data-ttu-id="14a36-277">**设置支持的应用部分中的内容Office 365应用**：</span><span class="sxs-lookup"><span data-stu-id="14a36-277">**Settings that apply to content in supported Office 365 apps** section:</span></span>
     - <span data-ttu-id="14a36-278">**Use 保险箱 Links in Office 365 apps**： Verify this setting is turned on (Toggle on ![ ](../../media/scc-toggle-on.png)) .</span><span class="sxs-lookup"><span data-stu-id="14a36-278">**Use Safe Links in Office 365 apps**: Verify this setting is turned on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>
     - <span data-ttu-id="14a36-279">**Do not track when users click protected links in Office 365 apps**： Turn this setting off (Toggle off ![ ](../../media/scc-toggle-off.png)) .</span><span class="sxs-lookup"><span data-stu-id="14a36-279">**Do not track when users click protected links in Office 365 apps**: Turn this setting off (![Toggle off](../../media/scc-toggle-off.png)).</span></span>
     - <span data-ttu-id="14a36-280">**请勿让用户单击浏览** 到 Office 365 应用中的原始 URL：验证此设置是否 ("切换 ![ ](../../media/scc-toggle-on.png) ") 。</span><span class="sxs-lookup"><span data-stu-id="14a36-280">**Do not let users click through to the original URL in Office 365 apps**: Verify this setting is turned on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

   <span data-ttu-id="14a36-281">完成后，单击"保存 **"**</span><span class="sxs-lookup"><span data-stu-id="14a36-281">When you're finished, click **Save**</span></span>

3. <span data-ttu-id="14a36-282">返回到 **"保险箱"页上**，单击" ![ 创建图标 ](../../media/m365-cc-sc-create-icon.png) "。</span><span class="sxs-lookup"><span data-stu-id="14a36-282">Back on the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png).</span></span>

4. <span data-ttu-id="14a36-283">在打开 **的** 保险箱链接策略向导中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-283">In the **Create Safe Links policy** wizard that opens, configure the following settings:</span></span>
   - <span data-ttu-id="14a36-284">**命名策略** 页面：</span><span class="sxs-lookup"><span data-stu-id="14a36-284">**Name your policy** page:</span></span>
     - <span data-ttu-id="14a36-285">**名称**：输入唯一的描述性内容。</span><span class="sxs-lookup"><span data-stu-id="14a36-285">**Name**: Enter something unique and descriptive.</span></span>
     - <span data-ttu-id="14a36-286">**说明**：输入可选说明。</span><span class="sxs-lookup"><span data-stu-id="14a36-286">**Description**: Enter an optional description.</span></span>
   - <span data-ttu-id="14a36-287">**用户和域** 页面：因为这是你的第一个策略，你可能想要最大化覆盖范围，请考虑在"域"[](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)框中 **输入接受的** 域。</span><span class="sxs-lookup"><span data-stu-id="14a36-287">**Users and domains** page: Because this is your first policy and you likely want to maximize coverage, consider entering your [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in the **Domains** box.</span></span> <span data-ttu-id="14a36-288">否则，可以使用"用户 **"** 和" **组** "框进行更精细的控制。</span><span class="sxs-lookup"><span data-stu-id="14a36-288">Otherwise, you can use the **Users** and **Groups** boxes for more granular control.</span></span> <span data-ttu-id="14a36-289">可以通过选择"排除这些用户、组和域"并输入值 **来指定例外** 。</span><span class="sxs-lookup"><span data-stu-id="14a36-289">You can specify exceptions by selecting **Exclude these users, groups, and domains** and entering values.</span></span>
   - <span data-ttu-id="14a36-290">**"保护设置"** 页：</span><span class="sxs-lookup"><span data-stu-id="14a36-290">**Protection settings** page:</span></span>
     - <span data-ttu-id="14a36-291">**选择邮件中未知潜在恶意 URL 的操作**：打开 **此设置**。</span><span class="sxs-lookup"><span data-stu-id="14a36-291">**Select the action for unknown potentially malicious URLs in messages**: Turn this setting **On**.</span></span>
     - <span data-ttu-id="14a36-292">**Select the action for unknown or potentially malicious urls within Microsoft Teams**： Turn this setting **On**.</span><span class="sxs-lookup"><span data-stu-id="14a36-292">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Turn this setting **On**.</span></span> <span data-ttu-id="14a36-293">自 2020 年 3 月起，此设置为预览版，仅对 Microsoft Teams 技术采用计划成员 (TAP) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-293">As of March 2020, this setting is in Preview and is available or functional only for members of the Microsoft Teams Technology Adoption Program (TAP).</span></span>
     - <span data-ttu-id="14a36-294">**对指向文件的可疑链接应用实时 URL** 扫描：选择此设置 (打开) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-294">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting (turn on).</span></span>
       - <span data-ttu-id="14a36-295">**等待 URL 扫描完成，然后再传递邮件**：选择此设置 (打开) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-295">**Wait for URL scanning to complete before delivering the message**: Select this setting (turn on).</span></span>
     - <span data-ttu-id="14a36-296">**Apply 保险箱 Links to email messages sent within the organization**： Select this setting (turn on) .</span><span class="sxs-lookup"><span data-stu-id="14a36-296">**Apply Safe Links to email messages sent within the organization**: Select this setting (turn on).</span></span>
     - <span data-ttu-id="14a36-297">**Do not track user clicks**： Verify this setting is not selected (off) .</span><span class="sxs-lookup"><span data-stu-id="14a36-297">**Do not track user clicks**: Verify this setting is not selected (turned off).</span></span>
     - <span data-ttu-id="14a36-298">**不允许用户单击到原始 URL：** 验证此设置是否 (选中) 。</span><span class="sxs-lookup"><span data-stu-id="14a36-298">**Do not let users click through to the original URL**: Verify this setting is turned on (selected).</span></span>
     - <span data-ttu-id="14a36-299">在通知和警告页面上显示组织品牌：选择此设置 (将其打开) 只有在按照自定义[组织的 Microsoft 365](../../admin/setup/customize-your-organization-theme.md)主题中的说明上载公司徽标后，此设置才有意义。</span><span class="sxs-lookup"><span data-stu-id="14a36-299">**Display the organization branding on notification and warning pages**: Selecting this setting (turning it on) is meaningful only after you've followed the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your company logo.</span></span>
     - <span data-ttu-id="14a36-300">**不要重写以下 URL：** 我们对此设置没有具体的建议。</span><span class="sxs-lookup"><span data-stu-id="14a36-300">**Do not rewrite the following URLs**: We have no specific recommendation for this setting.</span></span> <span data-ttu-id="14a36-301">有关详细信息，请参阅链接策略中的"不重写[保险箱 URL"列表](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="14a36-301">For more information, see ["Do not rewrite the following URLs" lists in Safe Links policies](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies).</span></span>
   - <span data-ttu-id="14a36-302">**通知** 页面：</span><span class="sxs-lookup"><span data-stu-id="14a36-302">**Notification** page:</span></span>
     - <span data-ttu-id="14a36-303">**如何通知用户？** section：（可选）可以选择"使用 **自定义通知文本** "输入要使用自定义的通知文本。</span><span class="sxs-lookup"><span data-stu-id="14a36-303">**How would you like to notify users?** section: Optionally, you can select **Use custom notification text** to enter customized notification text to use.</span></span> <span data-ttu-id="14a36-304">还可以选择"使用 **Microsoft 翻译工具进行自动本地化**"，将自定义通知文本翻译为用户语言。</span><span class="sxs-lookup"><span data-stu-id="14a36-304">You can also select **Use Microsoft Translator for automatic localization** to translate the custom notification text into the user's language.</span></span> <span data-ttu-id="14a36-305">否则，保留 **"使用默认通知文本"** 为选中状态。</span><span class="sxs-lookup"><span data-stu-id="14a36-305">Otherwise, leave **Use the default notification text** selected.</span></span>

5. <span data-ttu-id="14a36-306">完成后，单击"提交 **"，** 然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="14a36-306">When you're finished, click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="14a36-307">有关为链接配置 保险箱 链接策略和全局设置的保险箱，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="14a36-307">For detailed instructions for configuring Safe Links policies and global settings for Safe Links, see the following topics:</span></span>

- [<span data-ttu-id="14a36-308">在 Microsoft Defender 保险箱设置链接策略Office 365</span><span class="sxs-lookup"><span data-stu-id="14a36-308">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>](set-up-safe-links-policies.md)
- [<span data-ttu-id="14a36-309">在 Microsoft Defender 中配置保险箱链接的全局Office 365</span><span class="sxs-lookup"><span data-stu-id="14a36-309">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a><span data-ttu-id="14a36-310">现在，为 SharePoint Online 或 OneDrive for Business 中检测到的文件设置警报</span><span class="sxs-lookup"><span data-stu-id="14a36-310">Now set up alerts for detected files in SharePoint Online or OneDrive for Business</span></span>

<span data-ttu-id="14a36-311">若要在 SharePoint Online 或 OneDrive for Business文件被标识为恶意文件时收到通知，可以设置警报，如本节中所述。</span><span class="sxs-lookup"><span data-stu-id="14a36-311">To receive notification when a file in SharePoint Online or OneDrive for Business has been identified as malicious, you can set up an alert as described in this section.</span></span>

1. <span data-ttu-id="14a36-312">In the Microsoft 365 Defender portal at <https://security.microsoft.com> ， go to Email & **collaboration** \> **Policys & alert** \> **policy**.</span><span class="sxs-lookup"><span data-stu-id="14a36-312">In the Microsoft 365 Defender portal at <https://security.microsoft.com>, go to **Email & collaboration** \> **Polices & rules** \> **Alert policy**.</span></span>

2. <span data-ttu-id="14a36-313">在"**警报策略"** 页上，单击"**新建警报策略"。**</span><span class="sxs-lookup"><span data-stu-id="14a36-313">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="14a36-314">将 **打开"新建警报策略** "向导。</span><span class="sxs-lookup"><span data-stu-id="14a36-314">The **New alert policy** wizard opens.</span></span> <span data-ttu-id="14a36-315">在" **名称** "页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-315">On the **Name** page, configure the following settings:</span></span>
   - <span data-ttu-id="14a36-316">**名称**：输入唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="14a36-316">**Name**: Enter a unique and descriptive name.</span></span> <span data-ttu-id="14a36-317">比如，你可以在库中键入恶意文件。</span><span class="sxs-lookup"><span data-stu-id="14a36-317">For example, you could type Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="14a36-318">**说明**：输入可选说明。</span><span class="sxs-lookup"><span data-stu-id="14a36-318">**Description**: Enter an optional description.</span></span>
   - <span data-ttu-id="14a36-319">**严重性：** 选择 **低**、**中或\*\*\*\*高**。</span><span class="sxs-lookup"><span data-stu-id="14a36-319">**Severity**: Select **Low**, **Medium** or **High**.</span></span>
   - <span data-ttu-id="14a36-320">**类别**：选择 **威胁管理**。</span><span class="sxs-lookup"><span data-stu-id="14a36-320">**Category**: Select **Threat management**.</span></span>

   <span data-ttu-id="14a36-321">完成后，单击"下一 **步"**</span><span class="sxs-lookup"><span data-stu-id="14a36-321">When you're finished, click **Next**</span></span>

4. <span data-ttu-id="14a36-322">在" **创建警报设置"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-322">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="14a36-323">**要提醒什么？** section： **Activity is** Detected malware in \> **file**.</span><span class="sxs-lookup"><span data-stu-id="14a36-323">**What do you want to alert on?** section: **Activity is** \> **Detected malware in file**.</span></span>
   - <span data-ttu-id="14a36-324">**您希望如何触发警报** 部分 **：每次选择** 活动匹配规则时验证。</span><span class="sxs-lookup"><span data-stu-id="14a36-324">**How do you want the alert to be triggered** section: Verify **Every time an activity matches the rule** is selected.</span></span>

   <span data-ttu-id="14a36-325">完成后，单击"下一 **步"**</span><span class="sxs-lookup"><span data-stu-id="14a36-325">When you're finished, click **Next**</span></span>

5. <span data-ttu-id="14a36-326">在 **"设置收件人"** 页上，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="14a36-326">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="14a36-327">**发送电子邮件通知**：验证此设置是否已选择。</span><span class="sxs-lookup"><span data-stu-id="14a36-327">**Send email notifications**: Verify this setting is selcted.</span></span>
   - <span data-ttu-id="14a36-328">**电子邮件收件人**：选择一个或多个全局管理员、安全管理员或安全读者，他们应在检测到恶意文件时收到通知。</span><span class="sxs-lookup"><span data-stu-id="14a36-328">**Email recipients**: Select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="14a36-329">**每日通知限制**：验证 **未选择** 限制。</span><span class="sxs-lookup"><span data-stu-id="14a36-329">**Daily notification limit**: Verify **No limit** is selected.</span></span>

   <span data-ttu-id="14a36-330">完成后，单击"下一 **步"**</span><span class="sxs-lookup"><span data-stu-id="14a36-330">When you're finished, click **Next**</span></span>

6. <span data-ttu-id="14a36-331">在" **查看设置"** 页上，查看设置，验证"是， **立即** 打开"已选中，然后单击"完成 **"**</span><span class="sxs-lookup"><span data-stu-id="14a36-331">On the **Review your settings** page, review your settings, verify **Yes, turn it on right away** is selected, and then click **Finish**</span></span>

<span data-ttu-id="14a36-332">若要了解有关警报策略的更多信息，请参阅警报[策略Microsoft 365 合规中心。](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="14a36-332">To learn more about alert policies, see [Alert policies in the Microsoft 365 compliance center](../../compliance/alert-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="14a36-333">当你完成配置时，使用这些链接开始工作负载调查：</span><span class="sxs-lookup"><span data-stu-id="14a36-333">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="14a36-334">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="14a36-334">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="14a36-335">使用 Microsoft 365 Defender 门户在 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="14a36-335">Use the Microsoft 365 Defender portal to manage quarantined files in Defender for Office 365</span></span>](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [<span data-ttu-id="14a36-336">在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到恶意文件需采取的操作</span><span class="sxs-lookup"><span data-stu-id="14a36-336">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="14a36-337">在 Microsoft 365 中以管理员身份管理已隔离邮件和文件</span><span class="sxs-lookup"><span data-stu-id="14a36-337">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="14a36-338">安装后任务和接下来的步骤</span><span class="sxs-lookup"><span data-stu-id="14a36-338">Post-setup tasks and next steps</span></span>

<span data-ttu-id="14a36-339">配置威胁防护功能之后，确保监控这些功能的运行情况！</span><span class="sxs-lookup"><span data-stu-id="14a36-339">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="14a36-340">检查并修改你的策略，让它们按你的需求运行。</span><span class="sxs-lookup"><span data-stu-id="14a36-340">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="14a36-341">同时，关注可以增加价值的新功能和服务。</span><span class="sxs-lookup"><span data-stu-id="14a36-341">Also, watch for new features and service updates that can add value.</span></span>

<br>

****

|<span data-ttu-id="14a36-342">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="14a36-342">What to do</span></span>|<span data-ttu-id="14a36-343">了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="14a36-343">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="14a36-344">通过查看报告了解威胁防护功能如何为你的阻止工作</span><span class="sxs-lookup"><span data-stu-id="14a36-344">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="14a36-345">电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="14a36-345">Email security reports</span></span>](view-email-security-reports.md) <p> [<span data-ttu-id="14a36-346">Microsoft Defender for Office 365 报告</span><span class="sxs-lookup"><span data-stu-id="14a36-346">Reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md) <p> [<span data-ttu-id="14a36-347">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="14a36-347">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="14a36-348">定期检查和修改你的威胁防护策略（如有需要）</span><span class="sxs-lookup"><span data-stu-id="14a36-348">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="14a36-349">安全功能分数</span><span class="sxs-lookup"><span data-stu-id="14a36-349">Secure Score</span></span>](../defender/microsoft-secure-score.md) <p> [<span data-ttu-id="14a36-350">Microsoft 365 威胁调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="14a36-350">Microsoft 365 threat investigation and response features</span></span>](./office-365-ti.md)|
|<span data-ttu-id="14a36-351">关注新功能和服务更新</span><span class="sxs-lookup"><span data-stu-id="14a36-351">Watch for new features and service updates</span></span>|[<span data-ttu-id="14a36-352">标准和目标发布选项</span><span class="sxs-lookup"><span data-stu-id="14a36-352">Standard and Targeted release options</span></span>](../../admin/manage/release-options-in-office-365.md) <p> [<span data-ttu-id="14a36-353">消息中心</span><span class="sxs-lookup"><span data-stu-id="14a36-353">Message Center</span></span>](../../admin/manage/message-center.md) <p> [<span data-ttu-id="14a36-354">Microsoft 365 路线图</span><span class="sxs-lookup"><span data-stu-id="14a36-354">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [<span data-ttu-id="14a36-355">服务说明</span><span class="sxs-lookup"><span data-stu-id="14a36-355">Service Descriptions</span></span>](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
