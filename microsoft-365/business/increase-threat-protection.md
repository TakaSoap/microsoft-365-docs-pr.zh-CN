---
title: 提高 Microsoft 365 for Business 的威胁防护
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 设置 Office 365 高级威胁防护，并针对网络钓鱼、恶意软件和其他威胁保护敏感数据。
ms.openlocfilehash: d56a5371bc5fc4da22f4625024769cc0325a25ca
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948580"
---
# <a name="increase-threat-protection"></a><span data-ttu-id="5ecdb-103">增强威胁防护</span><span class="sxs-lookup"><span data-stu-id="5ecdb-103">Increase threat protection</span></span>

<span data-ttu-id="5ecdb-104">本文可帮助你提高 Microsoft 365 订阅中的保护，以防止出现网络钓鱼、恶意软件和其他威胁。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="5ecdb-105">这些建议适用于具有更高安全性需求的组织，如法律办公室和卫生保健诊所。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-105">These recommendations are appropriate for organizations with an increased need for security, like law offices and health care clinics.</span></span>

<span data-ttu-id="5ecdb-106">在开始之前，请检查您的 Office 365 安全分数。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-106">Before you begin, check your Office 365 Secure Score.</span></span> <span data-ttu-id="5ecdb-107">Office 365 安全分数根据您的常规活动和安全设置来分析组织的安全性，并分配分数。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-107">Office 365 Secure Score analyzes your organization's security based on your regular activities and security settings, and assigns a score.</span></span> <span data-ttu-id="5ecdb-108">首先记录你的当前分数。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="5ecdb-109">若要增加成绩，请完成本文中建议的操作。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-109">To increase your score, complete the actions recommended in this article.</span></span> <span data-ttu-id="5ecdb-110">目标不能达到最大分数，但请注意保护您的环境不会对用户的工作效率造成负面影响的机会。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-110">The goal isn't to achieve the maximum score, but to be aware of opportunities to protect your environment that don't negatively affect productivity for your users.</span></span>

