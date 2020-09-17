---
title: 增强威胁防护
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: 获取有关在 Microsoft 365 中提高保护级别的帮助
ms.openlocfilehash: 36ff6c1ff5fd8c826434504c694046d12b5e63bc
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948612"
---
# <a name="increase-threat-protection"></a><span data-ttu-id="63780-103">增强威胁防护</span><span class="sxs-lookup"><span data-stu-id="63780-103">Increase threat protection</span></span>

<span data-ttu-id="63780-104">本文可帮助你提高 Microsoft 365 订阅中的保护，以防止出现网络钓鱼、恶意软件和其他威胁。</span><span class="sxs-lookup"><span data-stu-id="63780-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="63780-105">这些建议适用于具有更高安全性需求的组织，如政治市场、法律办事处和卫生保健诊所。</span><span class="sxs-lookup"><span data-stu-id="63780-105">These recommendations are appropriate for organizations with an increased need for security, like political campaigns, law offices, and health care clinics.</span></span>

<span data-ttu-id="63780-106">在开始之前，请检查你的 Microsoft 安全分数。</span><span class="sxs-lookup"><span data-stu-id="63780-106">Before you begin, check your Microsoft Secure Score.</span></span> <span data-ttu-id="63780-107">Microsoft 安全分数根据您的常规活动和安全设置来分析组织的安全性，并给出分数。</span><span class="sxs-lookup"><span data-stu-id="63780-107">Microsoft Secure Score analyzes your organization's security based on your regular activities and security settings and assigns a score.</span></span> <span data-ttu-id="63780-108">首先记录你的当前分数。</span><span class="sxs-lookup"><span data-stu-id="63780-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="63780-109">采取本文中建议的操作可提高您的成绩。</span><span class="sxs-lookup"><span data-stu-id="63780-109">Taking the actions recommended in this article increases your score.</span></span> <span data-ttu-id="63780-110">目标不能达到最大分数，但请注意保护您的环境不会对用户的工作效率造成负面影响的机会。</span><span class="sxs-lookup"><span data-stu-id="63780-110">The goal isn't to achieve the max score, but to be aware of opportunities to protect your environment that don't negatively affect productivity for your users.</span></span>

