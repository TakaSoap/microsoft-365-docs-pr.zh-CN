---
title: 保护免遭威胁侵害
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Microsoft 365 中的威胁防护，并配置如何将其用于组织。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ad74e9bdcd7b937873108d2ba049c16db8c235b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202575"
---
# <a name="protect-against-threats"></a><span data-ttu-id="a5bcb-103">保护免遭威胁侵害</span><span class="sxs-lookup"><span data-stu-id="a5bcb-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a5bcb-104">下面是一个快速入门指南，用于将高级威胁防护的配置分解为多个块。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-104">Here's a quick-start guide that breaks the configuration of Advanced Threat Protection into chunks.</span></span> <span data-ttu-id="a5bcb-105">如果你刚开始使用 Office 365 中的威胁防护功能，则不确定从哪里开始，或者如果你了解 *最佳方法，* 请使用本指南作为检查表和起点。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-105">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5bcb-106">**为每种策略提供了初始推荐设置; 但是，有许多可用选项，您可以调整设置以满足特定组织的需求**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-106">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="a5bcb-107">为你的策略或更改允许大约30分钟，以在你的数据中心中工作。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-107">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="a5bcb-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="a5bcb-108">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="a5bcb-109">订阅</span><span class="sxs-lookup"><span data-stu-id="a5bcb-109">Subscriptions</span></span>

<span data-ttu-id="a5bcb-110">威胁防护功能包含在 *所有* Microsoft 或 Office 365 订阅中;但是，有些订阅具有高级功能。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-110">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="a5bcb-111">下表列出了本文附带的保护功能以及最低订阅要求。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-111">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="a5bcb-112">请注意，除了打开审核的说明之外， *步骤* 还启动反恶意软件、反网络钓鱼和反垃圾邮件，它们被标记为 Office 365 Exchange Online Protection (**EOP**) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-112">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="a5bcb-113">这在高级威胁防护文章中似乎是不正常的，除非您记下高级威胁防护 (**ATP**) 包含，并在 EOP 中进行构建。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-113">This can seem odd in an Advanced Threat Protection article, until you remember Advanced Threat Protection (**ATP**) contains, and builds on, EOP.</span></span>

****

|<span data-ttu-id="a5bcb-114">保护类型</span><span class="sxs-lookup"><span data-stu-id="a5bcb-114">Protection type</span></span>|<span data-ttu-id="a5bcb-115">订阅要求</span><span class="sxs-lookup"><span data-stu-id="a5bcb-115">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="a5bcb-116">用于报告目的的审核日志记录 () </span><span class="sxs-lookup"><span data-stu-id="a5bcb-116">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="a5bcb-117">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a5bcb-117">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="a5bcb-118">反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="a5bcb-118">Anti-malware protection</span></span>|<span data-ttu-id="a5bcb-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**) </span><span class="sxs-lookup"><span data-stu-id="a5bcb-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="a5bcb-120">防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="a5bcb-120">Anti-phishing protection</span></span>|[<span data-ttu-id="a5bcb-121">EOP</span><span class="sxs-lookup"><span data-stu-id="a5bcb-121">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="a5bcb-122">反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="a5bcb-122">Anti-spam protection</span></span>|[<span data-ttu-id="a5bcb-123">EOP</span><span class="sxs-lookup"><span data-stu-id="a5bcb-123">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="a5bcb-124">电子邮件的零小时自动清除 () </span><span class="sxs-lookup"><span data-stu-id="a5bcb-124">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="a5bcb-125">EOP</span><span class="sxs-lookup"><span data-stu-id="a5bcb-125">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="a5bcb-126">防止电子邮件和 Office 文档中的恶意 Url 和文件 (安全链接和安全附件) </span><span class="sxs-lookup"><span data-stu-id="a5bcb-126">Protection from malicious URLs and files in email and Office documents (safe links and safe attachments)</span></span>|<span data-ttu-id="a5bcb-127">[Office 365 高级威胁防护](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**) </span><span class="sxs-lookup"><span data-stu-id="a5bcb-127">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)</span></span>|
|<span data-ttu-id="a5bcb-128">为 SharePoint、OneDrive 和 Microsoft 团队工作负荷启用 ATP</span><span class="sxs-lookup"><span data-stu-id="a5bcb-128">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>| [<span data-ttu-id="a5bcb-129">ATP</span><span class="sxs-lookup"><span data-stu-id="a5bcb-129">ATP</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide)|
|<span data-ttu-id="a5bcb-130">高级反网络钓鱼防护</span><span class="sxs-lookup"><span data-stu-id="a5bcb-130">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="a5bcb-131">ATP</span><span class="sxs-lookup"><span data-stu-id="a5bcb-131">ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="a5bcb-132">角色和权限</span><span class="sxs-lookup"><span data-stu-id="a5bcb-132">Roles and permissions</span></span>

