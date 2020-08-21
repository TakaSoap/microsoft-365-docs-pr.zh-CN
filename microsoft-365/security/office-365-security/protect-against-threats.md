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
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Microsoft 365 中的威胁防护，并配置如何将其用于组织。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8f1cecbb3141b4751778212025e5aad582707e12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826821"
---
# <a name="protect-against-threats"></a><span data-ttu-id="fba86-103">保护免遭威胁侵害</span><span class="sxs-lookup"><span data-stu-id="fba86-103">Protect against threats</span></span>

<span data-ttu-id="fba86-104">Microsoft 365 包括各种威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="fba86-104">Microsoft 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="fba86-105">下面是一个快速入门指南，你可以将其用作清单，以确保你的威胁防护功能已针对你的组织做了设置。</span><span class="sxs-lookup"><span data-stu-id="fba86-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="fba86-106">如果你不确定出 Office 365 中的威胁防护功能，或者不只是你不确定从哪里开始使用，请使用以下指南作为起点。</span><span class="sxs-lookup"><span data-stu-id="fba86-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fba86-107">**初始建议设置包括每种策略类型;但是，许多可用选项**，您可以根据特定组织的需求调整设置。</span><span class="sxs-lookup"><span data-stu-id="fba86-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="fba86-108">对于策略或更改大约 30 分钟，也可以使用更改来完成数据中心。</span><span class="sxs-lookup"><span data-stu-id="fba86-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="fba86-109">Requirements</span><span class="sxs-lookup"><span data-stu-id="fba86-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="fba86-110">订阅</span><span class="sxs-lookup"><span data-stu-id="fba86-110">Subscriptions</span></span>

<span data-ttu-id="fba86-111">所有 Microsoft 365 订阅中均包含威胁防护功能;但是，某些订阅包含更高级的功能。</span><span class="sxs-lookup"><span data-stu-id="fba86-111">Threat protection features are included in all Microsoft 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="fba86-112">下表列出了本文中包含的保护功能以及最低订阅要求。</span><span class="sxs-lookup"><span data-stu-id="fba86-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span>

****