<span data-ttu-id="5ecdb-111">有关详细信息，请参阅 [Microsoft 安全分数](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-111">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="5ecdb-112">提高针对邮件中的恶意软件的保护级别</span><span class="sxs-lookup"><span data-stu-id="5ecdb-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="5ecdb-113">您的 Office 365 或 Microsoft 365 环境包括针对恶意软件的防护。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-113">Your Office 365 or Microsoft 365 environment includes protection against malware.</span></span> <span data-ttu-id="5ecdb-114">您可以通过阻止经常用于恶意软件的文件类型来阻止附件，从而提高此保护。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-114">You can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="5ecdb-115">若要提高电子邮件的恶意软件保护：</span><span class="sxs-lookup"><span data-stu-id="5ecdb-115">To increase malware protection in email:</span></span>

1. <span data-ttu-id="5ecdb-116">转到 [https://protection.office.com](https://protection.office.com) 并使用你的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-116">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account credentials.</span></span>

2. <span data-ttu-id="5ecdb-117">在安全 &amp; 合规性中心的左侧导航窗格中的 " **威胁管理**" 下，选择 " **策略** \> **反恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-117">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>

3. <span data-ttu-id="5ecdb-118">双击默认策略以编辑此公司范围的策略。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-118">Double-click the default policy to edit this company-wide policy.</span></span>

4. <span data-ttu-id="5ecdb-119">选择“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-119">Select **Settings**.</span></span>

5. <span data-ttu-id="5ecdb-120">在 " **常用附件类型筛选器**" 下，选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-120">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="5ecdb-121">被阻止的文件类型在此控件正下方的窗口中列出。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-121">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="5ecdb-122">请确保添加以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="5ecdb-122">Make sure that you add these file types:</span></span>

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   <span data-ttu-id="5ecdb-123">如有必要，您可以稍后添加或删除文件类型。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-123">If necessary, you can add or delete file types later.</span></span>

6. <span data-ttu-id="5ecdb-124">选择 " **保存"。**</span><span class="sxs-lookup"><span data-stu-id="5ecdb-124">Select **Save.**</span></span>

<span data-ttu-id="5ecdb-125">有关详细信息，请参阅 [EOP 中的反恶意软件保护](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-125">For more information, see [Anti-malware protection in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).</span></span>

## <a name="protect-against-ransomware"></a><span data-ttu-id="5ecdb-126">防范勒索软件</span><span class="sxs-lookup"><span data-stu-id="5ecdb-126">Protect against ransomware</span></span>

<span data-ttu-id="5ecdb-127">勒索软件通过加密文件或锁定计算机屏幕来限制对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-127">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="5ecdb-128">然后，它会通过在 exchange 中请求 "勒索" （通常为 "cryptocurrencies" 的形式为 "Bitcoin"），从受害者处 extort 钱，以供 exchange 访问数据。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-128">It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span>

<span data-ttu-id="5ecdb-129">若要针对勒索软件进行保护，请创建一个或多个邮件流规则，以阻止用于勒索软件的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-129">To protect against ransomware, create one or more mail flow rules to block file extensions that are commonly used for ransomware.</span></span> <span data-ttu-id="5ecdb-130"> (您在 "邮件" 步骤中添加了这些规则以 [防止恶意软件的保护级别](#raise-the-level-of-protection-against-malware-in-mail) 。 ) 您还可以在电子邮件中警告收到这些附件的用户。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-130">(You added these rules in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step.) You can also warn users who receive these attachments in email.</span></span>

<span data-ttu-id="5ecdb-131">除了在上一步中阻止的文件，在打开包含宏的 Office 文件附件之前，最好先创建一个规则来警告用户。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-131">In addition to the files that you blocked in the previous step, it's a good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="5ecdb-132">勒索软件可以隐藏在宏中，因此警告用户不要从他们不知道的人那里打开这些文件。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-132">Ransomware can be hidden inside macros, so warn users not to open these files from people they don't know.</span></span>

<span data-ttu-id="5ecdb-133">若要创建邮件传输规则，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5ecdb-133">To create a mail transport rule:</span></span>

1. <span data-ttu-id="5ecdb-134">转到 "管理中心" <https://admin.microsoft.com> ，然后选择 " **管理中心**" " \> **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-134">Go to the admin center at <https://admin.microsoft.com>, and choose **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="5ecdb-135">在 " **邮件流** " 类别中，选择 " **规则**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-135">In the **mail flow** category, select **rules**.</span></span>

3. <span data-ttu-id="5ecdb-136">选择 **+** ""，然后选择 " **创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-136">Select **+**, and then select **Create a new rule**.</span></span>

4. <span data-ttu-id="5ecdb-137">选择对话框底部的 " **更多选项** " 可查看完整的选项集。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-137">Select **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="5ecdb-138">对规则应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-138">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="5ecdb-139">对其余设置使用默认值，除非您要对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-139">Use the default values for the rest of the settings, unless you want to change them.</span></span>

6. <span data-ttu-id="5ecdb-140">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-140">Select **Save**.</span></span>

|<span data-ttu-id="5ecdb-141">设置</span><span class="sxs-lookup"><span data-stu-id="5ecdb-141">Setting</span></span>|<span data-ttu-id="5ecdb-142">在打开 Office 文件附件之前警告用户</span><span class="sxs-lookup"><span data-stu-id="5ecdb-142">Warn users before opening attachments of Office files</span></span>||
|---|---|---|
|<span data-ttu-id="5ecdb-143">名称</span><span class="sxs-lookup"><span data-stu-id="5ecdb-143">Name</span></span>|<span data-ttu-id="5ecdb-144">反勒索软件规则：警告用户</span><span class="sxs-lookup"><span data-stu-id="5ecdb-144">Anti-ransomware rule: warn users</span></span>|
|<span data-ttu-id="5ecdb-145">在以下情况应用此规则。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-145">Apply this rule if .</span></span> <span data-ttu-id="5ecdb-146">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-146">.</span></span> <span data-ttu-id="5ecdb-147">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-147">.</span></span>|<span data-ttu-id="5ecdb-148">任何附件。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-148">Any attachment .</span></span> <span data-ttu-id="5ecdb-149">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-149">.</span></span> <span data-ttu-id="5ecdb-150">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-150">.</span></span> <span data-ttu-id="5ecdb-151">文件扩展名匹配。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-151">file extension matches .</span></span> <span data-ttu-id="5ecdb-152">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-152">.</span></span> <span data-ttu-id="5ecdb-153">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-153">.</span></span>|
|<span data-ttu-id="5ecdb-154">指定字词或短语</span><span class="sxs-lookup"><span data-stu-id="5ecdb-154">Specify words or phrases</span></span>|<span data-ttu-id="5ecdb-155">添加以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="5ecdb-155">Add these file types:</span></span>  <br/> <span data-ttu-id="5ecdb-156">normal.dotm、.docm、xlsm、sltm、xlodbc.xla 加载、.xlam、xll、.pptm、potm、.ppam、ppsm、sldm</span><span class="sxs-lookup"><span data-stu-id="5ecdb-156">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span></span>|
|<span data-ttu-id="5ecdb-157">执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-157">Do the following .</span></span> <span data-ttu-id="5ecdb-158">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-158">.</span></span> <span data-ttu-id="5ecdb-159">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-159">.</span></span>|<span data-ttu-id="5ecdb-160">使用邮件通知收件人</span><span class="sxs-lookup"><span data-stu-id="5ecdb-160">Notify the recipient with a message</span></span>|
|<span data-ttu-id="5ecdb-161">提供邮件文本</span><span class="sxs-lookup"><span data-stu-id="5ecdb-161">Provide message text</span></span>|<span data-ttu-id="5ecdb-162">请勿从不知道的人打开这些类型的文件，因为它们可能包含恶意代码的宏。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-162">Do not open these types of files from people you do not know because they might contain macros with malicious code.</span></span>|

<span data-ttu-id="5ecdb-163">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="5ecdb-163">For more information, see:</span></span>

- [<span data-ttu-id="5ecdb-164">勒索软件：如何降低风险</span><span class="sxs-lookup"><span data-stu-id="5ecdb-164">Ransomware: how to reduce risk</span></span>](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [<span data-ttu-id="5ecdb-165">还原你的 OneDrive</span><span class="sxs-lookup"><span data-stu-id="5ecdb-165">Restore your OneDrive</span></span>](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="5ecdb-166">停止电子邮件的自动转发</span><span class="sxs-lookup"><span data-stu-id="5ecdb-166">Stop auto-forwarding for email</span></span>

<span data-ttu-id="5ecdb-167">获取对用户邮箱的访问权限的黑客可以通过将邮箱设置为自动转发电子邮件来盗取邮件。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-167">Hackers who gain access to a user's mailbox can steal mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="5ecdb-168">即使没有用户的意识，也会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-168">This can happen even without the user's awareness.</span></span> <span data-ttu-id="5ecdb-169">若要防止这种情况发生，请配置邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-169">To prevent this from happening, configure a mail flow rule.</span></span>

<span data-ttu-id="5ecdb-170">若要创建邮件传输规则，请观看 [此简短视频](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) 或按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="5ecdb-170">To create a mail transport rule, either watch [this short video](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>

1. <span data-ttu-id="5ecdb-171">在 Microsoft 365 管理中心，选择 " **管理中心**" " \> **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-171">In the Microsoft 365 admin center, select **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="5ecdb-172">在 " **邮件流** " 类别中，选择 " **规则**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-172">In the **mail flow** category, select **rules**.</span></span>

3. <span data-ttu-id="5ecdb-173">选择 **+** ""，然后选择 " **创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-173">Select **+**, and then select **Create a new rule**.</span></span>

4. <span data-ttu-id="5ecdb-174">若要查看所有选项，请在对话框底部选择 " **更多选项** "。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-174">To see all the options, select **More options** at the bottom of the dialog box.</span></span>

5. <span data-ttu-id="5ecdb-175">应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-175">Apply the settings in the following table.</span></span> <span data-ttu-id="5ecdb-176">对其余设置使用默认值，除非您要对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-176">Use the default values for the rest of the settings, unless you want to change them.</span></span>

6. <span data-ttu-id="5ecdb-177">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-177">Select **Save**.</span></span>

|<span data-ttu-id="5ecdb-178">设置</span><span class="sxs-lookup"><span data-stu-id="5ecdb-178">Setting</span></span>|<span data-ttu-id="5ecdb-179">在打开 Office 文件附件之前警告用户</span><span class="sxs-lookup"><span data-stu-id="5ecdb-179">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="5ecdb-180">名称</span><span class="sxs-lookup"><span data-stu-id="5ecdb-180">Name</span></span>|<span data-ttu-id="5ecdb-181">阻止电子邮件自动转发到外部域</span><span class="sxs-lookup"><span data-stu-id="5ecdb-181">Prevent auto forwarding of email to external domains</span></span>|
|<span data-ttu-id="5ecdb-182">在以下情况应用此规则 .。。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-182">Apply this rule if ...</span></span>|<span data-ttu-id="5ecdb-183">发件人。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-183">The sender .</span></span> <span data-ttu-id="5ecdb-184">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-184">.</span></span> <span data-ttu-id="5ecdb-185">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-185">.</span></span> <span data-ttu-id="5ecdb-186">为外部/内部。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-186">is external/internal .</span></span> <span data-ttu-id="5ecdb-187">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-187">.</span></span> <span data-ttu-id="5ecdb-188">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-188">.</span></span> <span data-ttu-id="5ecdb-189">组织内部</span><span class="sxs-lookup"><span data-stu-id="5ecdb-189">Inside the organization</span></span>|
|<span data-ttu-id="5ecdb-190">添加条件</span><span class="sxs-lookup"><span data-stu-id="5ecdb-190">Add condition</span></span>|<span data-ttu-id="5ecdb-191">邮件属性。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-191">The message properties .</span></span> <span data-ttu-id="5ecdb-192">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-192">.</span></span> <span data-ttu-id="5ecdb-193">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-193">.</span></span> <span data-ttu-id="5ecdb-194">包含邮件类型。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-194">include the message type .</span></span> <span data-ttu-id="5ecdb-195">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-195">.</span></span> <span data-ttu-id="5ecdb-196">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-196">.</span></span> <span data-ttu-id="5ecdb-197">自动转发</span><span class="sxs-lookup"><span data-stu-id="5ecdb-197">Auto-forward</span></span>|
|<span data-ttu-id="5ecdb-198">执行以下操作 .。。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-198">Do the following ...</span></span>|<span data-ttu-id="5ecdb-199">阻止邮件。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-199">Block the message .</span></span> <span data-ttu-id="5ecdb-200">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-200">.</span></span> <span data-ttu-id="5ecdb-201">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-201">.</span></span> <span data-ttu-id="5ecdb-202">拒绝邮件并提供说明。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-202">reject the message and include an explanation.</span></span>|
|<span data-ttu-id="5ecdb-203">提供邮件文本</span><span class="sxs-lookup"><span data-stu-id="5ecdb-203">Provide message text</span></span>|<span data-ttu-id="5ecdb-204">出于安全考虑，将阻止此组织外部的自动转发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-204">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>|


## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="5ecdb-205">保护你的电子邮件免受网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="5ecdb-205">Protect your email from phishing attacks</span></span>

<span data-ttu-id="5ecdb-206">如果您为 Office 365 或 Microsoft 365 环境配置了一个或多个自定义域，则可以配置目标的反网络钓鱼保护。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-206">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="5ecdb-207">ATP 反网络钓鱼保护是 Office 365 高级威胁防护的一部分，可帮助保护您的组织免受基于恶意模拟的网络钓鱼攻击和其他网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-207">ATP anti-phishing protection, part of Office 365 Advanced Threat Protection, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="5ecdb-208">如果尚未配置自定义域，则无需执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-208">If you haven't configured a custom domain, you don't need to do this.</span></span>

<span data-ttu-id="5ecdb-209">我们建议您通过创建策略来保护最重要的用户和您的自定义域，以此来开始保护。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-209">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span>

<span data-ttu-id="5ecdb-210">若要创建 ATP 反网络钓鱼策略，请观看  [此简短的培训视频](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5ecdb-210">To create an ATP anti-phishing policy, watch  [this short training video](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>

1. <span data-ttu-id="5ecdb-211">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-211">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="5ecdb-212">在安全 &amp; 合规性中心的左侧导航窗格中的 " **威胁管理**" 下，选择 " **策略**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-212">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="5ecdb-213">在 " **策略** " 页上，选择 " **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-213">On the **Policy** page, choose **ATP anti-phishing**.</span></span>

4. <span data-ttu-id="5ecdb-214">在 " **反钓鱼网站** " 页上，选择 " **+ 创建**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-214">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="5ecdb-215">向导将启动，引导您完成定义您的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-215">A wizard launches that steps you through defining your anti-phishing policy.</span></span>

5. <span data-ttu-id="5ecdb-216">按下表中的建议指定策略的名称、说明和设置。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-216">Specify the name, description, and settings for your policy as recommended in the following table.</span></span> <span data-ttu-id="5ecdb-217">有关更多详细信息，请参阅 [了解 ATP 反网络钓鱼策略选项](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-217">For more details, see [Learn about ATP anti-phishing policy options](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).</span></span>

6. <span data-ttu-id="5ecdb-218">查看设置后，根据需要选择 " **创建此策略** " 或 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-218">After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="5ecdb-219">设置或选项</span><span class="sxs-lookup"><span data-stu-id="5ecdb-219">Setting or option</span></span>|<span data-ttu-id="5ecdb-220">推荐设置</span><span class="sxs-lookup"><span data-stu-id="5ecdb-220">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="5ecdb-221">名称</span><span class="sxs-lookup"><span data-stu-id="5ecdb-221">Name</span></span>|<span data-ttu-id="5ecdb-222">域和最有价值的市场活动员工</span><span class="sxs-lookup"><span data-stu-id="5ecdb-222">Domain and most valuable campaign staff</span></span>|
|<span data-ttu-id="5ecdb-223">说明</span><span class="sxs-lookup"><span data-stu-id="5ecdb-223">Description</span></span>|<span data-ttu-id="5ecdb-224">确保不会模拟大多数重要的人员和我们的域。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-224">Ensure most important staff and our domain are not being impersonated.</span></span>|
|<span data-ttu-id="5ecdb-225">添加要保护的用户</span><span class="sxs-lookup"><span data-stu-id="5ecdb-225">Add users to protect</span></span>|<span data-ttu-id="5ecdb-226">选择 **+ 添加条件，收件人为**。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-226">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="5ecdb-227">键入用户名称或输入候选人、活动经理和其他重要教职员工成员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-227">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="5ecdb-228">您最大可以添加20个要从模拟中保护的内部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-228">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>|
|<span data-ttu-id="5ecdb-229">添加要保护的域</span><span class="sxs-lookup"><span data-stu-id="5ecdb-229">Add domains to protect</span></span>|<span data-ttu-id="5ecdb-230">选择 **"+ 添加条件，收件人域为"**。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-230">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="5ecdb-231">输入与 Microsoft 365 订阅关联的自定义域（如果已定义一个）。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-231">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="5ecdb-232">您可以输入一个以上的域。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-232">You can enter more than one domain.</span></span>|
|<span data-ttu-id="5ecdb-233">选择操作</span><span class="sxs-lookup"><span data-stu-id="5ecdb-233">Choose actions</span></span>|<span data-ttu-id="5ecdb-234">如果模拟用户发送电子邮件：选择 "**将邮件重定向到另一个电子邮件地址**"，然后键入安全管理员的电子邮件地址;例如，*刘爱琳 <span> <span> @contoso .com*。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-234">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span> <span data-ttu-id="5ecdb-235">如果电子邮件是由模拟域发送的：请选择“隔离邮件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-235">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>|
|<span data-ttu-id="5ecdb-236">邮箱智能</span><span class="sxs-lookup"><span data-stu-id="5ecdb-236">Mailbox intelligence</span></span>|<span data-ttu-id="5ecdb-237">默认情况下，创建新的反钓鱼策略时，将选择邮箱智能。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-237">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="5ecdb-238">最好将此设置保留为“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-238">Leave this setting **On** for best results.</span></span>|
|<span data-ttu-id="5ecdb-239">添加受信任的发件人和域</span><span class="sxs-lookup"><span data-stu-id="5ecdb-239">Add trusted senders and domains</span></span>|<span data-ttu-id="5ecdb-240">你可以在此处添加你自己的域或任何其他受信任域。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-240">Here you can add your own domain, or any other trusted domains.</span></span>|
|<span data-ttu-id="5ecdb-241">应用于</span><span class="sxs-lookup"><span data-stu-id="5ecdb-241">Applied to</span></span>|<span data-ttu-id="5ecdb-242">选择“收件人域为”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-242">Select **The recipient domain is**.</span></span> <span data-ttu-id="5ecdb-243">在“以下任何项”\*\*\*\* 中，选择“选择”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-243">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="5ecdb-244">选择“+ 添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-244">Select **+ Add**.</span></span> <span data-ttu-id="5ecdb-245">选中域名称旁边的复选框，例如 " *contoso"。 <span> <span>com*，请在列表中，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-245">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="5ecdb-246">选择“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-246">Select **Done**.</span></span>|

## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a><span data-ttu-id="5ecdb-247">使用 ATP 安全附件防止恶意附件和文件</span><span class="sxs-lookup"><span data-stu-id="5ecdb-247">Protect against malicious attachments and files with ATP Safe Attachments</span></span>

<span data-ttu-id="5ecdb-248">用户定期发送、接收和共享附件，如文档、演示文稿、电子表格等。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-248">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="5ecdb-249">只需查看一封电子邮件，就能判断附件是安全还是恶意的，并不总是容易。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-249">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="5ecdb-250">Office 365 高级威胁防护包括 ATP 安全附件保护，但默认情况下不启用此保护。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-250">Office 365 Advanced Threat Protection includes ATP Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="5ecdb-251">我们建议您创建一个新规则以开始使用此保护。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-251">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="5ecdb-252">此保护功能扩展到 SharePoint、OneDrive 和 Microsoft 团队中的文件。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-252">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>

<span data-ttu-id="5ecdb-253">若要创建 ATP 安全附件策略，请观看 [此简短视频](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5ecdb-253">To create an ATP safe attachment policy, either watch [this short video](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>

1. <span data-ttu-id="5ecdb-254">转到 [https://protection.office.com](https://protection.office.com) ，然后使用你的管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-254">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span>

2. <span data-ttu-id="5ecdb-255">在安全 &amp; 合规性中心的左侧导航窗格中的 " **威胁管理**" 下，选择 " **策略**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-255">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="5ecdb-256">在 "策略" 页上，选择 " **ATP 安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-256">On the Policy page, choose **ATP safe attachments**.</span></span>

4. <span data-ttu-id="5ecdb-257">在 "安全附件" 页面上，选中 " **启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP** " 复选框，以应用广泛的保护。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-257">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span>

5. <span data-ttu-id="5ecdb-258">选择 **+** 以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-258">Select **+** to create a new policy.</span></span>

6. <span data-ttu-id="5ecdb-259">应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-259">Apply the settings in the following table.</span></span>

7. <span data-ttu-id="5ecdb-260">查看设置后，根据需要选择 " **创建此策略** " 或 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-260">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="5ecdb-261">设置或选项</span><span class="sxs-lookup"><span data-stu-id="5ecdb-261">Setting or option</span></span>|<span data-ttu-id="5ecdb-262">推荐设置</span><span class="sxs-lookup"><span data-stu-id="5ecdb-262">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="5ecdb-263">名称</span><span class="sxs-lookup"><span data-stu-id="5ecdb-263">Name</span></span>|<span data-ttu-id="5ecdb-264">使用检测到的恶意软件阻止当前和将来的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-264">Block current and future emails with detected malware.</span></span>|
|<span data-ttu-id="5ecdb-265">说明</span><span class="sxs-lookup"><span data-stu-id="5ecdb-265">Description</span></span>|<span data-ttu-id="5ecdb-266">使用检测到的恶意软件阻止当前和将来的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-266">Block current and future emails and attachments with detected malware.</span></span>|
|<span data-ttu-id="5ecdb-267">保存附件未知的恶意软件响应</span><span class="sxs-lookup"><span data-stu-id="5ecdb-267">Save attachments unknown malware response</span></span>|<span data-ttu-id="5ecdb-268">Select **block-阻止当前和将来的包含检测到的恶意软件的电子邮件和附件**。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-268">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>|
|<span data-ttu-id="5ecdb-269">在检测时重定向附件</span><span class="sxs-lookup"><span data-stu-id="5ecdb-269">Redirect attachment on detection</span></span>|<span data-ttu-id="5ecdb-270">启用重定向 (选中此框) 输入管理员帐户或邮箱设置进行隔离。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-270">Enable redirection (select this box)          Enter the admin account or a mailbox setup for quarantine.</span></span>          <span data-ttu-id="5ecdb-271">如果恶意软件扫描附件超时或发生错误，则应用上述选择) 。 (选中该框。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-271">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>|
|<span data-ttu-id="5ecdb-272">应用于</span><span class="sxs-lookup"><span data-stu-id="5ecdb-272">Applied to</span></span>|<span data-ttu-id="5ecdb-273">收件人域为。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-273">The recipient domain is .</span></span> <span data-ttu-id="5ecdb-274">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-274">.</span></span> <span data-ttu-id="5ecdb-275">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-275">.</span></span> <span data-ttu-id="5ecdb-276">选择您的域。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-276">select your domain.</span></span>|

<span data-ttu-id="5ecdb-277">有关详细信息，请参阅 [设置 Office 365 ATP 反网络钓鱼策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-277">For more information, see [Set up Office 365 ATP anti-phishing policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).</span></span>

## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a><span data-ttu-id="5ecdb-278">使用 ATP 安全链接防御网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="5ecdb-278">Protect against phishing attacks with ATP Safe Links</span></span>

<span data-ttu-id="5ecdb-279">黑客有时会在电子邮件或其他文件的链接中隐藏恶意网站。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-279">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="5ecdb-280">Office 365 ATP 安全链接 (ATP 安全链接) （Office 365 高级威胁防护的一部分）可以通过提供电子邮件和 Office 文档中) 的 web (地址的单击验证，从而帮助保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-280">Office 365 ATP Safe Links (ATP Safe Links), part of Office 365 Advanced Threat Protection, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="5ecdb-281">通过 ATP 安全链接策略定义保护。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-281">Protection is defined through ATP Safe Links policies.</span></span>

<span data-ttu-id="5ecdb-282">我们建议您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5ecdb-282">We recommend that you do the following:</span></span>

- <span data-ttu-id="5ecdb-283">修改默认策略以提高保护。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-283">Modify the default policy to increase protection.</span></span>

- <span data-ttu-id="5ecdb-284">添加目标为域中所有收件人的新策略。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-284">Add a new policy targeted to all recipients in your domain.</span></span>

<span data-ttu-id="5ecdb-285">若要设置 ATP 安全链接，请观看 [此简短的培训视频](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5ecdb-285">To set up ATP Safe Links, watch [this short training video](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>

1. <span data-ttu-id="5ecdb-286">转到 [https://protection.office.com](https://protection.office.com) ，然后使用你的管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-286">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span>

2. <span data-ttu-id="5ecdb-287">在安全 &amp; 合规性中心的左侧导航窗格中的 " **威胁管理**" 下，选择 " **策略**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-287">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="5ecdb-288">在 "策略" 页上，选择 " **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-288">On the Policy page, choose **ATP Safe Links**.</span></span>

<span data-ttu-id="5ecdb-289">若要修改默认策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5ecdb-289">To modify the default policy:</span></span>

1. <span data-ttu-id="5ecdb-290">在 "安全链接" 页面上，在 " **适用于整个组织的策略**" 下，选择 " **默认** 策略"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-290">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span>

2. <span data-ttu-id="5ecdb-291">在 " **适用于除电子邮件以外的内容的设置**" 下，选择 "适用于 **企业的 Microsoft 365 应用，Office For iOS 和 Android**"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-291">Under **Settings that apply to content except email**, select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.</span></span>

3. <span data-ttu-id="5ecdb-292">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-292">Select **Save**.</span></span>

<span data-ttu-id="5ecdb-293">创建一个面向域中所有收件人的新策略：</span><span class="sxs-lookup"><span data-stu-id="5ecdb-293">To create a new policy targeted to all recipients in your domain:</span></span>

1. <span data-ttu-id="5ecdb-294">在 "安全链接" 页面上，在 " **适用于整个组织的策略**" 下，选择 " **+** 创建新策略"。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-294">On the Safe links page, under **Policies that apply to the entire organization**, select **+** to create a new policy.</span></span>

2. <span data-ttu-id="5ecdb-295">应用下表中列出的设置。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-295">Apply the settings listed in the following table.</span></span>

3. <span data-ttu-id="5ecdb-296">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-296">Select **Save**.</span></span>

|<span data-ttu-id="5ecdb-297">设置或选项</span><span class="sxs-lookup"><span data-stu-id="5ecdb-297">Setting or option</span></span>|<span data-ttu-id="5ecdb-298">推荐设置</span><span class="sxs-lookup"><span data-stu-id="5ecdb-298">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="5ecdb-299">名称</span><span class="sxs-lookup"><span data-stu-id="5ecdb-299">Name</span></span>|<span data-ttu-id="5ecdb-300">域中所有收件人的安全链接策略</span><span class="sxs-lookup"><span data-stu-id="5ecdb-300">Safe links policy for all recipients in the domain</span></span>|
|<span data-ttu-id="5ecdb-301">选择邮件中未知的潜在恶意 Url 的操作</span><span class="sxs-lookup"><span data-stu-id="5ecdb-301">Select the action for unknown potentially malicious URLs in messages</span></span>|<span data-ttu-id="5ecdb-302">**当用户单击链接时，将会重写并检查在已知恶意链接列表中的 "按 Url"，并对其进行检查**。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-302">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>|
|<span data-ttu-id="5ecdb-303">使用安全附件扫描可下载的内容</span><span class="sxs-lookup"><span data-stu-id="5ecdb-303">Use Safe Attachments to scan downloadable content</span></span>|<span data-ttu-id="5ecdb-304">选中此框。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-304">Select this box.</span></span>|
|<span data-ttu-id="5ecdb-305">应用于</span><span class="sxs-lookup"><span data-stu-id="5ecdb-305">Applied to</span></span>|<span data-ttu-id="5ecdb-306">收件人域为。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-306">The recipient domain is .</span></span> <span data-ttu-id="5ecdb-307">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-307">.</span></span> <span data-ttu-id="5ecdb-308">.</span><span class="sxs-lookup"><span data-stu-id="5ecdb-308">.</span></span> <span data-ttu-id="5ecdb-309">选择您的域。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-309">select your domain.</span></span>|

<span data-ttu-id="5ecdb-310">有关详细信息，请参阅 [Office 365 ATP 安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-310">For more information, see [Office 365 ATP safe links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="5ecdb-311">转到 Intune 管理中心</span><span class="sxs-lookup"><span data-stu-id="5ecdb-311">Go to Intune admin center</span></span>

1. <span data-ttu-id="5ecdb-312">登录到 [Azure 门户](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-312">Sign in to [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="5ecdb-313">在 "**搜索" 框**中选择 "**所有服务**"，然后键入*Intune* 。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-313">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="5ecdb-314">在结果出现后，选择 " **Microsoft Intune** " 旁边的 "开始"，使其成为收藏且易于查找。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-314">Once the results appear, select the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="5ecdb-315">除了管理中心之外，你还可以使用 Intune 注册和管理你的组织的设备。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-315">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="5ecdb-316">有关详细信息，请参阅 [Windows 设备注册方法](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) 和由 [Intune 管理的设备的注册选项](https://docs.microsoft.com/intune/enrollment-options)的功能。</span><span class="sxs-lookup"><span data-stu-id="5ecdb-316">For more information, see [Capabilities by enrollment method for Windows devices](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) and [Enrollment options for devices managed by Intune](https://docs.microsoft.com/intune/enrollment-options).</span></span>