<span data-ttu-id="63780-111">有关详细信息，请参阅 [Microsoft 安全分数](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。</span><span class="sxs-lookup"><span data-stu-id="63780-111">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="63780-112">提高针对邮件中的恶意软件的保护级别</span><span class="sxs-lookup"><span data-stu-id="63780-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="63780-113">你的 Office 365 或 Microsoft 365 环境包括针对恶意软件的防护，但你可以通过阻止常见恶意软件使用的文件类型的附件来提高此保护。</span><span class="sxs-lookup"><span data-stu-id="63780-113">Your Office 365 or Microsoft 365 environment includes protection against malware, but you can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="63780-114">若要增大电子邮件的恶意软件保护，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="63780-114">To bump up malware protection in email:</span></span>

1. <span data-ttu-id="63780-115">转到 <https://protection.office.com> 并使用你的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="63780-115">Go to <https://protection.office.com> and sign in with your admin account credentials.</span></span>

2. <span data-ttu-id="63780-116">在安全 & 合规性中心的左侧导航窗格中的 " **威胁管理**" 下，选择 " **策略** \> **反恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="63780-116">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>

3. <span data-ttu-id="63780-117">双击默认策略以编辑此公司范围的策略。</span><span class="sxs-lookup"><span data-stu-id="63780-117">Double-click the default policy to edit this company-wide policy.</span></span>

4. <span data-ttu-id="63780-118">单击“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="63780-118">Click **Settings**.</span></span>

5. <span data-ttu-id="63780-119">在 " **常用附件类型筛选器**" 下，选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="63780-119">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="63780-120">被阻止的文件类型在此控件正下方的窗口中列出。</span><span class="sxs-lookup"><span data-stu-id="63780-120">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="63780-121">请确保添加以下 filetypes：</span><span class="sxs-lookup"><span data-stu-id="63780-121">Make sure you add these filetypes:</span></span>

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   <span data-ttu-id="63780-122">如果需要，您可以稍后添加或删除文件类型。</span><span class="sxs-lookup"><span data-stu-id="63780-122">You can add or delete file types later, if needed.</span></span>

6. <span data-ttu-id="63780-123">单击“保存”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="63780-123">Click **Save.**</span></span>

<span data-ttu-id="63780-124">有关详细信息，请参阅 [EOP 中的反恶意软件保护](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)。</span><span class="sxs-lookup"><span data-stu-id="63780-124">For more information, see [Anti-malware protection in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).</span></span>

## <a name="protect-against-ransomware"></a><span data-ttu-id="63780-125">防范勒索软件</span><span class="sxs-lookup"><span data-stu-id="63780-125">Protect against ransomware</span></span>

<span data-ttu-id="63780-126">勒索软件通过加密文件或锁定计算机屏幕来限制对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="63780-126">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="63780-127">然后，它会通过在 exchange 中请求 "勒索" （通常为 "cryptocurrencies" 的形式为 "Bitcoin"），从受害者处 extort 钱，以供 exchange 访问数据。</span><span class="sxs-lookup"><span data-stu-id="63780-127">It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span>

<span data-ttu-id="63780-128">您可以通过创建一个或多个邮件流规则来阻止勒索软件，以阻止通常用于 (勒索软件的文件扩展名，在 " [提高邮件中的恶意软件的保护级别](#raise-the-level-of-protection-against-malware-in-mail) ") 中添加这些邮件，或警告用户在电子邮件中接收这些附件的用户，可以防止勒索软件。</span><span class="sxs-lookup"><span data-stu-id="63780-128">You can protect against ransomware by creating one or more mail flow rules to block file extensions that are commonly used for ransomware (these were added in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step), or to warn users who receive these attachments in email.</span></span>

<span data-ttu-id="63780-129">除了在上一步中阻止的文件，在打开包含宏的 Office 文件附件之前，创建规则来警告用户也是一种很好的做法。</span><span class="sxs-lookup"><span data-stu-id="63780-129">In addition to the files that you blocked in the previous step, it's also good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="63780-130">勒索软件可以隐藏在宏中，因此警告用户不要从他们不知道的人打开这些文件。</span><span class="sxs-lookup"><span data-stu-id="63780-130">Ransomware can be hidden inside macros, so warn users to not open these files from people they don't know.</span></span>

<span data-ttu-id="63780-131">若要创建邮件传输规则，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="63780-131">To create a mail transport rule:</span></span>

1. <span data-ttu-id="63780-132">转到 "管理中心" <https://admin.microsoft.com> ，然后选择 " **管理中心** \> **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="63780-132">Go to the admin center at <https://admin.microsoft.com> and choose **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="63780-133">在 " **邮件流** " 类别中，单击 " **规则**"。</span><span class="sxs-lookup"><span data-stu-id="63780-133">In the **mail flow** category, click **rules**.</span></span>

3. <span data-ttu-id="63780-134">单击 **+** ""，然后单击 " **创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="63780-134">Click **+**, and then click **Create a new rule**.</span></span>

4. <span data-ttu-id="63780-135">单击对话框底部的 " **更多选项** " 以查看完整的选项集。</span><span class="sxs-lookup"><span data-stu-id="63780-135">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="63780-136">对规则应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="63780-136">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="63780-137">将其余设置保留为默认值，除非您要对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="63780-137">Leave the rest of the settings at the default, unless you want to change them.</span></span>

6. <span data-ttu-id="63780-138">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63780-138">Click **Save**.</span></span>

|<span data-ttu-id="63780-139">设置</span><span class="sxs-lookup"><span data-stu-id="63780-139">Setting</span></span>|<span data-ttu-id="63780-140">在打开 Office 文件附件之前警告用户</span><span class="sxs-lookup"><span data-stu-id="63780-140">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="63780-141">名称</span><span class="sxs-lookup"><span data-stu-id="63780-141">Name</span></span>|<span data-ttu-id="63780-142">反勒索软件规则：警告用户</span><span class="sxs-lookup"><span data-stu-id="63780-142">Anti-ransomware rule: warn users</span></span>|
|<span data-ttu-id="63780-143">在以下情况应用此规则。</span><span class="sxs-lookup"><span data-stu-id="63780-143">Apply this rule if .</span></span> <span data-ttu-id="63780-144">.</span><span class="sxs-lookup"><span data-stu-id="63780-144">.</span></span> <span data-ttu-id="63780-145">.</span><span class="sxs-lookup"><span data-stu-id="63780-145">.</span></span>|<span data-ttu-id="63780-146">任何附件。</span><span class="sxs-lookup"><span data-stu-id="63780-146">Any attachment .</span></span> <span data-ttu-id="63780-147">.</span><span class="sxs-lookup"><span data-stu-id="63780-147">.</span></span> <span data-ttu-id="63780-148">.</span><span class="sxs-lookup"><span data-stu-id="63780-148">.</span></span> <span data-ttu-id="63780-149">文件扩展名匹配。</span><span class="sxs-lookup"><span data-stu-id="63780-149">file extension matches .</span></span> <span data-ttu-id="63780-150">.</span><span class="sxs-lookup"><span data-stu-id="63780-150">.</span></span> <span data-ttu-id="63780-151">.</span><span class="sxs-lookup"><span data-stu-id="63780-151">.</span></span>|
|<span data-ttu-id="63780-152">指定字词或短语</span><span class="sxs-lookup"><span data-stu-id="63780-152">Specify words or phrases</span></span>|<span data-ttu-id="63780-153">添加以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="63780-153">Add these file types:</span></span> <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|<span data-ttu-id="63780-154">执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="63780-154">Do the following .</span></span> <span data-ttu-id="63780-155">.</span><span class="sxs-lookup"><span data-stu-id="63780-155">.</span></span> <span data-ttu-id="63780-156">.</span><span class="sxs-lookup"><span data-stu-id="63780-156">.</span></span>|<span data-ttu-id="63780-157">使用邮件通知收件人</span><span class="sxs-lookup"><span data-stu-id="63780-157">Notify the recipient with a message</span></span>|
|<span data-ttu-id="63780-158">提供邮件文本</span><span class="sxs-lookup"><span data-stu-id="63780-158">Provide message text</span></span>|<span data-ttu-id="63780-159">请勿从不知道的人打开这些类型的文件，因为它们可能包含恶意代码的宏。</span><span class="sxs-lookup"><span data-stu-id="63780-159">Do not open these types of files from people you do not know because they might contain macros with malicious code.</span></span>|

<span data-ttu-id="63780-160">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="63780-160">For more information, see:</span></span>

- [<span data-ttu-id="63780-161">勒索软件：如何降低风险</span><span class="sxs-lookup"><span data-stu-id="63780-161">Ransomware: how to reduce risk</span></span>](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [<span data-ttu-id="63780-162">还原你的 OneDrive</span><span class="sxs-lookup"><span data-stu-id="63780-162">Restore your OneDrive</span></span>](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="63780-163">停止电子邮件的自动转发</span><span class="sxs-lookup"><span data-stu-id="63780-163">Stop auto-forwarding for email</span></span>

<span data-ttu-id="63780-164">通过将邮箱设置为自动转发电子邮件，获取对用户邮箱的访问权限的黑客可以盗取您的邮件。</span><span class="sxs-lookup"><span data-stu-id="63780-164">Hackers who gain access to a user's mailbox can steal your mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="63780-165">即使没有用户的意识，也会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="63780-165">This can happen even without the user's awareness.</span></span> <span data-ttu-id="63780-166">您可以通过配置邮件流规则来防止这种情况发生。</span><span class="sxs-lookup"><span data-stu-id="63780-166">You can prevent this from happening by configuring a mail flow rule.</span></span>

<span data-ttu-id="63780-167">若要创建邮件传输规则，请观看 [此简短视频](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) 或按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="63780-167">To create a mail transport rule, either watch [this short video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>

1. <span data-ttu-id="63780-168">在 Microsoft 365 管理中心，单击 " **管理中心** \> **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="63780-168">In the Microsoft 365 admin center, click **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="63780-169">在 " **邮件流** " 类别中，单击 " **规则**"。</span><span class="sxs-lookup"><span data-stu-id="63780-169">In the **mail flow** category, click **rules**.</span></span>

3. <span data-ttu-id="63780-170">单击 **+** ""，然后单击 " **创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="63780-170">Click **+**, and then click **Create a new rule**.</span></span>

4. <span data-ttu-id="63780-171">单击对话框底部的 " **更多选项** " 以查看完整的选项集。</span><span class="sxs-lookup"><span data-stu-id="63780-171">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="63780-172">应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="63780-172">Apply the settings in the following table.</span></span> <span data-ttu-id="63780-173">将其余设置保留为默认值，除非您要对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="63780-173">Leave the rest of the settings at the default, unless you want to change them.</span></span>

6. <span data-ttu-id="63780-174">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63780-174">Click **Save**.</span></span>

|<span data-ttu-id="63780-175">设置</span><span class="sxs-lookup"><span data-stu-id="63780-175">Setting</span></span>|<span data-ttu-id="63780-176">在打开 Office 文件附件之前警告用户</span><span class="sxs-lookup"><span data-stu-id="63780-176">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="63780-177">名称</span><span class="sxs-lookup"><span data-stu-id="63780-177">Name</span></span>|<span data-ttu-id="63780-178">阻止电子邮件自动转发到外部域</span><span class="sxs-lookup"><span data-stu-id="63780-178">Prevent auto forwarding of email to external domains</span></span>|
|<span data-ttu-id="63780-179">在以下情况应用此规则 .。。</span><span class="sxs-lookup"><span data-stu-id="63780-179">Apply this rule if ...</span></span>|<span data-ttu-id="63780-180">发件人。</span><span class="sxs-lookup"><span data-stu-id="63780-180">The sender .</span></span> <span data-ttu-id="63780-181">.</span><span class="sxs-lookup"><span data-stu-id="63780-181">.</span></span> <span data-ttu-id="63780-182">.</span><span class="sxs-lookup"><span data-stu-id="63780-182">.</span></span> <span data-ttu-id="63780-183">为外部/内部。</span><span class="sxs-lookup"><span data-stu-id="63780-183">is external/internal .</span></span> <span data-ttu-id="63780-184">.</span><span class="sxs-lookup"><span data-stu-id="63780-184">.</span></span> <span data-ttu-id="63780-185">.</span><span class="sxs-lookup"><span data-stu-id="63780-185">.</span></span> <span data-ttu-id="63780-186">组织内部</span><span class="sxs-lookup"><span data-stu-id="63780-186">Inside the organization</span></span>|
|<span data-ttu-id="63780-187">添加条件</span><span class="sxs-lookup"><span data-stu-id="63780-187">Add condition</span></span>|<span data-ttu-id="63780-188">邮件属性。</span><span class="sxs-lookup"><span data-stu-id="63780-188">The message properties .</span></span> <span data-ttu-id="63780-189">.</span><span class="sxs-lookup"><span data-stu-id="63780-189">.</span></span> <span data-ttu-id="63780-190">.</span><span class="sxs-lookup"><span data-stu-id="63780-190">.</span></span> <span data-ttu-id="63780-191">包含邮件类型。</span><span class="sxs-lookup"><span data-stu-id="63780-191">include the message type .</span></span> <span data-ttu-id="63780-192">.</span><span class="sxs-lookup"><span data-stu-id="63780-192">.</span></span> <span data-ttu-id="63780-193">.</span><span class="sxs-lookup"><span data-stu-id="63780-193">.</span></span> <span data-ttu-id="63780-194">自动转发</span><span class="sxs-lookup"><span data-stu-id="63780-194">Auto-forward</span></span>|
|<span data-ttu-id="63780-195">执行以下操作 .。。</span><span class="sxs-lookup"><span data-stu-id="63780-195">Do the following ...</span></span>|<span data-ttu-id="63780-196">阻止邮件。</span><span class="sxs-lookup"><span data-stu-id="63780-196">Block the message .</span></span> <span data-ttu-id="63780-197">.</span><span class="sxs-lookup"><span data-stu-id="63780-197">.</span></span> <span data-ttu-id="63780-198">.</span><span class="sxs-lookup"><span data-stu-id="63780-198">.</span></span> <span data-ttu-id="63780-199">拒绝邮件并提供说明。</span><span class="sxs-lookup"><span data-stu-id="63780-199">reject the message and include an explanation.</span></span>|
|<span data-ttu-id="63780-200">提供邮件文本</span><span class="sxs-lookup"><span data-stu-id="63780-200">Provide message text</span></span>|<span data-ttu-id="63780-201">出于安全考虑，将阻止此组织外部的自动转发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="63780-201">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>|

## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="63780-202">保护你的电子邮件免受网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="63780-202">Protect your email from phishing attacks</span></span>

<span data-ttu-id="63780-203">如果您为 Office 365 或 Microsoft 365 环境配置了一个或多个自定义域，则可以配置目标的反网络钓鱼保护。</span><span class="sxs-lookup"><span data-stu-id="63780-203">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="63780-204">ATP 反网络钓鱼保护是 Office 365 高级威胁防护的一部分，可帮助保护您的组织免受基于恶意模拟的网络钓鱼攻击和其他网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="63780-204">ATP anti-phishing protection, part of Office 365 Advanced Threat Protection, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="63780-205">如果尚未配置自定义域，则无需执行此操作。</span><span class="sxs-lookup"><span data-stu-id="63780-205">If you haven't configured a custom domain, you don't need to do this.</span></span>

<span data-ttu-id="63780-206">我们建议您通过创建策略来保护最重要的用户和您的自定义域，以此来开始保护。</span><span class="sxs-lookup"><span data-stu-id="63780-206">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span>

<span data-ttu-id="63780-207">若要创建 ATP 反网络钓鱼策略，请观看 [此简短的培训视频](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="63780-207">To create an ATP anti-phishing policy, watch [this short training video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>

1. <span data-ttu-id="63780-208">转到 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="63780-208">Go to <https://protection.office.com>.</span></span>

2. <span data-ttu-id="63780-209">在安全 & 合规性中心的左侧导航窗格中的 " **威胁管理**" 下，选择 " **策略**"。</span><span class="sxs-lookup"><span data-stu-id="63780-209">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="63780-210">在 " **策略** " 页上，选择 " **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="63780-210">On the **Policy** page, choose **ATP anti-phishing**.</span></span>

4. <span data-ttu-id="63780-211">在 " **反钓鱼网站** " 页上，选择 " **+ 创建**"。</span><span class="sxs-lookup"><span data-stu-id="63780-211">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="63780-212">向导将启动，引导您完成定义您的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="63780-212">A wizard launches that steps you through defining your anti-phishing policy.</span></span>

5. <span data-ttu-id="63780-213">按照下表中的建议，指定策略的名称、说明和设置。</span><span class="sxs-lookup"><span data-stu-id="63780-213">Specify the name, description, and settings for your policy as recommended in the chart below.</span></span> <span data-ttu-id="63780-214">有关详细信息，请参阅 [了解 ATP 反网络钓鱼策略选项](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="63780-214">For more information, see [Learn about ATP anti-phishing policy options](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).</span></span>

6. <span data-ttu-id="63780-215">查看设置后，根据需要选择 " **创建此策略** " 或 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="63780-215">After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="63780-216">设置或选项</span><span class="sxs-lookup"><span data-stu-id="63780-216">Setting or option</span></span>|<span data-ttu-id="63780-217">推荐设置</span><span class="sxs-lookup"><span data-stu-id="63780-217">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="63780-218">名称</span><span class="sxs-lookup"><span data-stu-id="63780-218">Name</span></span>|<span data-ttu-id="63780-219">域和最有价值的市场活动员工</span><span class="sxs-lookup"><span data-stu-id="63780-219">Domain and most valuable campaign staff</span></span>|
|<span data-ttu-id="63780-220">说明</span><span class="sxs-lookup"><span data-stu-id="63780-220">Description</span></span>|<span data-ttu-id="63780-221">确保不会模拟大多数重要的人员和我们的域。</span><span class="sxs-lookup"><span data-stu-id="63780-221">Ensure most important staff and our domain are not being impersonated.</span></span>|
|<span data-ttu-id="63780-222">添加要保护的用户</span><span class="sxs-lookup"><span data-stu-id="63780-222">Add users to protect</span></span>|<span data-ttu-id="63780-223">选择 **+ 添加条件，收件人为**。</span><span class="sxs-lookup"><span data-stu-id="63780-223">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="63780-224">键入用户名称或输入候选人、活动经理和其他重要教职员工成员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="63780-224">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="63780-225">您最大可以添加20个要从模拟中保护的内部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="63780-225">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>|
|<span data-ttu-id="63780-226">添加要保护的域</span><span class="sxs-lookup"><span data-stu-id="63780-226">Add domains to protect</span></span>|<span data-ttu-id="63780-227">选择 **"+ 添加条件，收件人域为"**。</span><span class="sxs-lookup"><span data-stu-id="63780-227">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="63780-228">输入与 Microsoft 365 订阅关联的自定义域（如果已定义一个）。</span><span class="sxs-lookup"><span data-stu-id="63780-228">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="63780-229">您可以输入一个以上的域。</span><span class="sxs-lookup"><span data-stu-id="63780-229">You can enter more than one domain.</span></span>|
|<span data-ttu-id="63780-230">选择操作</span><span class="sxs-lookup"><span data-stu-id="63780-230">Choose actions</span></span>|<span data-ttu-id="63780-231">如果模拟用户发送电子邮件：选择 "**将邮件重定向到另一个电子邮件地址**"，然后键入安全管理员的电子邮件地址;例如，*刘爱琳 <span> <span> @contoso .com*。</span><span class="sxs-lookup"><span data-stu-id="63780-231">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span> <br/> <span data-ttu-id="63780-232">如果电子邮件是由模拟域发送的：请选择“隔离邮件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63780-232">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>|
|<span data-ttu-id="63780-233">邮箱智能</span><span class="sxs-lookup"><span data-stu-id="63780-233">Mailbox intelligence</span></span>|<span data-ttu-id="63780-234">默认情况下，创建新的反钓鱼策略时，将选择邮箱智能。</span><span class="sxs-lookup"><span data-stu-id="63780-234">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="63780-235">最好将此设置保留为“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63780-235">Leave this setting **On** for best results.</span></span>|
|<span data-ttu-id="63780-236">添加受信任的发件人和域</span><span class="sxs-lookup"><span data-stu-id="63780-236">Add trusted senders and domains</span></span>|<span data-ttu-id="63780-237">你可以在此处添加你自己的域或任何其他受信任域。</span><span class="sxs-lookup"><span data-stu-id="63780-237">Here you can add your own domain, or any other trusted domains.</span></span>|
|<span data-ttu-id="63780-238">应用于</span><span class="sxs-lookup"><span data-stu-id="63780-238">Applied to</span></span>|<span data-ttu-id="63780-239">选择“收件人域为”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63780-239">Select **The recipient domain is**.</span></span> <span data-ttu-id="63780-240">在“以下任何项”\*\*\*\* 中，选择“选择”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63780-240">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="63780-241">选择“+ 添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63780-241">Select **+ Add**.</span></span> <span data-ttu-id="63780-242">选中域名称旁边的复选框，例如 " *contoso"。 <span> <span>com*，请在列表中，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="63780-242">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="63780-243">选择“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63780-243">Select **Done**.</span></span>|

<span data-ttu-id="63780-244">有关详细信息，请参阅 [设置 Office 365 ATP 反网络钓鱼策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="63780-244">For more information, see [Set up Office 365 ATP anti-phishing policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).</span></span>

## <a name="protect-against-malicious-attachments-files-and-links-with-advanced-threat-protection-atp"></a><span data-ttu-id="63780-245">针对具有高级威胁防护 (ATP) 的恶意附件、文件和链接进行防护</span><span class="sxs-lookup"><span data-stu-id="63780-245">Protect against malicious attachments, files, and links with Advanced Threat Protection (ATP)</span></span>

![指向的标题 https://aka.ms/aboutM365preview 。](../media/m365admincenterchanging.png)

<span data-ttu-id="63780-247">首先，请确保在管理中心中 <https://admin.microsoft.com> 打开了新的管理中心预览。</span><span class="sxs-lookup"><span data-stu-id="63780-247">First, make sure, in the admin center at <https://admin.microsoft.com> that you have the new admin center preview turned on.</span></span> <span data-ttu-id="63780-248">打开 **新管理中心**的文本旁边的切换。</span><span class="sxs-lookup"><span data-stu-id="63780-248">Turn on the toggle next to the text **The new admin center**.</span></span>

   ![上的新管理中心预览。](../media/previewon.png)

<span data-ttu-id="63780-250">如果你的租户中未显示包含卡的 **安装程序** 页，请参阅 how To complete Security & 合规中心中的 "如何完成这些步骤"。</span><span class="sxs-lookup"><span data-stu-id="63780-250">If you don't see the **Setup** page with cards in your tenant yet, see how to complete these steps in Security & Compliance Center.</span></span> <span data-ttu-id="63780-251">请参阅 [在安全 & 合规性中心中设置 atp 安全附件](#set-up-atp-safe-attachments-in-the-security--compliance-center) ，并 [在安全 & 合规性中心中设置 atp 安全链接](#set-up-atp-safe-links-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="63780-251">See [Set up ATP safe attachments in the Security & Compliance Center](#set-up-atp-safe-attachments-in-the-security--compliance-center) and [Set up ATP Safe Links in the Security & Compliance Center](#set-up-atp-safe-links-in-the-security--compliance-center).</span></span>

1. <span data-ttu-id="63780-252">在左侧导航中，选择 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="63780-252">In the left nav, choose **Setup**.</span></span>
2. <span data-ttu-id="63780-253">在 "**安装程序**" 页上，选择 "**增强来自高级威胁的保护**" 卡片上的 "**查看**"。</span><span class="sxs-lookup"><span data-stu-id="63780-253">On the **Setup** page, choose **View** on the **Increase protection from advanced threats** card.</span></span>

   ![选择 "从高级威胁提高保护" 上的 "查看"。](../media/startatp.png)

3. <span data-ttu-id="63780-255">在 " **提高来自高级威胁的保护** " 页上，选择 " **已启动**"。</span><span class="sxs-lookup"><span data-stu-id="63780-255">On the **Increase protection from advanced threats** page, choose **Get started**.</span></span>
4. <span data-ttu-id="63780-256">在打开的窗格中，选中 "电子邮件中的 **链接和附件**" 旁边的复选框、"在 **SharePoint、OneDrive 和团队中扫描文件**" 和 "扫描项目中的 office **Online 应用程序** " 中的链接， **以查找恶意内容**。</span><span class="sxs-lookup"><span data-stu-id="63780-256">On the pane that opens, select the check boxes next to **Links and attachments in email**, **Scan files in SharePoint, OneDrive, and Teams**, and **Scan links in Office desktop and Office Online apps** under **Scan items for malicious content**.</span></span>

   <span data-ttu-id="63780-257">**在 "电子邮件中的链接和附件**" 下，键入所有用户或要扫描其电子邮件的特定用户。</span><span class="sxs-lookup"><span data-stu-id="63780-257">Under **Links and attachments in email**, Type in All Users, or the specific users whose email you want scanned.</span></span>

   ![选中 "增强对来自高级威胁的保护" 中的所有复选框。](../media/setatp.png)

5. <span data-ttu-id="63780-259">选择 " **创建策略** " 以打开 ATP 安全附件和 atp 安全链接。</span><span class="sxs-lookup"><span data-stu-id="63780-259">Choose **Create policies** to turn on ATP safe attachments and ATP safe links.</span></span>

### <a name="set-up-atp-safe-attachments-in-the-security--compliance-center"></a><span data-ttu-id="63780-260">在安全 & 合规中心中设置 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="63780-260">Set up ATP safe attachments in the Security & Compliance Center</span></span>

<span data-ttu-id="63780-261">用户定期发送、接收和共享附件，如文档、演示文稿、电子表格等。</span><span class="sxs-lookup"><span data-stu-id="63780-261">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="63780-262">只需查看一封电子邮件，就能判断附件是安全还是恶意的，并不总是容易。</span><span class="sxs-lookup"><span data-stu-id="63780-262">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="63780-263">Office 365 高级威胁防护包括 ATP 安全附件保护，但默认情况下不启用此保护。</span><span class="sxs-lookup"><span data-stu-id="63780-263">Office 365 Advanced Threat Protection includes ATP Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="63780-264">我们建议您创建一个新规则以开始使用此保护。</span><span class="sxs-lookup"><span data-stu-id="63780-264">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="63780-265">此保护功能扩展到 SharePoint、OneDrive 和 Microsoft 团队中的文件。</span><span class="sxs-lookup"><span data-stu-id="63780-265">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>

<span data-ttu-id="63780-266">若要创建 ATP 安全附件策略，请观看 [此简短视频](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="63780-266">To create an ATP safe attachment policy, either watch [this short video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>

1. <span data-ttu-id="63780-267">转到 <https://protection.office.com> 并使用管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="63780-267">Go to <https://protection.office.com> and sign in with your admin account.</span></span>

2. <span data-ttu-id="63780-268">在安全 & 合规性中心的左侧导航窗格中的 " **威胁管理**" 下，选择 " **策略**"。</span><span class="sxs-lookup"><span data-stu-id="63780-268">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="63780-269">在 "策略" 页上，选择 " **ATP 安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="63780-269">On the Policy page, choose **ATP safe attachments**.</span></span>

4. <span data-ttu-id="63780-270">在 "安全附件" 页面上，选中 " **启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP** " 复选框，以应用广泛的保护。</span><span class="sxs-lookup"><span data-stu-id="63780-270">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span>

5. <span data-ttu-id="63780-271">选择 **+** 以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="63780-271">Select **+** to create a new policy.</span></span>

6. <span data-ttu-id="63780-272">应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="63780-272">Apply the settings in the following table.</span></span>

7. <span data-ttu-id="63780-273">查看设置后，根据需要选择 " **创建此策略** " 或 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="63780-273">After you review your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="63780-274">设置或选项</span><span class="sxs-lookup"><span data-stu-id="63780-274">Setting or option</span></span>|<span data-ttu-id="63780-275">推荐设置</span><span class="sxs-lookup"><span data-stu-id="63780-275">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="63780-276">名称</span><span class="sxs-lookup"><span data-stu-id="63780-276">Name</span></span>|<span data-ttu-id="63780-277">使用检测到的恶意软件阻止当前和将来的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="63780-277">Block current and future emails with detected malware.</span></span>|
|<span data-ttu-id="63780-278">说明</span><span class="sxs-lookup"><span data-stu-id="63780-278">Description</span></span>|<span data-ttu-id="63780-279">使用检测到的恶意软件阻止当前和将来的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="63780-279">Block current and future emails and attachments with detected malware.</span></span>|
|<span data-ttu-id="63780-280">保存附件未知的恶意软件响应</span><span class="sxs-lookup"><span data-stu-id="63780-280">Save attachments unknown malware response</span></span>|<span data-ttu-id="63780-281">Select **block-阻止当前和将来的包含检测到的恶意软件的电子邮件和附件**。</span><span class="sxs-lookup"><span data-stu-id="63780-281">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>|
|<span data-ttu-id="63780-282">在检测时重定向附件</span><span class="sxs-lookup"><span data-stu-id="63780-282">Redirect attachment on detection</span></span>|<span data-ttu-id="63780-283">启用重定向 (选中此框) </span><span class="sxs-lookup"><span data-stu-id="63780-283">Enable redirection (select this box)</span></span> <br/> <span data-ttu-id="63780-284">输入用于隔离的管理员帐户或邮箱设置。</span><span class="sxs-lookup"><span data-stu-id="63780-284">Enter the admin account or a mailbox setup for quarantine.</span></span> <br/> <span data-ttu-id="63780-285">如果恶意软件扫描附件超时或发生错误，则应用上述选择) 。 (选中该框。</span><span class="sxs-lookup"><span data-stu-id="63780-285">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>|
|<span data-ttu-id="63780-286">应用于</span><span class="sxs-lookup"><span data-stu-id="63780-286">Applied to</span></span>|<span data-ttu-id="63780-287">收件人域为。</span><span class="sxs-lookup"><span data-stu-id="63780-287">The recipient domain is .</span></span> <span data-ttu-id="63780-288">.</span><span class="sxs-lookup"><span data-stu-id="63780-288">.</span></span> <span data-ttu-id="63780-289">.</span><span class="sxs-lookup"><span data-stu-id="63780-289">.</span></span> <span data-ttu-id="63780-290">选择您的域。</span><span class="sxs-lookup"><span data-stu-id="63780-290">select your domain.</span></span>|

<span data-ttu-id="63780-291">有关详细信息，请参阅 [设置 Office 365 ATP 反网络钓鱼策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="63780-291">For more information, see [Set up Office 365 ATP anti-phishing policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).</span></span>

### <a name="set-up-atp-safe-links-in-the-security--compliance-center"></a><span data-ttu-id="63780-292">在安全 & 合规中心中设置 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="63780-292">Set up ATP Safe Links in the Security & Compliance Center</span></span>

<span data-ttu-id="63780-293">黑客有时会在电子邮件或其他文件的链接中隐藏恶意网站。</span><span class="sxs-lookup"><span data-stu-id="63780-293">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="63780-294">Office 365 ATP 安全链接 (ATP 安全链接) （Office 365 高级威胁防护的一部分）可以通过提供电子邮件和 Office 文档中) 的 web (地址的单击验证，从而帮助保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="63780-294">Office 365 ATP Safe Links (ATP Safe Links), part of Office 365 Advanced Threat Protection, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="63780-295">通过 ATP 安全链接策略定义保护。</span><span class="sxs-lookup"><span data-stu-id="63780-295">Protection is defined through ATP Safe Links policies.</span></span>

<span data-ttu-id="63780-296">我们建议您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="63780-296">We recommend that you do the following:</span></span>

- <span data-ttu-id="63780-297">修改默认策略以提高保护。</span><span class="sxs-lookup"><span data-stu-id="63780-297">Modify the default policy to increase protection.</span></span>

- <span data-ttu-id="63780-298">添加目标为域中所有收件人的新策略。</span><span class="sxs-lookup"><span data-stu-id="63780-298">Add a new policy targeted to all recipients in your domain.</span></span>

<span data-ttu-id="63780-299">若要设置 ATP 安全链接，请观看 [此简短的培训视频](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="63780-299">To set up ATP Safe Links, watch [this short training video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>

1. <span data-ttu-id="63780-300">转到 <https://protection.office.com> 并使用管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="63780-300">Go to <https://protection.office.com> and sign in with your admin account.</span></span>

2. <span data-ttu-id="63780-301">在安全 & 合规性中心的左侧导航窗格中的 " **威胁管理**" 下，选择 " **策略**"。</span><span class="sxs-lookup"><span data-stu-id="63780-301">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="63780-302">在 "策略" 页上，选择 " **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="63780-302">On the Policy page, choose **ATP Safe Links**.</span></span>

<span data-ttu-id="63780-303">若要修改默认策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="63780-303">To modify the default policy:</span></span>

1. <span data-ttu-id="63780-304">在 "安全链接" 页面上，在 " **适用于整个组织的策略**" 下，选择 " **默认** 策略"。</span><span class="sxs-lookup"><span data-stu-id="63780-304">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span>

2. <span data-ttu-id="63780-305">在 " **适用于除电子邮件以外的内容的设置**" 下，选择 "适用于 **企业的 Microsoft 365 应用，Office For iOS 和 Android**"。</span><span class="sxs-lookup"><span data-stu-id="63780-305">Under **Settings that apply to content except email**, select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.</span></span>

3. <span data-ttu-id="63780-306">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63780-306">Click **Save**.</span></span>

<span data-ttu-id="63780-307">创建一个面向域中所有收件人的新策略：</span><span class="sxs-lookup"><span data-stu-id="63780-307">To create a new policy targeted to all recipients in your domain:</span></span>

1. <span data-ttu-id="63780-308">在 "安全链接" 页面上，在 " **适用于整个组织的策略**" 下，单击 " **+** 创建新策略"。</span><span class="sxs-lookup"><span data-stu-id="63780-308">On the Safe links page, under **Policies that apply to the entire organization**, click **+** to create a new policy.</span></span>

2. <span data-ttu-id="63780-309">应用下表中列出的设置。</span><span class="sxs-lookup"><span data-stu-id="63780-309">Apply the settings listed in the following table.</span></span>

3. <span data-ttu-id="63780-310">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63780-310">Click **Save**.</span></span>

|<span data-ttu-id="63780-311">设置或选项</span><span class="sxs-lookup"><span data-stu-id="63780-311">Setting or option</span></span>|<span data-ttu-id="63780-312">推荐设置</span><span class="sxs-lookup"><span data-stu-id="63780-312">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="63780-313">名称</span><span class="sxs-lookup"><span data-stu-id="63780-313">Name</span></span>|<span data-ttu-id="63780-314">域中所有收件人的安全链接策略</span><span class="sxs-lookup"><span data-stu-id="63780-314">Safe links policy for all recipients in the domain</span></span>|
|<span data-ttu-id="63780-315">选择邮件中未知的潜在恶意 Url 的操作</span><span class="sxs-lookup"><span data-stu-id="63780-315">Select the action for unknown potentially malicious URLs in messages</span></span>|<span data-ttu-id="63780-316">**当用户单击链接时，将会重写并检查在已知恶意链接列表中的 "按 Url"，并对其进行检查**。</span><span class="sxs-lookup"><span data-stu-id="63780-316">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>|
|<span data-ttu-id="63780-317">使用安全附件扫描可下载的内容</span><span class="sxs-lookup"><span data-stu-id="63780-317">Use Safe Attachments to scan downloadable content</span></span>|<span data-ttu-id="63780-318">选中此框。</span><span class="sxs-lookup"><span data-stu-id="63780-318">Select this box.</span></span>|
|<span data-ttu-id="63780-319">应用于</span><span class="sxs-lookup"><span data-stu-id="63780-319">Applied to</span></span>|<span data-ttu-id="63780-320">收件人域为。</span><span class="sxs-lookup"><span data-stu-id="63780-320">The recipient domain is .</span></span> <span data-ttu-id="63780-321">.</span><span class="sxs-lookup"><span data-stu-id="63780-321">.</span></span> <span data-ttu-id="63780-322">.</span><span class="sxs-lookup"><span data-stu-id="63780-322">.</span></span> <span data-ttu-id="63780-323">选择您的域。</span><span class="sxs-lookup"><span data-stu-id="63780-323">select your domain.</span></span>|

<span data-ttu-id="63780-324">有关详细信息，请参阅 [Office 365 ATP 中的安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="63780-324">For more information, see [Safe Links in Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).</span></span>

## <a name="turn-on-the-unified-audit-log"></a><span data-ttu-id="63780-325">打开统一审核日志</span><span class="sxs-lookup"><span data-stu-id="63780-325">Turn on the Unified Audit Log</span></span>

<span data-ttu-id="63780-326">在安全 & 合规中心中打开审核日志搜索之后，您可以将管理员和其他用户活动保留在日志中并进行搜索。</span><span class="sxs-lookup"><span data-stu-id="63780-326">After you turn on the audit log search in the Security & Compliance Center, you can retain the admin and other user activity in the log and search it.</span></span>

<span data-ttu-id="63780-327">您必须在 Exchange Online 中向您分配 "审核日志" 角色，以便在 Microsoft 365 订阅中打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="63780-327">You must be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 subscription.</span></span> <span data-ttu-id="63780-328">默认情况下，此角色在 Exchange 管理中心中的 "权限" 页上分配给合规性管理和组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="63780-328">By default, this role is assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="63780-329">默认情况下，Microsoft 365 中的全局管理员是此组的成员。</span><span class="sxs-lookup"><span data-stu-id="63780-329">Global admins in Microsoft 365 are members of this group by default.</span></span>

1. <span data-ttu-id="63780-330">若要启用审核日志搜索，请转到管理中心， <https://admin.microsoft.com> 然后在左侧导航中的 "**管理中心**" 下选择 "**合规性**"。</span><span class="sxs-lookup"><span data-stu-id="63780-330">To turn on the audit log search on, go to the admin center at <https://admin.microsoft.com> and then choose **Compliance** under **Admin centers** in the left nav.</span></span>
2. <span data-ttu-id="63780-331">在 " **Microsoft 365 合规性** " 页面上，选择 " **更多资源**"，然后 **打开** " **Office 365 安全 & 中心** 卡"。</span><span class="sxs-lookup"><span data-stu-id="63780-331">On the **Microsoft 365 compliance** page, choose **More resources**, and then **Open** on the **Office 365 security & center** card.</span></span>

    ![在安全 & 合规性轿车上选择 "打开"。](../media/gotosecandcomp.png)
3. <span data-ttu-id="63780-333">在 "安全性和合规性" 页上，依次选择 " **搜索** " 和 " **审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="63780-333">On the security and compliance page, choose **Search** and then **Audit log search**.</span></span>
4. <span data-ttu-id="63780-334">在 " **审核日志搜索** " 页的顶部，选择 " **启用审核**"。</span><span class="sxs-lookup"><span data-stu-id="63780-334">On the top of the **Audit log search** page, choose **Turn on auditing**.</span></span>

<span data-ttu-id="63780-335">打开该功能后，您可以搜索文件、文件夹和多个活动。</span><span class="sxs-lookup"><span data-stu-id="63780-335">After the feature is turned on, you can search for files, folders, and many activities.</span></span> <span data-ttu-id="63780-336">有关详细信息，请参阅 [搜索审核日志](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="63780-336">For more information, see [search the audit log](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a><span data-ttu-id="63780-337">优化 SharePoint 和 OneDrive 文件和文件夹的匿名共享设置</span><span class="sxs-lookup"><span data-stu-id="63780-337">Tune-up anonymous sharing settings for SharePoint and OneDrive files and folders</span></span>

<span data-ttu-id="63780-338"> (将默认匿名链接过期时间更改为14天，请将默认共享类型更改为 "特定人员" ) 以更改 OneDrive 和 SharePoint 的共享设置：</span><span class="sxs-lookup"><span data-stu-id="63780-338">(change default anonymous link expiration to 14 days, change default sharing type to "Specific People") To change the sharing settings for OneDrive and SharePoint:</span></span>

1. <span data-ttu-id="63780-339">转到 "管理中心" <https://admin.microsoft.com> ，然后在左侧导航中选择 "**管理中心**" 下的 " **SharePoint** "。</span><span class="sxs-lookup"><span data-stu-id="63780-339">Go to the admin center at <https://admin.microsoft.com> and then choose **SharePoint** under **Admin centers** in the left nav.</span></span>
2. <span data-ttu-id="63780-340">在 SharePoint 管理中心中，转到 " **策略** \> **共享**"。</span><span class="sxs-lookup"><span data-stu-id="63780-340">In the SharePoint admin center, go to **Policies** \> **Sharing**.</span></span>
3. <span data-ttu-id="63780-341">在 " **共享** " 页面的 " **文件和文件夹链接**" 下，选择 " **特定人员**"，在 **"任何人" 链接的 "高级设置**" 下，选择 " **这些链接必须在此天数内过期**"，并键入 14 (或要将链接生存期限制为) 的其他天数。</span><span class="sxs-lookup"><span data-stu-id="63780-341">On the **Sharing** page, under **File and folder links**, select **Specific people**, and under **Advanced settings for "Anyone" links**, select **These links must expire within this many days**, and type in 14 (or another number of days you want to restrict the link lifetime to).</span></span>

   ![选择 "特定人员"，并将 "链接过期" 设置为14天。](../media/anyonelinks.png)

## <a name="activity-alerts"></a><span data-ttu-id="63780-343">活动通知</span><span class="sxs-lookup"><span data-stu-id="63780-343">Activity alerts</span></span>

<span data-ttu-id="63780-344">您可以使用活动警报跟踪管理员和用户活动，并检测组织中的恶意软件和数据丢失防护事件。</span><span class="sxs-lookup"><span data-stu-id="63780-344">You can use activity alerts to track admin and user activities and detect malware and data loss prevention incidents in your organization.</span></span> <span data-ttu-id="63780-345">你的订阅包含一组默认策略，但你也可以创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="63780-345">Your subscription includes a set of default policies, but you can also create custom ones.</span></span> <span data-ttu-id="63780-346">有关详细信息，请参阅 [警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)。</span><span class="sxs-lookup"><span data-stu-id="63780-346">For more information, see [alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span> <span data-ttu-id="63780-347">例如，如果您在 SharePoint 中存储不希望任何人在外部共享的重要文件，则可以创建通知，以便在用户确实共享时通知您。</span><span class="sxs-lookup"><span data-stu-id="63780-347">For example, if you store an important file in SharePoint that you don't want anyone to share externally, you can create a notification that alerts you if someone does share it.</span></span>

<span data-ttu-id="63780-348">下图显示了 Microsoft 365 附带的默认策略。</span><span class="sxs-lookup"><span data-stu-id="63780-348">The following figure shows the default policies that are included with Microsoft 365.</span></span>

![Microsoft 365 附带的默认通知策略](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a><span data-ttu-id="63780-350">禁用或管理日历共享</span><span class="sxs-lookup"><span data-stu-id="63780-350">Disable or manage calendar sharing</span></span>

<span data-ttu-id="63780-351">您可以阻止组织中的人员共享其日历，也可以管理他们可以共享的内容。</span><span class="sxs-lookup"><span data-stu-id="63780-351">You can prevent people in your organization from sharing their calendars, or you can also manage what they can share.</span></span> <span data-ttu-id="63780-352">例如，您可以将共享限制为仅限共享忙/闲时间。</span><span class="sxs-lookup"><span data-stu-id="63780-352">For example, you can restrict the sharing to free/busy times only.</span></span>

1. <span data-ttu-id="63780-353">转到管理中心 <https://admin.microsoft.com> ，然后选择 " **设置** \> **服务 & 外接程序**"。</span><span class="sxs-lookup"><span data-stu-id="63780-353">Go to the admin center at <https://admin.microsoft.com> and choose **Settings** \> **Services & add-ins**.</span></span>
2. <span data-ttu-id="63780-354">在 " **服务" & "外接程序** " 页上，选择 " **日历**"，然后选择组织中的人员是否可以与拥有 Office 365 或 Exchange 的人员或任何人共享其日历。</span><span class="sxs-lookup"><span data-stu-id="63780-354">On the **Services & add-ins** page, choose **Calendar**, and choose whether people in your organization can share their calendars with people outside who have Office 365 or Exchange, or with anyone.</span></span>

   <span data-ttu-id="63780-355">如果选择 "与任何人共享" 选项，则可以决定仅共享忙/闲信息。</span><span class="sxs-lookup"><span data-stu-id="63780-355">If you choose the share with anyone option, you can decide to also only share free/busy information.</span></span>

3. <span data-ttu-id="63780-356">在页面底部选择 " **保存更改** "。</span><span class="sxs-lookup"><span data-stu-id="63780-356">Choose **Save changes** on the bottom of the page.</span></span>

   <span data-ttu-id="63780-357">下图显示了不允许的日历共享。</span><span class="sxs-lookup"><span data-stu-id="63780-357">The following figure shows calendar sharing not allowed.</span></span>

   ![显示不允许的外部日历共享的屏幕截图。](../media/nocalendarsharing.png)

   <span data-ttu-id="63780-359">下图显示了允许使用仅忙/闲信息的电子邮件链接进行日历共享时的设置。</span><span class="sxs-lookup"><span data-stu-id="63780-359">The following figure shows the settings when calendar sharing is allowed with an email link with only free/busy information.</span></span>

   ![与任何人共享日历忙/闲信息的屏幕截图。](../media/sharefreebusy.png)

<span data-ttu-id="63780-361">如果允许您的用户共享其日历，请参阅 [这些说明](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) 了解如何从 web 上的 Outlook 共享。</span><span class="sxs-lookup"><span data-stu-id="63780-361">If your users are allowed to share their calendars, see [these instructions](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for how to share from Outlook on the web.</span></span>