|<span data-ttu-id="fba86-113">保护类型</span><span class="sxs-lookup"><span data-stu-id="fba86-113">Protection type</span></span>|<span data-ttu-id="fba86-114">订阅要求</span><span class="sxs-lookup"><span data-stu-id="fba86-114">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="fba86-115">反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="fba86-115">Anti-malware protection</span></span>|<span data-ttu-id="fba86-116">[使用](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) EOP 管理 (Exchange Online) </span><span class="sxs-lookup"><span data-stu-id="fba86-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="fba86-117">防止电子邮件和 Office 文档中的恶意 URL 和文件</span><span class="sxs-lookup"><span data-stu-id="fba86-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="fba86-118">[Office 365 高级威胁防](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 护 (ATP) </span><span class="sxs-lookup"><span data-stu-id="fba86-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="fba86-119">防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="fba86-119">Anti-phishing protection</span></span>|[<span data-ttu-id="fba86-120">EOP</span><span class="sxs-lookup"><span data-stu-id="fba86-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="fba86-121">高级防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="fba86-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="fba86-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="fba86-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="fba86-123">反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="fba86-123">Anti-spam protection</span></span>|[<span data-ttu-id="fba86-124">EOP</span><span class="sxs-lookup"><span data-stu-id="fba86-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="fba86-125">电子邮件加密的零时 (自动清除) </span><span class="sxs-lookup"><span data-stu-id="fba86-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="fba86-126">EOP</span><span class="sxs-lookup"><span data-stu-id="fba86-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="fba86-127">审核 (用于报告目) </span><span class="sxs-lookup"><span data-stu-id="fba86-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="fba86-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fba86-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="fba86-129">角色和权限</span><span class="sxs-lookup"><span data-stu-id="fba86-129">Roles and permissions</span></span>

<span data-ttu-id="fba86-130">您必须分配有适当的角色，才能在安全与 [合规&中配置策略](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="fba86-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="fba86-131">下表提供一些示例：</span><span class="sxs-lookup"><span data-stu-id="fba86-131">The following table includes some examples:</span></span>

****

|<span data-ttu-id="fba86-132">角色或角色组</span><span class="sxs-lookup"><span data-stu-id="fba86-132">Role or role group</span></span>|<span data-ttu-id="fba86-133">了解详细信息在哪里</span><span class="sxs-lookup"><span data-stu-id="fba86-133">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="fba86-134">全局管理员</span><span class="sxs-lookup"><span data-stu-id="fba86-134">global administrator</span></span>|[<span data-ttu-id="fba86-135">关于 Microsoft 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="fba86-135">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="fba86-136">安全管理员</span><span class="sxs-lookup"><span data-stu-id="fba86-136">Security Administrator</span></span>|[<span data-ttu-id="fba86-137">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="fba86-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="fba86-138">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="fba86-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="fba86-139">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="fba86-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="fba86-140">和</span><span class="sxs-lookup"><span data-stu-id="fba86-140">and</span></span><br> [<span data-ttu-id="fba86-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="fba86-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="fba86-142">若要了解详细信息，请参阅 [安全合规中心 &amp; 中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="fba86-142">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="fba86-143">第 1 部分 - 反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="fba86-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="fba86-144">[反恶意软件保护](anti-malware-protection.md) 适用于包括 EOP 的 [订阅](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="fba86-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="fba86-145">在安全[与合规&，](https://protection.office.com)选择威**胁**  >  **管理**  >  **策略反恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="fba86-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="fba86-146">双击"默认 **"** 策略，**然后选择设置。**</span><span class="sxs-lookup"><span data-stu-id="fba86-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="fba86-147">指定下列设置：</span><span class="sxs-lookup"><span data-stu-id="fba86-147">Specify the following settings:</span></span>

    - <span data-ttu-id="fba86-148">在"**恶意软件检测响应"** 部分，保留默认设置"否 **"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="fba86-149">在"**常见附件类型筛选器"部分**中，选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="fba86-150">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fba86-150">Click **Save**.</span></span>

<span data-ttu-id="fba86-151">有关反恶意软件策略选项的详细信息，请参阅配置 [反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fba86-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="fba86-152">第 2 部分 - 防恶意 URL 和文件</span><span class="sxs-lookup"><span data-stu-id="fba86-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="fba86-153">来自恶意 URL 和文件的点击时保护适用于 [包括 Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) 的订阅，该订阅通过 ATP 安全附件和 [ATP](atp-safe-attachments.md) [安全链接](atp-safe-links.md) 策略进行设置。</span><span class="sxs-lookup"><span data-stu-id="fba86-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="fba86-154">ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="fba86-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="fba86-155">若要设置 [ATP 安全附件，](atp-safe-attachments.md)必须至少定义一个 ATP 安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="fba86-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="fba86-156">在安全[与合规&中心](https://protection.office.com)内，选择**威**  >  **胁管理**  >  **策略 ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="fba86-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="fba86-157">选择此选项 **"为 SharePoint、OneDrive 和 Microsoft Teams 打开 ATP"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="fba86-158">在" **保护电子邮件附件"** 部分中，单击加号 **+** () 。</span><span class="sxs-lookup"><span data-stu-id="fba86-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="fba86-159">指定下列设置：</span><span class="sxs-lookup"><span data-stu-id="fba86-159">Specify the following settings:</span></span>

   - <span data-ttu-id="fba86-160">在" **名称"** 框中，键入 `Block malware` .</span><span class="sxs-lookup"><span data-stu-id="fba86-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="fba86-161">在响应部分，选择"**阻止"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="fba86-162">在" **重定向附件** "部分，选择 **"启用重定向"** 选项，然后为组织的安全管理员或话务员指定电子邮件地址，以查看检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="fba86-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="fba86-163">在"**适用于"部分**，选择"**收件人域为"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="fba86-164">然后，选择您的域，选择"**添加"，** 然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="fba86-165">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fba86-165">Click **Save**.</span></span>

6. <span data-ttu-id="fba86-166"> (**建议的额外**) 作为全局管理员或 SharePoint Online 管理员，为 Microsoft 365 环境运行**[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet，**将 DisallowInfectedFileDownload**参数设置为*true。*</span><span class="sxs-lookup"><span data-stu-id="fba86-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="fba86-167"> (这会防止用户打开、移动、复制或共享检测为恶意文件) </span><span class="sxs-lookup"><span data-stu-id="fba86-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="fba86-168">若要了解详细信息，请参阅["设置 Office 365 ATP 安全附件"策略，](set-up-atp-safe-attachments-policies.md)[并启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP。](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="fba86-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="fba86-169">ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="fba86-169">ATP Safe Links policies</span></span>

<span data-ttu-id="fba86-170">若要设置 [ATP 安全链接，](atp-safe-links.md)请查看和编辑默认策略，并为特定用户添加策略。</span><span class="sxs-lookup"><span data-stu-id="fba86-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="fba86-171">在安全[与合规&，](https://protection.office.com)选择 **"威**  >  **胁管理策略**  >  **ATP 安全链接"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="fba86-172">双击"默认 **"** 策略。</span><span class="sxs-lookup"><span data-stu-id="fba86-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="fba86-173">在"**部分中使用安全链接"** 部分中，选择 **"Microsoft 365 企业应用版、Office for iOS"和"Outlook for Android"，** 然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-173">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="fba86-174">在" **适用于特定收件人的策略"** 部分，单击加号 **+** () 。</span><span class="sxs-lookup"><span data-stu-id="fba86-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="fba86-175">指定下列设置：</span><span class="sxs-lookup"><span data-stu-id="fba86-175">Specify the following settings:</span></span>

   - <span data-ttu-id="fba86-176">在" **名称** "框中，键入名称，如 `Safe Links` 。</span><span class="sxs-lookup"><span data-stu-id="fba86-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="fba86-177">在"**选择操作"部分中**，选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="fba86-178">选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="fba86-178">Select these options:</span></span>

     - <span data-ttu-id="fba86-179">**使用安全附件扫描可下载的内容**</span><span class="sxs-lookup"><span data-stu-id="fba86-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="fba86-180">**向组织内发送的电子邮件应用安全链接**</span><span class="sxs-lookup"><span data-stu-id="fba86-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="fba86-181">**不允许用户单击至原始 URL 的安全链接**</span><span class="sxs-lookup"><span data-stu-id="fba86-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="fba86-182">在"**适用于"部分**，选择"**收件人域为"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="fba86-183">然后，选择您的域，选择"**添加"，** 然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="fba86-184">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fba86-184">Click **Save**.</span></span>

<span data-ttu-id="fba86-185">若要了解详细信息，请参阅[设置 Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fba86-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="fba86-186">第 3 部分 - 防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="fba86-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="fba86-187">[反网络钓鱼]</span><span class="sxs-lookup"><span data-stu-id="fba86-187">[Anti-phishing]</span></span>

<span data-ttu-id="fba86-188">[在包括 EOP 的订阅中提供](anti-phishing-protection.md) 反网络钓鱼 [保护](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="fba86-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="fba86-189">ATP 中提供高级反网络 [钓鱼保护](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="fba86-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="fba86-190">以下过程将介绍如何配置 ATP 防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="fba86-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="fba86-191">这些步骤类似于在不包括 ATP 策略的情况下配置 (网络钓鱼) 。</span><span class="sxs-lookup"><span data-stu-id="fba86-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="fba86-192">在安全[与&中心内，](https://protection.office.com)选择**威**  >  **胁**  >  **管理策略 ATP 防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="fba86-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="fba86-193">单击 **"默认策略"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="fba86-194">在" **模拟"部分** ，单击" **编辑"，** 然后指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="fba86-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="fba86-195">在" **添加要保护的用户"** 选项卡上，打开保护。</span><span class="sxs-lookup"><span data-stu-id="fba86-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="fba86-196">然后添加用户，如组织的主层成员、CEO、CFO 和其他更高层领导。</span><span class="sxs-lookup"><span data-stu-id="fba86-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="fba86-197"> (您可以键入单个电子邮件地址，或单击以显示 list.) </span><span class="sxs-lookup"><span data-stu-id="fba86-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="fba86-198">在"**添加域以保护"** 选项卡上，启用 **"自动包含我自己的域"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="fba86-199">如果您有自定义域，则也请添加这些域。</span><span class="sxs-lookup"><span data-stu-id="fba86-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="fba86-200">在 **"** 操作"选项卡上 **，选择模拟用户**和**模拟域**选项**的"隔离邮件"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="fba86-201">此外，打开模拟安全提示。</span><span class="sxs-lookup"><span data-stu-id="fba86-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="fba86-202">在 **"邮箱智能** "选项卡上，确保邮箱智能处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="fba86-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="fba86-203">此外，启用基于邮箱智能的模拟保护。</span><span class="sxs-lookup"><span data-stu-id="fba86-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="fba86-204">在 **"如果电子邮件是由模拟用户列表发送**"中，请**选择"隔离邮件"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="fba86-205">在" **添加受信任的发件人和域** "选项卡上，指定要添加的任何受信任的发件人或域。</span><span class="sxs-lookup"><span data-stu-id="fba86-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="fba86-206">在"**查看设置"** 选项卡上，查看设置后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="fba86-207">在" **欺骗"** 部分， **单击"编辑**"，然后指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="fba86-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="fba86-208">在 **"欺骗检查** 设置"选项卡上，请确保启用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="fba86-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="fba86-209">在 **"操作**"**选项卡上，选择"隔离邮件"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="fba86-210">在"**查看设置"** 选项卡上，查看设置后，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="fba86-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="fba86-211"> (如果未进行任何更改，请单击 **"取消**.) </span><span class="sxs-lookup"><span data-stu-id="fba86-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="fba86-212">关闭默认的策略设置页。</span><span class="sxs-lookup"><span data-stu-id="fba86-212">Close the default policy settings page.</span></span>

<span data-ttu-id="fba86-213">若要了解有关反网络钓鱼策略选项的详细信息，请参阅配置 [ATP 防钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fba86-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="fba86-214">第 4 部分 - 反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="fba86-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="fba86-215">[反垃圾邮件保护](anti-spam-protection.md) 适用于包括 EOP 在内的 [订阅](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)中。</span><span class="sxs-lookup"><span data-stu-id="fba86-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="fba86-216">在安全[与合规&，](https://protection.office.com)选择威**胁**  >  **管理**  >  **策略反垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="fba86-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="fba86-217">在" **自定义"** 选项卡上，打开 **"自定义设置** "。</span><span class="sxs-lookup"><span data-stu-id="fba86-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="fba86-218">展开 **"默认垃圾邮件筛选策略**"、单击 **"编辑策略**"，然后指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="fba86-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="fba86-219">在" **垃圾邮件和批量操作"** 部分，将阈值设为 5 或 6。</span><span class="sxs-lookup"><span data-stu-id="fba86-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="fba86-220">在" **允许列表"** 部分， (根据需要编辑) 允许发件人和域。</span><span class="sxs-lookup"><span data-stu-id="fba86-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="fba86-221">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fba86-221">Click **Save**.</span></span>

<span data-ttu-id="fba86-222">若要详细了解反垃圾邮件策略选项，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fba86-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="fba86-223">第 5 部分 - 要配置的其他设置</span><span class="sxs-lookup"><span data-stu-id="fba86-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="fba86-224">除了配置防止恶意软件、恶意 URL 和文件、网络钓鱼和垃圾邮件的保护，我们建议配置零时差自动清除和审核日志记录设置。</span><span class="sxs-lookup"><span data-stu-id="fba86-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="fba86-225">电子邮件的零时差自动清除</span><span class="sxs-lookup"><span data-stu-id="fba86-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="fba86-226">[零时差自动清除 (](zero-hour-auto-purge.md) ZAP) 包括 EOP 的订阅 [中可用](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="fba86-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="fba86-227">此保护默认处于打开状态;但是，保护必须满足以下条件才能生效：</span><span class="sxs-lookup"><span data-stu-id="fba86-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="fba86-228">在反垃圾邮件策略中 **，垃圾邮件操作被设置为"将邮件**[移动到"垃圾邮件"文件夹](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="fba86-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="fba86-229">用户保留了他们的默认 [垃圾邮件设置，](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)但未关闭垃圾邮件保护。</span><span class="sxs-lookup"><span data-stu-id="fba86-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="fba86-230">若要了解详细信息， [请参阅零时差自动清除 - 防范垃圾邮件和恶意软件](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="fba86-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="fba86-231">报告和调查的审核日志记录</span><span class="sxs-lookup"><span data-stu-id="fba86-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="fba86-232">审核日志记录在包括 Exchange Online 的订阅 [中可用](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)。</span><span class="sxs-lookup"><span data-stu-id="fba86-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="fba86-233">为了查看威胁防护报告中的数据（如 [安全仪表板](security-dashboard.md)、 [电子邮件安全报告](view-email-security-reports.md)和 [资源](threat-explorer.md)管理器），必须为组织启用审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="fba86-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="fba86-234">若要了解详细信息，[请参阅审核日志打开或关闭搜索。](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="fba86-234">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="fba86-235">安装后任务</span><span class="sxs-lookup"><span data-stu-id="fba86-235">Post-setup tasks</span></span>

<span data-ttu-id="fba86-236">在配置威胁防护功能之后，请确保监视这些功能的运行方式、根据需要审核并修订策略，并观察新的功能和服务更新。</span><span class="sxs-lookup"><span data-stu-id="fba86-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

****

|<span data-ttu-id="fba86-237">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="fba86-237">What to do</span></span>|<span data-ttu-id="fba86-238">了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="fba86-238">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="fba86-239">查看报告，了解威胁防护功能如何对组织工作</span><span class="sxs-lookup"><span data-stu-id="fba86-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="fba86-240">安全仪表板</span><span class="sxs-lookup"><span data-stu-id="fba86-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="fba86-241">电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="fba86-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="fba86-242">Office 365 ATP 报告</span><span class="sxs-lookup"><span data-stu-id="fba86-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="fba86-243">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="fba86-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="fba86-244">定期检查并修改威胁防护策略（如果需要）</span><span class="sxs-lookup"><span data-stu-id="fba86-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="fba86-245">安全功能分数</span><span class="sxs-lookup"><span data-stu-id="fba86-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="fba86-246">智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="fba86-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="fba86-247">Microsoft 365 威胁调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="fba86-247">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="fba86-248">观看新增功能和服务更新</span><span class="sxs-lookup"><span data-stu-id="fba86-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="fba86-249">标准和定向发布选项</span><span class="sxs-lookup"><span data-stu-id="fba86-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="fba86-250">消息中心</span><span class="sxs-lookup"><span data-stu-id="fba86-250">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="fba86-251">Microsoft 365 路线图</span><span class="sxs-lookup"><span data-stu-id="fba86-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="fba86-252">服务说明</span><span class="sxs-lookup"><span data-stu-id="fba86-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