<span data-ttu-id="a5bcb-133">若要配置 ATP 策略，必须在 [安全 & 合规性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)中为您分配适当的角色。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-133">To configure ATP policies, you must be assigned an appropriate role in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="a5bcb-134">有关可执行这些操作的角色，请查看下面的表格。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-134">Take a look at the table below for roles that can do these actions.</span></span>

****

|<span data-ttu-id="a5bcb-135">角色或角色组</span><span class="sxs-lookup"><span data-stu-id="a5bcb-135">Role or role group</span></span>|<span data-ttu-id="a5bcb-136">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="a5bcb-136">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="a5bcb-137">全局管理员</span><span class="sxs-lookup"><span data-stu-id="a5bcb-137">global administrator</span></span>|[<span data-ttu-id="a5bcb-138">关于 Microsoft 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="a5bcb-138">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="a5bcb-139">安全管理员</span><span class="sxs-lookup"><span data-stu-id="a5bcb-139">Security Administrator</span></span>|[<span data-ttu-id="a5bcb-140">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="a5bcb-140">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="a5bcb-141">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="a5bcb-141">Exchange Online Organization Management</span></span>|[<span data-ttu-id="a5bcb-142">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="a5bcb-142">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="a5bcb-143">和</span><span class="sxs-lookup"><span data-stu-id="a5bcb-143">and</span></span><br> [<span data-ttu-id="a5bcb-144">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5bcb-144">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="a5bcb-145">若要了解详细信息，请参阅 [安全 &amp; 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-145">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="a5bcb-146">在开始之前，请启用报告和调查的审核日志记录</span><span class="sxs-lookup"><span data-stu-id="a5bcb-146">Before you begin, turn on Audit logging for reporting and investigation</span></span>

<span data-ttu-id="a5bcb-147">尽早启动审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-147">Start your audit logging early.</span></span> <span data-ttu-id="a5bcb-148">您 **需要进行审核** ，以确保执行后续步骤。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-148">You'll need auditing to be **ON** for certain of the steps that follow.</span></span> <span data-ttu-id="a5bcb-149">审核日志记录在包括 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-149">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="a5bcb-150">为了查看威胁防护报告中的数据（如 [安全仪表板](security-dashboard.md)、 [电子邮件安全报告](view-email-security-reports.md)和 [浏览器](threat-explorer.md)），审核日志记录必须 *打开*。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-150">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="a5bcb-151">若要了解详细信息，请参阅 [打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-151">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="a5bcb-152">第1部分-反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="a5bcb-152">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="a5bcb-153">[反恶意软件保护](anti-malware-protection.md) 在包含 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-153">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="a5bcb-154">在[安全 & 合规性中心](https://protection.office.com)中，选择 "**威胁管理**  >  **策略**  >  **反恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-154">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="a5bcb-155">双击 **默认** 策略，然后选择 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-155">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="a5bcb-156">指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="a5bcb-156">Specify the following settings:</span></span>

    - <span data-ttu-id="a5bcb-157">在 " **恶意软件检测响应** " 部分，保留默认设置 " **否**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-157">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="a5bcb-158">在 " **常见附件类型筛选器** " 部分，选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-158">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="a5bcb-159">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-159">Click **Save**.</span></span>

<span data-ttu-id="a5bcb-160">若要了解有关反恶意软件策略选项的详细信息，请参阅 [配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-160">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection"></a><span data-ttu-id="a5bcb-161">第2部分-反网络钓鱼防护</span><span class="sxs-lookup"><span data-stu-id="a5bcb-161">Part 2 - Anti-phishing protection</span></span>

<span data-ttu-id="a5bcb-162">[反钓鱼]</span><span class="sxs-lookup"><span data-stu-id="a5bcb-162">[Anti-phishing]</span></span>

<span data-ttu-id="a5bcb-163">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的订阅中提供了[反网络钓鱼保护](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-163">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="a5bcb-164">在 [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中提供高级反钓鱼保护。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-164">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="a5bcb-165">以下过程介绍如何配置 ATP 反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-165">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="a5bcb-166">在不使用 ATP) 配置反网络钓鱼策略 (的步骤类似。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-166">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="a5bcb-167">在[安全 & 合规性中心](https://protection.office.com)中，选择**威胁管理**  >  **策略**  >  **ATP 反网络钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-167">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="a5bcb-168">单击 " **默认策略**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-168">Click **Default policy**.</span></span>

3. <span data-ttu-id="a5bcb-169">在 " **模拟** " 部分，单击 " **编辑**"，然后指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="a5bcb-169">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="a5bcb-170">在 " **添加要保护的用户** " 选项 *卡上，打开保护* 。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-170">On the **Add users to protect** tab, turn *On* protection.</span></span> <span data-ttu-id="a5bcb-171">然后添加用户，如贵组织的董事会成员、CEO、CFO 和其他高级领导者。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-171">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="a5bcb-172"> (您可以键入单个电子邮件地址，或单击以显示列表。 ) </span><span class="sxs-lookup"><span data-stu-id="a5bcb-172">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="a5bcb-173">在 " **要保护的添加域** " 选项卡上，打开 " **自动包括我拥有的域"**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-173">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="a5bcb-174">如果你有自定义域，请立即添加。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-174">If you have custom domains, add them now.</span></span>

   - <span data-ttu-id="a5bcb-175">在 "**操作**" 选项卡上，选择 "隔离**模拟用户**和**模拟域**的**邮件"** 选项。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-175">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="a5bcb-176">此外，打开模拟安全提示。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-176">Also, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="a5bcb-177">在 " **邮箱智能** " 选项卡上，确保已打开邮箱智能，并启用基于邮箱智能的模拟保护。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-177">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on and turn on mailbox intelligence-based impersonation protection.</span></span> <span data-ttu-id="a5bcb-178">在 " **如果模拟用户发送电子邮件** " 列表中，选择 **"隔离邮件"**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-178">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="a5bcb-179">在 " **添加受信任的发件人和域** " 选项卡上，指定要添加的任何受信任的发件人或域。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-179">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="a5bcb-180">查看设置后，**保存**在 "**查看您的设置**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-180">**Save** on the **Review your settings** tab after you've reviewed your settings.</span></span>

4. <span data-ttu-id="a5bcb-181">在 " **欺骗** " 部分，单击 " **编辑**"，然后指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="a5bcb-181">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="a5bcb-182">在 " **哄骗筛选器设置** " 选项卡上，确保已打开 "反欺骗保护"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-182">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="a5bcb-183">在 " **操作** " 选项卡上，选择 " **隔离邮件"**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-183">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="a5bcb-184">在审阅完更改后，**保存**在 "**查看您的设置**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-184">**Save** on the **Review your settings** tab after you have reviewed your changes.</span></span> <span data-ttu-id="a5bcb-185"> (如果未进行任何更改，请 **取消**。 ) </span><span class="sxs-lookup"><span data-stu-id="a5bcb-185">(If you didn't make any changes, **Cancel**.)</span></span>

5. <span data-ttu-id="a5bcb-186">关闭 "默认策略设置" 页。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-186">Close the default policy settings page.</span></span>

<span data-ttu-id="a5bcb-187">若要了解有关反网络钓鱼策略选项的详细信息，请参阅 [配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-187">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection"></a><span data-ttu-id="a5bcb-188">第3部分-反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="a5bcb-188">Part 3 - Anti-spam protection</span></span>

<span data-ttu-id="a5bcb-189">[反垃圾邮件保护](anti-spam-protection.md) 在包含 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-189">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="a5bcb-190">在[安全 & 合规性中心](https://protection.office.com)中，选择 "**威胁管理**  >  **策略**  >  **反垃圾邮件**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-190">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="a5bcb-191">在 " **自定义** " 选项卡上，打开 "自定义设置"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-191">On the **Custom** tab, turn on Custom settings.</span></span>

3. <span data-ttu-id="a5bcb-192">展开 " **默认垃圾邮件筛选器策略**"，单击 " **编辑策略**"，然后指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="a5bcb-192">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="a5bcb-193">在 " **垃圾邮件和批量操作** " 部分，将阈值设置为值5或6。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-193">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="a5bcb-194">在 " **允许列表** " 部分，查看 (和/或编辑) 您允许的发件人和域。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-194">In the **Allow lists** section, review (and/or edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="a5bcb-195">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-195">Click **Save**.</span></span>

<span data-ttu-id="a5bcb-196">若要了解有关您的反垃圾邮件策略选项的详细信息，请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-196">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments"></a><span data-ttu-id="a5bcb-197">第4部分-防止恶意 Url 和文件 (安全链接和安全附件) </span><span class="sxs-lookup"><span data-stu-id="a5bcb-197">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments)</span></span>

<span data-ttu-id="a5bcb-198">来自恶意 Url 和文件的点击时间保护在包含 [Office 365 atp](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (atp) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-198">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP).</span></span> <span data-ttu-id="a5bcb-199">它通过 [Atp 安全附件](atp-safe-attachments.md) 和 [atp 安全链接](atp-safe-links.md) 策略进行设置。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-199">It's set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="a5bcb-200">ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="a5bcb-200">ATP Safe Attachments policies</span></span>

<span data-ttu-id="a5bcb-201">若要设置 [Atp 安全附件](atp-safe-attachments.md)，必须至少定义一个 ATP 安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-201">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="a5bcb-202">在 "[安全性 & 合规性中心](https://protection.office.com)中，选择"**威胁管理**  >  **策略**  >  **ATP 安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-202">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="a5bcb-203">选择 " **打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP**" 选项。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-203">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="a5bcb-204">在 " **保护电子邮件附件** " 部分，单击加号 (**+**) 。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-204">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="a5bcb-205">指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="a5bcb-205">Specify the following settings:</span></span>

   - <span data-ttu-id="a5bcb-206">在 " **名称** " 框中，键入 `Block malware` 。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-206">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="a5bcb-207">在 "响应" 部分，选择 " **阻止**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-207">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="a5bcb-208">在 " **重定向附件** " 部分，选择 " **启用重定向**" 选项。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-208">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="a5bcb-209">指定组织的安全管理员或操作员的电子邮件地址，该地址将审阅检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-209">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

   - <span data-ttu-id="a5bcb-210">在 " **应用** 于" 部分中，选择 **"收件人域"**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-210">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="a5bcb-211">然后，选择您的域，选择 " **添加**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-211">Then, select your domain, choose **Add**, and then **OK**.</span></span>

5. <span data-ttu-id="a5bcb-212">**保存**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-212">**Save**.</span></span>

6. <span data-ttu-id="a5bcb-213"> (**建议的其他步骤**) 为全局管理员或 SharePoint Online 管理员，请运行 Microsoft 365 环境的**DisallowInfectedFileDownload**参数设置为*true*的**[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-213">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="a5bcb-214"> (这将阻止用户打开、移动、复制或共享被检测为恶意的文件 ) </span><span class="sxs-lookup"><span data-stu-id="a5bcb-214">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="a5bcb-215">若要了解详细信息，请参阅 [设置 office 365 Atp 安全附件策略](set-up-atp-safe-attachments-policies.md) 和 [打开 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-215">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="a5bcb-216">ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="a5bcb-216">ATP Safe Links policies</span></span>

<span data-ttu-id="a5bcb-217">若要设置 [ATP 安全链接](atp-safe-links.md)，请查看并编辑默认策略，并为特定用户添加策略。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-217">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="a5bcb-218">在 "[安全性 & 合规性中心](https://protection.office.com)中，选择"**威胁管理**  >  **策略**  >  **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-218">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a5bcb-219">双击 **默认** 策略。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-219">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="a5bcb-220">在 " **使用安全链接** " 部分，选择 " **Microsoft 365 Apps For enterprise，Office For iOS 和 Android**" 选项，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-220">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="a5bcb-221">在 " **适用于特定收件人的策略** " 部分，单击加号 (**+**) 。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-221">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="a5bcb-222">指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="a5bcb-222">Specify the following settings:</span></span>

   - <span data-ttu-id="a5bcb-223">在 " **名称** " 框中，键入一个名称，例如 `Safe Links` 。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-223">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="a5bcb-224">在 " **选择操作** " 部分，选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-224">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="a5bcb-225">选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="a5bcb-225">Select these options:</span></span>

     - <span data-ttu-id="a5bcb-226">**使用安全附件扫描可下载的内容**</span><span class="sxs-lookup"><span data-stu-id="a5bcb-226">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="a5bcb-227">**将安全链接应用于在组织内发送的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="a5bcb-227">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="a5bcb-228">**不要让用户通过指向原始 URL 的安全链接进行单击**</span><span class="sxs-lookup"><span data-stu-id="a5bcb-228">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="a5bcb-229">在 " **应用** 于" 部分中，选择 **"收件人域"**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-229">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="a5bcb-230">然后，选择您的域，选择 " **添加**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-230">Then, select your domain, choose **Add**, and then **OK**.</span></span>

6. <span data-ttu-id="a5bcb-231">**保存**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-231">**Save**.</span></span>

<span data-ttu-id="a5bcb-232">若要了解详细信息，请参阅[设置 Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-232">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads"></a><span data-ttu-id="a5bcb-233">第5部分-打开适用于 SharePoint、OneDrive 和 Microsoft 团队工作负荷的 ATP</span><span class="sxs-lookup"><span data-stu-id="a5bcb-233">Part 5 - Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>

<span data-ttu-id="a5bcb-234">SharePoint、OneDrive 和团队等工作负荷是为协作而构建的。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-234">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="a5bcb-235">使用 ATP 有助于阻止和检测在工作组网站和文档库中被标识为恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-235">Using ATP helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="a5bcb-236">您可以阅读有关 [此处](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide)的工作方式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-236">You can read more about how that works [here](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5bcb-237">在**开始此过程之前，请确保已为您的 Microsoft 365 环境启用审核日志记录**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-237">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="a5bcb-238">这通常由在 Exchange Online 中分配了审核日志角色的人完成。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-238">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="a5bcb-239">有关详细信息，请参阅 [打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)！</span><span class="sxs-lookup"><span data-stu-id="a5bcb-239">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="a5bcb-240">转到 <https://protection.office.com> ，然后使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-240">Go to <https://protection.office.com>, and sign in with your work or school account.</span></span>

2. <span data-ttu-id="a5bcb-241">在安全 & 合规性中心的左侧导航窗格中的 " **威胁管理**" 下，选择 " **策略** \> **安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-241">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![在安全 & 合规性中心中，选择威胁管理 \> 策略](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="a5bcb-243">选择 " **为 SharePoint、OneDrive 和 Microsoft 团队启用 ATP**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-243">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![为 SharePoint Online、OneDrive for Business 和 Microsoft 团队启用高级威胁防护](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="a5bcb-245">**保存**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-245">**Save**.</span></span>

5. <span data-ttu-id="a5bcb-246">查看 (，并根据需要编辑) 组织的 [安全附件策略](set-up-atp-safe-attachments-policies.md) 和 [安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-246">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="a5bcb-247"> (推荐) 为全局管理员或 SharePoint Online 管理员，请运行 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet，并将 _DisallowInfectedFileDownload_ 参数设置为 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-247">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="a5bcb-248">`$true` 阻止除 Delete) 检测到的文件之外的所有操作 (。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-248">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="a5bcb-249">用户无法打开、移动、复制或共享检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-249">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="a5bcb-250">`$false` 阻止除 "删除" 和 "下载" 以外的所有操作。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-250">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="a5bcb-251">用户可以选择接受风险并下载检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-251">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="a5bcb-252">若要了解有关在 Microsoft 365 中使用 PowerShell 的详细信息，请参阅使用 [Powershell 管理 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-252">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span></span>

7. <span data-ttu-id="a5bcb-253">允许最长30分钟，你的更改将传播到所有 Microsoft 365 数据中心。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-253">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="a5bcb-254">现在为检测到的文件设置通知</span><span class="sxs-lookup"><span data-stu-id="a5bcb-254">Now set up alerts for detected files</span></span>

<span data-ttu-id="a5bcb-255">若要在 SharePoint Online、OneDrive for Business 或 Microsoft 团队中的文件被标识为恶意文件时收到通知，可以设置警报。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-255">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="a5bcb-256">在 " [安全性 & 合规性中心](https://protection.office.com)中，选择" **通知**"" \> **管理通知**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-256">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="a5bcb-257">选择 " **新建警报策略**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-257">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="a5bcb-258">指定警报的名称。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-258">Specify a name for the alert.</span></span> <span data-ttu-id="a5bcb-259">例如，可以在库中键入恶意文件。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-259">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="a5bcb-260">键入警报的说明。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-260">Type a description for the alert.</span></span> <span data-ttu-id="a5bcb-261">例如，可以键入在 SharePoint Online、OneDrive 或 Microsoft 团队中检测到恶意文件时通知管理员。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-261">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="a5bcb-262">在 "在 **以下时间发送此通知** " 部分中，设置：</span><span class="sxs-lookup"><span data-stu-id="a5bcb-262">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="a5bcb-263">a.</span><span class="sxs-lookup"><span data-stu-id="a5bcb-263">a.</span></span> <span data-ttu-id="a5bcb-264">在 " **活动** " 列表中，选择 " **文件中检测到的恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-264">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="a5bcb-265">b.</span><span class="sxs-lookup"><span data-stu-id="a5bcb-265">b.</span></span> <span data-ttu-id="a5bcb-266">将 " **用户** " 字段留空。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-266">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="a5bcb-267">在 " **将此通知发送给 ...** " 部分，选择一个或多个全局管理员、安全管理员或在检测到恶意文件时应收到通知的安全阅读者。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-267">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="a5bcb-268">**保存**。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-268">**Save**.</span></span>

<span data-ttu-id="a5bcb-269">若要了解有关通知的详细信息，请参阅 [在安全 & 合规性中心中创建活动通知](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-269">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a5bcb-270">完成配置后，请使用以下链接启动工作负荷调查：</span><span class="sxs-lookup"><span data-stu-id="a5bcb-270">When you're finished configuring, use these links to start workload investigations:</span></span>
>
> - [<span data-ttu-id="a5bcb-271">查看有关在 SharePoint、OneDrive 或 Microsoft 团队中检测到的恶意文件的信息</span><span class="sxs-lookup"><span data-stu-id="a5bcb-271">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
> - [<span data-ttu-id="a5bcb-272">在 SharePoint Online、OneDrive 或 Microsoft 团队中找到恶意文件时要执行的操作</span><span class="sxs-lookup"><span data-stu-id="a5bcb-272">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
> - [<span data-ttu-id="a5bcb-273">在 Microsoft 365 中以管理员身份管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="a5bcb-273">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="a5bcb-274">第6部分-要配置的其他设置</span><span class="sxs-lookup"><span data-stu-id="a5bcb-274">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="a5bcb-275">通过对恶意软件、恶意 Url 和文件、网络钓鱼和垃圾邮件的保护进行配置，我们建议您配置零小时自动清除。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-275">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="a5bcb-276">EOP 中的电子邮件的零小时自动清除</span><span class="sxs-lookup"><span data-stu-id="a5bcb-276">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="a5bcb-277">[0 小时自动清除](zero-hour-auto-purge.md) (ZAP) 在包含 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-277">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="a5bcb-278">此保护在默认情况下处于启用状态。但是，若要使保护生效，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="a5bcb-278">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="a5bcb-279">垃圾邮件操作设置为将**邮件移动到**[反垃圾邮件策略](anti-spam-protection.md)中的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-279">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="a5bcb-280">用户保留其默认的 [垃圾邮件设置](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)，但尚未关闭垃圾邮件保护。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-280">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="a5bcb-281">若要了解详细信息，请参阅 [针对垃圾邮件和恶意软件的零小时自动清除保护](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-281">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="a5bcb-282">安装后任务和后续步骤</span><span class="sxs-lookup"><span data-stu-id="a5bcb-282">Post-setup tasks and next steps</span></span>

<span data-ttu-id="a5bcb-283">在配置威胁防护功能之后，请务必监视这些功能的工作方式！</span><span class="sxs-lookup"><span data-stu-id="a5bcb-283">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="a5bcb-284">查看和修订策略，以便他们可以执行所需的操作。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-284">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="a5bcb-285">此外，还请注意可添加值的新功能和服务更新。</span><span class="sxs-lookup"><span data-stu-id="a5bcb-285">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="a5bcb-286">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="a5bcb-286">What to do</span></span>|<span data-ttu-id="a5bcb-287">了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="a5bcb-287">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="a5bcb-288">查看报告的威胁防护功能是如何为你的组织工作的</span><span class="sxs-lookup"><span data-stu-id="a5bcb-288">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="a5bcb-289">安全仪表板</span><span class="sxs-lookup"><span data-stu-id="a5bcb-289">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="a5bcb-290">电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="a5bcb-290">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="a5bcb-291">Office 365 ATP 报告</span><span class="sxs-lookup"><span data-stu-id="a5bcb-291">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="a5bcb-292">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="a5bcb-292">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="a5bcb-293">根据需要定期查看和修改威胁防护策略</span><span class="sxs-lookup"><span data-stu-id="a5bcb-293">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="a5bcb-294">安全功能分数</span><span class="sxs-lookup"><span data-stu-id="a5bcb-294">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="a5bcb-295">智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="a5bcb-295">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="a5bcb-296">Microsoft 365 威胁调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="a5bcb-296">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="a5bcb-297">监视新功能和服务更新</span><span class="sxs-lookup"><span data-stu-id="a5bcb-297">Watch for new features and service updates</span></span>|[<span data-ttu-id="a5bcb-298">标准和目标发布选项</span><span class="sxs-lookup"><span data-stu-id="a5bcb-298">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="a5bcb-299">消息中心</span><span class="sxs-lookup"><span data-stu-id="a5bcb-299">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="a5bcb-300">Microsoft 365 路线图</span><span class="sxs-lookup"><span data-stu-id="a5bcb-300">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="a5bcb-301">服务说明</span><span class="sxs-lookup"><span data-stu-id="a5bcb-301">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="a5bcb-302">了解有关 EOP 和 ATP 的推荐标准和严格安全配置的详细信息</span><span class="sxs-lookup"><span data-stu-id="a5bcb-302">Learn the details about recommended Standard and Strict security configurations for EOP and ATP</span></span> | [<span data-ttu-id="a5bcb-303">EOP 和 Office 365 ATP 安全性的建议设置</span><span class="sxs-lookup"><span data-stu-id="a5bcb-303">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) |
