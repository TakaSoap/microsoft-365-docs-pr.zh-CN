---
title: 增强威胁防护
f1.keywords:
- NOCSH
ms.author: sharik
author: Skjerland
manager: scotv
audience: Admin
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
ms.openlocfilehash: a1f4714d5b7dcd8d6a22a07c118055e13b27e069
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398273"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a><span data-ttu-id="eb659-103">增强 Microsoft 365 订阅的威胁防护</span><span class="sxs-lookup"><span data-stu-id="eb659-103">Increase threat protection for Microsoft 365 subscription</span></span>

<span data-ttu-id="eb659-104">本文可帮助你增强 Microsoft 365 订阅中的保护，以抵御网络钓鱼、恶意软件和其他威胁。</span><span class="sxs-lookup"><span data-stu-id="eb659-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="eb659-105">这些建议适用于对安全性需求不断增加的组织，如政治宣传活动、法律办公室和医疗保健部门。</span><span class="sxs-lookup"><span data-stu-id="eb659-105">These recommendations are appropriate for organizations with an increased need for security, like political campaigns, law offices, and health care clinics.</span></span>

<span data-ttu-id="eb659-106">开始之前，请检查 Microsoft 安全分数。</span><span class="sxs-lookup"><span data-stu-id="eb659-106">Before you begin, check your Microsoft Secure Score.</span></span> <span data-ttu-id="eb659-107">Microsoft 安全分数根据常规活动和安全设置分析组织的安全性，并分配分数。</span><span class="sxs-lookup"><span data-stu-id="eb659-107">Microsoft Secure Score analyzes your organization's security based on your regular activities and security settings and assigns a score.</span></span> <span data-ttu-id="eb659-108">首先记下当前分数。</span><span class="sxs-lookup"><span data-stu-id="eb659-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="eb659-109">执行本文中推荐的操作会增加分数。</span><span class="sxs-lookup"><span data-stu-id="eb659-109">Taking the actions recommended in this article increases your score.</span></span> <span data-ttu-id="eb659-110">目标不是达到最高分，而是注意保护环境的机会，这些机会不会对用户的工作效率产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="eb659-110">The goal isn't to achieve the max score, but to be aware of opportunities to protect your environment that don't negatively affect productivity for your users.</span></span>

<span data-ttu-id="eb659-111">有关详细信息，请参阅 [Microsoft 安全分数](../security/defender/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="eb659-111">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="eb659-112">提高邮件中恶意软件防护级别</span><span class="sxs-lookup"><span data-stu-id="eb659-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="eb659-113">Office 365 或 Microsoft 365 环境包括恶意软件防护，但您可以通过阻止包含通常用于恶意软件的文件类型的附件来增强此保护。</span><span class="sxs-lookup"><span data-stu-id="eb659-113">Your Office 365 or Microsoft 365 environment includes protection against malware, but you can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="eb659-114">在电子邮件中加强恶意软件保护：</span><span class="sxs-lookup"><span data-stu-id="eb659-114">To bump up malware protection in email:</span></span>

1. <span data-ttu-id="eb659-115">转到 <https://protection.office.com> ，然后使用管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="eb659-115">Go to <https://protection.office.com> and sign in with your admin account credentials.</span></span>

2. <span data-ttu-id="eb659-116">在安全&合规中心的左侧导航窗格中，在"**威胁** 管理"下，选择"**策略** \> **""反恶意软件"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-116">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>

3. <span data-ttu-id="eb659-117">双击默认策略以编辑此公司范围内的策略。</span><span class="sxs-lookup"><span data-stu-id="eb659-117">Double-click the default policy to edit this company-wide policy.</span></span>

4. <span data-ttu-id="eb659-118">单击“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="eb659-118">Click **Settings**.</span></span>

5. <span data-ttu-id="eb659-119">在 **"常见附件类型筛选器"下，** 选择"**打开"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-119">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="eb659-120">被阻止的文件类型将在此控件正下方的窗口中列出。</span><span class="sxs-lookup"><span data-stu-id="eb659-120">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="eb659-121">请确保添加以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="eb659-121">Make sure you add these filetypes:</span></span>

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   <span data-ttu-id="eb659-122">如果需要，稍后可以添加或删除文件类型。</span><span class="sxs-lookup"><span data-stu-id="eb659-122">You can add or delete file types later, if needed.</span></span>

6. <span data-ttu-id="eb659-123">单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="eb659-123">Click **Save.**</span></span>

<span data-ttu-id="eb659-124">有关详细信息，请参阅 EOP 中的反 [恶意软件保护](../security/office-365-security/anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="eb659-124">For more information, see [Anti-malware protection in EOP](../security/office-365-security/anti-malware-protection.md).</span></span>

## <a name="protect-against-ransomware"></a><span data-ttu-id="eb659-125">防范勒索软件</span><span class="sxs-lookup"><span data-stu-id="eb659-125">Protect against ransomware</span></span>

<span data-ttu-id="eb659-126">勒索软件通过加密文件或锁定计算机屏幕来限制对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="eb659-126">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="eb659-127">然后，它尝试通过请求"勒索"（通常采用加密货币（如"Itin"）来从犯罪中勒索资金，以交换对数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="eb659-127">It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span>

<span data-ttu-id="eb659-128">您可以通过创建一个或多个邮件流规则来阻止通常用于勒索软件的文件扩展名 (这些扩展名已添加到邮件步骤) 中提高恶意软件防护级别，或警告通过电子邮件接收[](#raise-the-level-of-protection-against-malware-in-mail)这些附件的用户。</span><span class="sxs-lookup"><span data-stu-id="eb659-128">You can protect against ransomware by creating one or more mail flow rules to block file extensions that are commonly used for ransomware (these were added in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step), or to warn users who receive these attachments in email.</span></span>

<span data-ttu-id="eb659-129">除了在上一步中阻止的文件之外，在打开包含宏的 Office 文件附件之前创建一个警告用户的规则也是一个不错的做法。</span><span class="sxs-lookup"><span data-stu-id="eb659-129">In addition to the files that you blocked in the previous step, it's also good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="eb659-130">勒索软件可以隐藏在宏内，因此警告用户不要向他们不知道的人打开这些文件。</span><span class="sxs-lookup"><span data-stu-id="eb659-130">Ransomware can be hidden inside macros, so warn users to not open these files from people they don't know.</span></span>

<span data-ttu-id="eb659-131">创建邮件传输规则：</span><span class="sxs-lookup"><span data-stu-id="eb659-131">To create a mail transport rule:</span></span>

1. <span data-ttu-id="eb659-132">转到管理中心 ，然后选择 <https://admin.microsoft.com> 管理中心 \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="eb659-132">Go to the admin center at <https://admin.microsoft.com> and choose **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="eb659-133">在"**邮件流"** 类别中，单击"规则 **"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-133">In the **mail flow** category, click **rules**.</span></span>

3. <span data-ttu-id="eb659-134">单击 **+** ，然后单击"**创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-134">Click **+**, and then click **Create a new rule**.</span></span>

4. <span data-ttu-id="eb659-135">单击 **对话框** 底部的"更多选项"以查看完整的选项集。</span><span class="sxs-lookup"><span data-stu-id="eb659-135">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="eb659-136">为规则应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="eb659-136">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="eb659-137">保留其余设置为默认设置，除非您要更改它们。</span><span class="sxs-lookup"><span data-stu-id="eb659-137">Leave the rest of the settings at the default, unless you want to change them.</span></span>

6. <span data-ttu-id="eb659-138">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eb659-138">Click **Save**.</span></span>

|<span data-ttu-id="eb659-139">设置</span><span class="sxs-lookup"><span data-stu-id="eb659-139">Setting</span></span>|<span data-ttu-id="eb659-140">在打开 Office 文件的附件之前警告用户</span><span class="sxs-lookup"><span data-stu-id="eb659-140">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="eb659-141">名称</span><span class="sxs-lookup"><span data-stu-id="eb659-141">Name</span></span>|<span data-ttu-id="eb659-142">反勒索软件规则：警告用户</span><span class="sxs-lookup"><span data-stu-id="eb659-142">Anti-ransomware rule: warn users</span></span>|
|<span data-ttu-id="eb659-143">在 中应用此规则。</span><span class="sxs-lookup"><span data-stu-id="eb659-143">Apply this rule if .</span></span> <span data-ttu-id="eb659-144">.</span><span class="sxs-lookup"><span data-stu-id="eb659-144">.</span></span> <span data-ttu-id="eb659-145">.</span><span class="sxs-lookup"><span data-stu-id="eb659-145">.</span></span>|<span data-ttu-id="eb659-146">任何附件 。</span><span class="sxs-lookup"><span data-stu-id="eb659-146">Any attachment .</span></span> <span data-ttu-id="eb659-147">.</span><span class="sxs-lookup"><span data-stu-id="eb659-147">.</span></span> <span data-ttu-id="eb659-148">.</span><span class="sxs-lookup"><span data-stu-id="eb659-148">.</span></span> <span data-ttu-id="eb659-149">文件扩展名匹配 。</span><span class="sxs-lookup"><span data-stu-id="eb659-149">file extension matches .</span></span> <span data-ttu-id="eb659-150">.</span><span class="sxs-lookup"><span data-stu-id="eb659-150">.</span></span> <span data-ttu-id="eb659-151">.</span><span class="sxs-lookup"><span data-stu-id="eb659-151">.</span></span>|
|<span data-ttu-id="eb659-152">指定单词或短语</span><span class="sxs-lookup"><span data-stu-id="eb659-152">Specify words or phrases</span></span>|<span data-ttu-id="eb659-153">添加以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="eb659-153">Add these file types:</span></span> <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|<span data-ttu-id="eb659-154">执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="eb659-154">Do the following .</span></span> <span data-ttu-id="eb659-155">.</span><span class="sxs-lookup"><span data-stu-id="eb659-155">.</span></span> <span data-ttu-id="eb659-156">.</span><span class="sxs-lookup"><span data-stu-id="eb659-156">.</span></span>|<span data-ttu-id="eb659-157">使用邮件通知收件人</span><span class="sxs-lookup"><span data-stu-id="eb659-157">Notify the recipient with a message</span></span>|
|<span data-ttu-id="eb659-158">提供消息文本</span><span class="sxs-lookup"><span data-stu-id="eb659-158">Provide message text</span></span>|<span data-ttu-id="eb659-159">不要从您不知道的人打开这些类型的文件，因为它们可能包含包含恶意代码的宏。</span><span class="sxs-lookup"><span data-stu-id="eb659-159">Do not open these types of files from people you do not know because they might contain macros with malicious code.</span></span>|

<span data-ttu-id="eb659-160">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="eb659-160">For more information, see:</span></span>

- [<span data-ttu-id="eb659-161">勒索软件：如何降低风险</span><span class="sxs-lookup"><span data-stu-id="eb659-161">Ransomware: how to reduce risk</span></span>](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [<span data-ttu-id="eb659-162">还原 OneDrive</span><span class="sxs-lookup"><span data-stu-id="eb659-162">Restore your OneDrive</span></span>](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="eb659-163">停止电子邮件的自动转发</span><span class="sxs-lookup"><span data-stu-id="eb659-163">Stop auto-forwarding for email</span></span>

<span data-ttu-id="eb659-164">获取用户邮箱访问权限的黑客可以通过将邮箱设置为自动转发电子邮件来窃取您的邮件。</span><span class="sxs-lookup"><span data-stu-id="eb659-164">Hackers who gain access to a user's mailbox can steal your mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="eb659-165">即使没有用户感知，也可能发生此情况。</span><span class="sxs-lookup"><span data-stu-id="eb659-165">This can happen even without the user's awareness.</span></span> <span data-ttu-id="eb659-166">您可以通过配置邮件流规则来防止发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="eb659-166">You can prevent this from happening by configuring a mail flow rule.</span></span>

<span data-ttu-id="eb659-167">若要创建邮件传输规则，请观看此 [简短视频](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) 或执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="eb659-167">To create a mail transport rule, either watch [this short video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>

1. <span data-ttu-id="eb659-168">在 Microsoft 365 管理中心中，单击"**管理中心** \> **""Exchange"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-168">In the Microsoft 365 admin center, click **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="eb659-169">在"**邮件流"** 类别中，单击"规则 **"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-169">In the **mail flow** category, click **rules**.</span></span>

3. <span data-ttu-id="eb659-170">单击 **+** ，然后单击"**创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-170">Click **+**, and then click **Create a new rule**.</span></span>

4. <span data-ttu-id="eb659-171">单击 **对话框** 底部的"更多选项"以查看完整的选项集。</span><span class="sxs-lookup"><span data-stu-id="eb659-171">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="eb659-172">应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="eb659-172">Apply the settings in the following table.</span></span> <span data-ttu-id="eb659-173">保留其余设置为默认设置，除非您要更改它们。</span><span class="sxs-lookup"><span data-stu-id="eb659-173">Leave the rest of the settings at the default, unless you want to change them.</span></span>

6. <span data-ttu-id="eb659-174">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eb659-174">Click **Save**.</span></span>

|<span data-ttu-id="eb659-175">设置</span><span class="sxs-lookup"><span data-stu-id="eb659-175">Setting</span></span>|<span data-ttu-id="eb659-176">在打开 Office 文件的附件之前警告用户</span><span class="sxs-lookup"><span data-stu-id="eb659-176">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="eb659-177">名称</span><span class="sxs-lookup"><span data-stu-id="eb659-177">Name</span></span>|<span data-ttu-id="eb659-178">阻止电子邮件自动转发到外部域</span><span class="sxs-lookup"><span data-stu-id="eb659-178">Prevent auto forwarding of email to external domains</span></span>|
|<span data-ttu-id="eb659-179">如果 ...</span><span class="sxs-lookup"><span data-stu-id="eb659-179">Apply this rule if ...</span></span>|<span data-ttu-id="eb659-180">发件人 。</span><span class="sxs-lookup"><span data-stu-id="eb659-180">The sender .</span></span> <span data-ttu-id="eb659-181">.</span><span class="sxs-lookup"><span data-stu-id="eb659-181">.</span></span> <span data-ttu-id="eb659-182">.</span><span class="sxs-lookup"><span data-stu-id="eb659-182">.</span></span> <span data-ttu-id="eb659-183">是外部/内部 。</span><span class="sxs-lookup"><span data-stu-id="eb659-183">is external/internal .</span></span> <span data-ttu-id="eb659-184">.</span><span class="sxs-lookup"><span data-stu-id="eb659-184">.</span></span> <span data-ttu-id="eb659-185">.</span><span class="sxs-lookup"><span data-stu-id="eb659-185">.</span></span> <span data-ttu-id="eb659-186">组织内部</span><span class="sxs-lookup"><span data-stu-id="eb659-186">Inside the organization</span></span>|
|<span data-ttu-id="eb659-187">添加条件</span><span class="sxs-lookup"><span data-stu-id="eb659-187">Add condition</span></span>|<span data-ttu-id="eb659-188">邮件属性 。</span><span class="sxs-lookup"><span data-stu-id="eb659-188">The message properties .</span></span> <span data-ttu-id="eb659-189">.</span><span class="sxs-lookup"><span data-stu-id="eb659-189">.</span></span> <span data-ttu-id="eb659-190">.</span><span class="sxs-lookup"><span data-stu-id="eb659-190">.</span></span> <span data-ttu-id="eb659-191">包括邮件类型 。</span><span class="sxs-lookup"><span data-stu-id="eb659-191">include the message type .</span></span> <span data-ttu-id="eb659-192">.</span><span class="sxs-lookup"><span data-stu-id="eb659-192">.</span></span> <span data-ttu-id="eb659-193">.</span><span class="sxs-lookup"><span data-stu-id="eb659-193">.</span></span> <span data-ttu-id="eb659-194">自动转发</span><span class="sxs-lookup"><span data-stu-id="eb659-194">Auto-forward</span></span>|
|<span data-ttu-id="eb659-195">执行以下操作...</span><span class="sxs-lookup"><span data-stu-id="eb659-195">Do the following ...</span></span>|<span data-ttu-id="eb659-196">阻止邮件 。</span><span class="sxs-lookup"><span data-stu-id="eb659-196">Block the message .</span></span> <span data-ttu-id="eb659-197">.</span><span class="sxs-lookup"><span data-stu-id="eb659-197">.</span></span> <span data-ttu-id="eb659-198">.</span><span class="sxs-lookup"><span data-stu-id="eb659-198">.</span></span> <span data-ttu-id="eb659-199">拒绝邮件并给出说明。</span><span class="sxs-lookup"><span data-stu-id="eb659-199">reject the message and include an explanation.</span></span>|
|<span data-ttu-id="eb659-200">提供消息文本</span><span class="sxs-lookup"><span data-stu-id="eb659-200">Provide message text</span></span>|<span data-ttu-id="eb659-201">出于安全考虑，将阻止在此组织外自动转发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="eb659-201">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>|

## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="eb659-202">保护电子邮件免受网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="eb659-202">Protect your email from phishing attacks</span></span>

<span data-ttu-id="eb659-203">如果为 Office 365 或 Microsoft 365 环境配置了一个或多个自定义域，可以配置目标防钓鱼保护。</span><span class="sxs-lookup"><span data-stu-id="eb659-203">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="eb659-204">反网络钓鱼保护是 Microsoft Defender for Office 365 的一部分，可帮助保护你的组织免受基于恶意模拟的网络钓鱼攻击和其他网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="eb659-204">Anti-phishing protection, part of Microsoft Defender for Office 365, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="eb659-205">如果尚未配置自定义域，则无需这样做。</span><span class="sxs-lookup"><span data-stu-id="eb659-205">If you haven't configured a custom domain, you don't need to do this.</span></span>

<span data-ttu-id="eb659-206">我们建议你通过创建一个策略来保护最重要的用户和自定义域来开始使用此保护。</span><span class="sxs-lookup"><span data-stu-id="eb659-206">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span>

<span data-ttu-id="eb659-207">若要在 Defender for Office 365 中创建防钓鱼策略，请观看此简短 [培训](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)视频，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="eb659-207">To create an anti-phishing policy in Defender for Office 365, watch [this short training video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>

1. <span data-ttu-id="eb659-208">转到 <https://protection.office.com>。</span><span class="sxs-lookup"><span data-stu-id="eb659-208">Go to <https://protection.office.com>.</span></span>

2. <span data-ttu-id="eb659-209">在安全&合规中心的左侧导航窗格中，在"威胁管理"**下，选择**"策略 **"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-209">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="eb659-210">在"**策略"** 页面上，选择 **"防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-210">On the **Policy** page, choose **Anti-phishing**.</span></span>

4. <span data-ttu-id="eb659-211">在"**防钓鱼"页面上**，选择 **"+ 创建"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-211">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="eb659-212">向导将启动，可分步定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="eb659-212">A wizard launches that steps you through defining your anti-phishing policy.</span></span>

5. <span data-ttu-id="eb659-213">指定策略的名称、说明和设置，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="eb659-213">Specify the name, description, and settings for your policy as recommended in the chart below.</span></span> <span data-ttu-id="eb659-214">有关详细信息，请参阅了解 [Microsoft Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md)选项中的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="eb659-214">For more information, see [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

6. <span data-ttu-id="eb659-215">查看设置后，选择"创建此策略" **或** " **保存**"（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="eb659-215">After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="eb659-216">设置或选项</span><span class="sxs-lookup"><span data-stu-id="eb659-216">Setting or option</span></span>|<span data-ttu-id="eb659-217">推荐设置</span><span class="sxs-lookup"><span data-stu-id="eb659-217">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="eb659-218">名称</span><span class="sxs-lookup"><span data-stu-id="eb659-218">Name</span></span>|<span data-ttu-id="eb659-219">域和最有价值的员工</span><span class="sxs-lookup"><span data-stu-id="eb659-219">Domain and most valuable staff</span></span>|
|<span data-ttu-id="eb659-220">说明</span><span class="sxs-lookup"><span data-stu-id="eb659-220">Description</span></span>|<span data-ttu-id="eb659-221">确保不会模拟最重要的员工和域。</span><span class="sxs-lookup"><span data-stu-id="eb659-221">Ensure most important staff and our domain are not being impersonated.</span></span>|
|<span data-ttu-id="eb659-222">添加要保护的用户</span><span class="sxs-lookup"><span data-stu-id="eb659-222">Add users to protect</span></span>|<span data-ttu-id="eb659-223">选择 **+ 添加条件，收件人是**。</span><span class="sxs-lookup"><span data-stu-id="eb659-223">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="eb659-224">键入用户名或输入业务所有者、合作伙伴或候选人、经理和其他重要员工成员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="eb659-224">Type user names or enter the email address of the business owners, partners, or candidate, managers, and other important staff members.</span></span> <span data-ttu-id="eb659-225">您最多可以添加 20 个要防止模拟的内部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="eb659-225">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>|
|<span data-ttu-id="eb659-226">添加要保护的域</span><span class="sxs-lookup"><span data-stu-id="eb659-226">Add domains to protect</span></span>|<span data-ttu-id="eb659-227">选择 **+ 添加条件，收件人域为**。</span><span class="sxs-lookup"><span data-stu-id="eb659-227">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="eb659-228">输入与 Microsoft 365 订阅关联的自定义域（如果已定义）。</span><span class="sxs-lookup"><span data-stu-id="eb659-228">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="eb659-229">可以输入多个域。</span><span class="sxs-lookup"><span data-stu-id="eb659-229">You can enter more than one domain.</span></span>|
|<span data-ttu-id="eb659-230">选择操作</span><span class="sxs-lookup"><span data-stu-id="eb659-230">Choose actions</span></span>|<span data-ttu-id="eb659-231">如果电子邮件是由模拟用户发送的：选择"将邮件重定向到其他电子邮件地址"，然后键入安全管理员的电子邮件地址;例如 *，Alice <span> <span> @contoso.com*。</span><span class="sxs-lookup"><span data-stu-id="eb659-231">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span> <br/> <span data-ttu-id="eb659-232">如果电子邮件是由模拟域发送的：请选择“隔离邮件”。</span><span class="sxs-lookup"><span data-stu-id="eb659-232">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>|
|<span data-ttu-id="eb659-233">邮箱智能</span><span class="sxs-lookup"><span data-stu-id="eb659-233">Mailbox intelligence</span></span>|<span data-ttu-id="eb659-234">默认情况下，创建新的反钓鱼策略时，将选择邮箱智能。</span><span class="sxs-lookup"><span data-stu-id="eb659-234">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="eb659-235">最好将此设置保留为“打开”。</span><span class="sxs-lookup"><span data-stu-id="eb659-235">Leave this setting **On** for best results.</span></span>|
|<span data-ttu-id="eb659-236">添加受信任的发件人和域</span><span class="sxs-lookup"><span data-stu-id="eb659-236">Add trusted senders and domains</span></span>|<span data-ttu-id="eb659-237">可以在此处添加您自己的域，或任何其他受信任域。</span><span class="sxs-lookup"><span data-stu-id="eb659-237">Here you can add your own domain, or any other trusted domains.</span></span>|
|<span data-ttu-id="eb659-238">应用于</span><span class="sxs-lookup"><span data-stu-id="eb659-238">Applied to</span></span>|<span data-ttu-id="eb659-239">选择“收件人域为”。</span><span class="sxs-lookup"><span data-stu-id="eb659-239">Select **The recipient domain is**.</span></span> <span data-ttu-id="eb659-240">在“以下任何项”中，选择“选择”。</span><span class="sxs-lookup"><span data-stu-id="eb659-240">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="eb659-241">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="eb659-241">Select **+ Add**.</span></span> <span data-ttu-id="eb659-242">选中域名称旁边的复选框，例如 *contoso。 <span> <span>com*，在列表中，**然后选择添加**。</span><span class="sxs-lookup"><span data-stu-id="eb659-242">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="eb659-243">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="eb659-243">Select **Done**.</span></span>|

<span data-ttu-id="eb659-244">有关详细信息，请参阅在 [Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md)中设置防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="eb659-244">For more information, see [Set up anti-phishing policies in Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a><span data-ttu-id="eb659-245">使用 Defender for Office 365 防止恶意附件、文件和链接</span><span class="sxs-lookup"><span data-stu-id="eb659-245">Protect against malicious attachments, files, and links with Defender for Office 365</span></span>

![指向 的横幅 https://aka.ms/aboutM365preview 。](../media/m365admincenterchanging.png)

<span data-ttu-id="eb659-247">首先，请确保在管理中心中，你已打开新的管理中心 <https://admin.microsoft.com> 预览。</span><span class="sxs-lookup"><span data-stu-id="eb659-247">First, make sure, in the admin center at <https://admin.microsoft.com> that you have the new admin center preview turned on.</span></span> <span data-ttu-id="eb659-248">打开文本"新管理中心"**旁边的切换。**</span><span class="sxs-lookup"><span data-stu-id="eb659-248">Turn on the toggle next to the text **The new admin center**.</span></span>

   ![打开新的管理中心预览。](../media/previewon.png)

<span data-ttu-id="eb659-250">如果尚未在租户中看到带卡的"安装"页面，请参阅安全与合规中心&这些步骤。</span><span class="sxs-lookup"><span data-stu-id="eb659-250">If you don't see the **Setup** page with cards in your tenant yet, see how to complete these steps in Security & Compliance Center.</span></span> <span data-ttu-id="eb659-251">请参阅 [在安全与合规&](#set-up-safe-attachments-in-the-security--compliance-center) 设置安全附件和在安全与合规& [设置安全链接](#set-up-safe-links-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="eb659-251">See [Set up Safe Attachments in the Security & Compliance Center](#set-up-safe-attachments-in-the-security--compliance-center) and [Set up Safe Links in the Security & Compliance Center](#set-up-safe-links-in-the-security--compliance-center).</span></span>

1. <span data-ttu-id="eb659-252">在左侧导航中，选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-252">In the left nav, choose **Setup**.</span></span>
2. <span data-ttu-id="eb659-253">在" **设置"** 页上， **选择"** 从高级威胁 **卡增强保护"上的"查看** "。</span><span class="sxs-lookup"><span data-stu-id="eb659-253">On the **Setup** page, choose **View** on the **Increase protection from advanced threats** card.</span></span>

   ![在"增强对高级威胁的保护"上选择"查看"。](../media/startatp.png)

3. <span data-ttu-id="eb659-255">On the **Increase protection from advanced threats** page， choose Get **started**.</span><span class="sxs-lookup"><span data-stu-id="eb659-255">On the **Increase protection from advanced threats** page, choose **Get started**.</span></span>
4. <span data-ttu-id="eb659-256">在打开的窗格中，选中电子邮件中的链接和附件、扫描 **SharePoint、OneDrive** 和 Teams 中的文件以及扫描 Office **桌面** 和 Office Online 应用中的链接下的复选框，在扫描恶意内容的项目 **下。**</span><span class="sxs-lookup"><span data-stu-id="eb659-256">On the pane that opens, select the check boxes next to **Links and attachments in email**, **Scan files in SharePoint, OneDrive, and Teams**, and **Scan links in Office desktop and Office Online apps** under **Scan items for malicious content**.</span></span>

   <span data-ttu-id="eb659-257">在 **"电子邮件中的链接和附件"** 下，键入"所有用户"或要扫描其电子邮件的特定用户。</span><span class="sxs-lookup"><span data-stu-id="eb659-257">Under **Links and attachments in email**, Type in All Users, or the specific users whose email you want scanned.</span></span>

   ![在"增强对高级威胁的保护"中选中所有复选框。](../media/setatp.png)

5. <span data-ttu-id="eb659-259">选择 **"创建策略** "以打开"安全附件和安全链接"。</span><span class="sxs-lookup"><span data-stu-id="eb659-259">Choose **Create policies** to turn on Safe Attachments and Safe Links.</span></span>

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a><span data-ttu-id="eb659-260">在安全与合规中心&安全附件</span><span class="sxs-lookup"><span data-stu-id="eb659-260">Set up Safe Attachments in the Security & Compliance Center</span></span>

<span data-ttu-id="eb659-261">人们定期发送、接收和共享附件，如文档、演示文稿、电子表格等。</span><span class="sxs-lookup"><span data-stu-id="eb659-261">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="eb659-262">通过查看电子邮件来判断附件是安全还是恶意并不总是那么容易。</span><span class="sxs-lookup"><span data-stu-id="eb659-262">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="eb659-263">Microsoft Defender for Office 365 包括安全附件保护，但此保护默认未打开。</span><span class="sxs-lookup"><span data-stu-id="eb659-263">Microsoft Defender for Office 365 includes Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="eb659-264">我们建议您创建一个新规则以开始使用此保护。</span><span class="sxs-lookup"><span data-stu-id="eb659-264">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="eb659-265">此保护扩展到 SharePoint、OneDrive 和 Microsoft Teams 中的文件。</span><span class="sxs-lookup"><span data-stu-id="eb659-265">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>

<span data-ttu-id="eb659-266">若要创建安全附件策略，请观看此 [简短视频](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="eb659-266">To create an Safe Attachment policy, either watch [this short video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>

1. <span data-ttu-id="eb659-267">转到 <https://protection.office.com> ，然后使用管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="eb659-267">Go to <https://protection.office.com> and sign in with your admin account.</span></span>

2. <span data-ttu-id="eb659-268">在安全&合规中心的左侧导航窗格中，在"威胁管理"**下，选择**"策略 **"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-268">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="eb659-269">在"策略"页面上，选择"**安全附件"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-269">On the Policy page, choose **Safe Attachments**.</span></span>

4. <span data-ttu-id="eb659-270">在"安全附件"页上，通过选中"打开 **适用于 SharePoint、OneDrive** 和 Microsoft Teams 的 ATP"复选框来广泛应用此保护。</span><span class="sxs-lookup"><span data-stu-id="eb659-270">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span>

5. <span data-ttu-id="eb659-271">选择 **+** 以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="eb659-271">Select **+** to create a new policy.</span></span>

6. <span data-ttu-id="eb659-272">应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="eb659-272">Apply the settings in the following table.</span></span>

7. <span data-ttu-id="eb659-273">查看设置后，选择"创建 **此策略"或** " **保存**"（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="eb659-273">After you review your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="eb659-274">设置或选项</span><span class="sxs-lookup"><span data-stu-id="eb659-274">Setting or option</span></span>|<span data-ttu-id="eb659-275">推荐设置</span><span class="sxs-lookup"><span data-stu-id="eb659-275">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="eb659-276">名称</span><span class="sxs-lookup"><span data-stu-id="eb659-276">Name</span></span>|<span data-ttu-id="eb659-277">使用检测到的恶意软件阻止当前和将来的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="eb659-277">Block current and future emails with detected malware.</span></span>|
|<span data-ttu-id="eb659-278">说明</span><span class="sxs-lookup"><span data-stu-id="eb659-278">Description</span></span>|<span data-ttu-id="eb659-279">使用检测到的恶意软件阻止当前和未来的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="eb659-279">Block current and future emails and attachments with detected malware.</span></span>|
|<span data-ttu-id="eb659-280">保存附件未知恶意软件响应</span><span class="sxs-lookup"><span data-stu-id="eb659-280">Save attachments unknown malware response</span></span>|<span data-ttu-id="eb659-281">选择 **"阻止 - 阻止当前和将来的电子邮件和带检测到的恶意软件的附件"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-281">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>|
|<span data-ttu-id="eb659-282">检测时重定向附件</span><span class="sxs-lookup"><span data-stu-id="eb659-282">Redirect attachment on detection</span></span>|<span data-ttu-id="eb659-283">启用重定向 (选中此框) </span><span class="sxs-lookup"><span data-stu-id="eb659-283">Enable redirection (select this box)</span></span> <br/> <span data-ttu-id="eb659-284">输入管理员帐户或邮箱设置以隔离。</span><span class="sxs-lookup"><span data-stu-id="eb659-284">Enter the admin account or a mailbox setup for quarantine.</span></span> <br/> <span data-ttu-id="eb659-285">如果恶意软件扫描附件出现时间过或出现错误，请应用 (选中此框) 。</span><span class="sxs-lookup"><span data-stu-id="eb659-285">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>|
|<span data-ttu-id="eb659-286">应用于</span><span class="sxs-lookup"><span data-stu-id="eb659-286">Applied to</span></span>|<span data-ttu-id="eb659-287">收件人域为 。</span><span class="sxs-lookup"><span data-stu-id="eb659-287">The recipient domain is .</span></span> <span data-ttu-id="eb659-288">.</span><span class="sxs-lookup"><span data-stu-id="eb659-288">.</span></span> <span data-ttu-id="eb659-289">.</span><span class="sxs-lookup"><span data-stu-id="eb659-289">.</span></span> <span data-ttu-id="eb659-290">选择你的域。</span><span class="sxs-lookup"><span data-stu-id="eb659-290">select your domain.</span></span>|

<span data-ttu-id="eb659-291">有关详细信息，请参阅在 [Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md)中设置防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="eb659-291">For more information, see [Set up anti-phishing policies in Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

### <a name="set-up-safe-links-in-the-security--compliance-center"></a><span data-ttu-id="eb659-292">在安全与合规中心&安全链接</span><span class="sxs-lookup"><span data-stu-id="eb659-292">Set up Safe Links in the Security & Compliance Center</span></span>

<span data-ttu-id="eb659-293">黑客有时会在电子邮件或其他文件中的链接中隐藏恶意网站。</span><span class="sxs-lookup"><span data-stu-id="eb659-293">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="eb659-294">安全链接是 Microsoft Defender for Office 365 的一部分，通过提供电子邮件和 Office 文档中 Web 地址 (URL) 的点击时间验证，可帮助保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="eb659-294">Safe Links, part of Microsoft Defender for Office 365, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="eb659-295">保护通过安全链接策略定义。</span><span class="sxs-lookup"><span data-stu-id="eb659-295">Protection is defined through Safe Links policies.</span></span>

<span data-ttu-id="eb659-296">我们建议您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="eb659-296">We recommend that you do the following:</span></span>

- <span data-ttu-id="eb659-297">修改默认策略以提高保护。</span><span class="sxs-lookup"><span data-stu-id="eb659-297">Modify the default policy to increase protection.</span></span>

- <span data-ttu-id="eb659-298">添加面向域中所有收件人的新策略。</span><span class="sxs-lookup"><span data-stu-id="eb659-298">Add a new policy targeted to all recipients in your domain.</span></span>

<span data-ttu-id="eb659-299">若要设置安全链接，请观看此 [简短培训视频](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="eb659-299">To set up Safe Links, watch [this short training video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>

1. <span data-ttu-id="eb659-300">转到 <https://protection.office.com> ，然后使用管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="eb659-300">Go to <https://protection.office.com> and sign in with your admin account.</span></span>

2. <span data-ttu-id="eb659-301">在安全&合规中心的左侧导航窗格中，在"威胁管理"**下，选择**"策略 **"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-301">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="eb659-302">在"策略"页面上，选择"**安全链接"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-302">On the Policy page, choose **Safe Links**.</span></span>

<span data-ttu-id="eb659-303">修改默认策略：</span><span class="sxs-lookup"><span data-stu-id="eb659-303">To modify the default policy:</span></span>

1. <span data-ttu-id="eb659-304">在"安全链接"页上，在"适用于整个组织 **的策略"下**，选择" **默认策略** "。</span><span class="sxs-lookup"><span data-stu-id="eb659-304">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span>

2. <span data-ttu-id="eb659-305">在 **"应用于电子邮件以外的内容的设置**"下，选择 **"Microsoft 365 企业应用版、Office for iOS 和 Android"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-305">Under **Settings that apply to content except email**, select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.</span></span>

3. <span data-ttu-id="eb659-306">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eb659-306">Click **Save**.</span></span>

<span data-ttu-id="eb659-307">要创建面向域中所有收件人的新策略，请执行：</span><span class="sxs-lookup"><span data-stu-id="eb659-307">To create a new policy targeted to all recipients in your domain:</span></span>

1. <span data-ttu-id="eb659-308">在"安全链接"页上，在"适用于整个组织的策略" **下**，单击 **+** 以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="eb659-308">On the Safe links page, under **Policies that apply to the entire organization**, click **+** to create a new policy.</span></span>

2. <span data-ttu-id="eb659-309">应用下表中列出的设置。</span><span class="sxs-lookup"><span data-stu-id="eb659-309">Apply the settings listed in the following table.</span></span>

3. <span data-ttu-id="eb659-310">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="eb659-310">Click **Save**.</span></span>

|<span data-ttu-id="eb659-311">设置或选项</span><span class="sxs-lookup"><span data-stu-id="eb659-311">Setting or option</span></span>|<span data-ttu-id="eb659-312">推荐设置</span><span class="sxs-lookup"><span data-stu-id="eb659-312">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="eb659-313">名称</span><span class="sxs-lookup"><span data-stu-id="eb659-313">Name</span></span>|<span data-ttu-id="eb659-314">域中所有收件人的安全链接策略</span><span class="sxs-lookup"><span data-stu-id="eb659-314">Safe links policy for all recipients in the domain</span></span>|
|<span data-ttu-id="eb659-315">选择邮件中未知潜在恶意 URL 的操作</span><span class="sxs-lookup"><span data-stu-id="eb659-315">Select the action for unknown potentially malicious URLs in messages</span></span>|<span data-ttu-id="eb659-316">选择打开 - 当用户单击链接时，URL 将被重写，并针对 **已知恶意链接列表进行检查**。</span><span class="sxs-lookup"><span data-stu-id="eb659-316">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>|
|<span data-ttu-id="eb659-317">使用安全附件扫描可下载内容</span><span class="sxs-lookup"><span data-stu-id="eb659-317">Use Safe Attachments to scan downloadable content</span></span>|<span data-ttu-id="eb659-318">选中此框。</span><span class="sxs-lookup"><span data-stu-id="eb659-318">Select this box.</span></span>|
|<span data-ttu-id="eb659-319">应用于</span><span class="sxs-lookup"><span data-stu-id="eb659-319">Applied to</span></span>|<span data-ttu-id="eb659-320">收件人域为 。</span><span class="sxs-lookup"><span data-stu-id="eb659-320">The recipient domain is .</span></span> <span data-ttu-id="eb659-321">.</span><span class="sxs-lookup"><span data-stu-id="eb659-321">.</span></span> <span data-ttu-id="eb659-322">.</span><span class="sxs-lookup"><span data-stu-id="eb659-322">.</span></span> <span data-ttu-id="eb659-323">选择你的域。</span><span class="sxs-lookup"><span data-stu-id="eb659-323">select your domain.</span></span>|

<span data-ttu-id="eb659-324">有关详细信息，请参阅适用于 [Office 365 的 Defender 中的安全链接](../security/office-365-security/safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="eb659-324">For more information, see [Safe Links in Defender for Office 365](../security/office-365-security/safe-links.md).</span></span>

## <a name="turn-on-the-unified-audit-log"></a><span data-ttu-id="eb659-325">打开统一审核日志</span><span class="sxs-lookup"><span data-stu-id="eb659-325">Turn on the Unified Audit Log</span></span>

<span data-ttu-id="eb659-326">在安全与审核日志中心启用 & 搜索后，可以在日志中保留管理员和其他用户活动并搜索它。</span><span class="sxs-lookup"><span data-stu-id="eb659-326">After you turn on the audit log search in the Security & Compliance Center, you can retain the admin and other user activity in the log and search it.</span></span>

<span data-ttu-id="eb659-327">必须在 Exchange Online 中分配审核日志角色，审核日志 Microsoft 365 订阅中打开或关闭搜索。</span><span class="sxs-lookup"><span data-stu-id="eb659-327">You must be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 subscription.</span></span> <span data-ttu-id="eb659-328">默认情况下，此角色分配给 Exchange 管理中心中"权限"页上的"合规性管理"和"组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="eb659-328">By default, this role is assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="eb659-329">默认情况下，Microsoft 365 中的全局管理员是此组的成员。</span><span class="sxs-lookup"><span data-stu-id="eb659-329">Global admins in Microsoft 365 are members of this group by default.</span></span>

1. <span data-ttu-id="eb659-330">若要打开"审核日志"，请转到 的管理中心 ，然后选择左侧导航中"管理中心" <https://admin.microsoft.com> 下的"安全性"。 </span><span class="sxs-lookup"><span data-stu-id="eb659-330">To turn on the audit log search, go to the admin center at <https://admin.microsoft.com> and then choose **Security** under **Admin centers** in the left nav.</span></span>
2. <span data-ttu-id="eb659-331">在 **"Microsoft 365 安全中心**"页面上，选择"更多资源"，然后在 **"Office 365** 安全与合规中心"&"打开"。 </span><span class="sxs-lookup"><span data-stu-id="eb659-331">On the **Microsoft 365 Security** page, choose **More resources**, and then **Open** on the **Office 365 Security & Compliance Center** card.</span></span>

    ![在安全与合规&选择"打开"。](../media/gotosecandcomp.png)
3. <span data-ttu-id="eb659-333">在"安全性和合规性"页上，选择"**搜索"，** 然后选择"**审核日志搜索"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-333">On the security and compliance page, choose **Search** and then **Audit log search**.</span></span>
4. <span data-ttu-id="eb659-334">在"审核日志搜索"页 **的顶部**，选择 **"启用审核"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-334">On the top of the **Audit log search** page, choose **Turn on auditing**.</span></span>

<span data-ttu-id="eb659-335">启用该功能后，你可以搜索文件、文件夹和许多活动。</span><span class="sxs-lookup"><span data-stu-id="eb659-335">After the feature is turned on, you can search for files, folders, and many activities.</span></span> <span data-ttu-id="eb659-336">有关详细信息，请参阅[搜索审核日志。](../compliance/search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="eb659-336">For more information, see [search the audit log](../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a><span data-ttu-id="eb659-337">调整 SharePoint 和 OneDrive 文件和文件夹的匿名共享设置</span><span class="sxs-lookup"><span data-stu-id="eb659-337">Tune-up anonymous sharing settings for SharePoint and OneDrive files and folders</span></span>

<span data-ttu-id="eb659-338"> (默认匿名链接过期时间更改为 14 天，将默认共享类型更改为"特定人员") 更改 OneDrive 和 SharePoint 的共享设置：</span><span class="sxs-lookup"><span data-stu-id="eb659-338">(change default anonymous link expiration to 14 days, change default sharing type to "Specific People") To change the sharing settings for OneDrive and SharePoint:</span></span>

1. <span data-ttu-id="eb659-339">转到管理中心 ，然后选择左侧导航中 <https://admin.microsoft.com> "管理 **中心**"下的 **"SharePoint"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-339">Go to the admin center at <https://admin.microsoft.com> and then choose **SharePoint** under **Admin centers** in the left nav.</span></span>
2. <span data-ttu-id="eb659-340">在 SharePoint 管理中心中，转到"**策略** \> **""共享"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-340">In the SharePoint admin center, go to **Policies** \> **Sharing**.</span></span>
3. <span data-ttu-id="eb659-341">在"共享"页面上的"文件和文件夹链接"下，选择"特定人员"，在"任何人"链接的高级设置下，选择"这些链接必须在此天数内过期"，然后键入 14 (或您希望将链接生存期限制为) 的另一天数。 </span><span class="sxs-lookup"><span data-stu-id="eb659-341">On the **Sharing** page, under **File and folder links**, select **Specific people**, and under **Advanced settings for "Anyone" links**, select **These links must expire within this many days**, and type in 14 (or another number of days you want to restrict the link lifetime to).</span></span>

   ![选择"特定人员"，将链接过期时间设置为 14 天。](../media/anyonelinks.png)

## <a name="activity-alerts"></a><span data-ttu-id="eb659-343">活动警报</span><span class="sxs-lookup"><span data-stu-id="eb659-343">Activity alerts</span></span>

<span data-ttu-id="eb659-344">可以使用活动警报跟踪管理员和用户活动，并检测组织中恶意软件和数据丢失防护事件。</span><span class="sxs-lookup"><span data-stu-id="eb659-344">You can use activity alerts to track admin and user activities and detect malware and data loss prevention incidents in your organization.</span></span> <span data-ttu-id="eb659-345">你的订阅包括一组默认策略，但你也可以创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="eb659-345">Your subscription includes a set of default policies, but you can also create custom ones.</span></span> <span data-ttu-id="eb659-346">有关详细信息，请参阅警报 [策略](../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="eb659-346">For more information, see [alert policies](../compliance/alert-policies.md).</span></span> <span data-ttu-id="eb659-347">例如，如果您将一个重要文件存储在 SharePoint 中，而您不希望任何人在外部共享，您可以创建一个通知，提醒您是否有人共享该文件。</span><span class="sxs-lookup"><span data-stu-id="eb659-347">For example, if you store an important file in SharePoint that you don't want anyone to share externally, you can create a notification that alerts you if someone does share it.</span></span>

<span data-ttu-id="eb659-348">下图显示了 Microsoft 365 中包含的默认策略。</span><span class="sxs-lookup"><span data-stu-id="eb659-348">The following figure shows the default policies that are included with Microsoft 365.</span></span>

![Microsoft 365 中包含的默认警报策略](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a><span data-ttu-id="eb659-350">禁用或管理日历共享</span><span class="sxs-lookup"><span data-stu-id="eb659-350">Disable or manage calendar sharing</span></span>

<span data-ttu-id="eb659-351">您可以阻止组织成员共享其日历，也可以管理他们可以共享的信息。</span><span class="sxs-lookup"><span data-stu-id="eb659-351">You can prevent people in your organization from sharing their calendars, or you can also manage what they can share.</span></span> <span data-ttu-id="eb659-352">例如，您可以将共享限制为仅忙/闲时间。</span><span class="sxs-lookup"><span data-stu-id="eb659-352">For example, you can restrict the sharing to free/busy times only.</span></span>

1. <span data-ttu-id="eb659-353">转到管理中心，然后选择 <https://admin.microsoft.com> "设置"" \> **组织设置"。**</span><span class="sxs-lookup"><span data-stu-id="eb659-353">Go to the admin center at <https://admin.microsoft.com> and choose **Settings** \> **Org Settings**.</span></span>
2. <span data-ttu-id="eb659-354">在"**服务**"页上，选择"日历"，然后选择组织成员是否可以与拥有 Office 365 或 Exchange 的外部人员或任何人共享其日历。</span><span class="sxs-lookup"><span data-stu-id="eb659-354">On the **Services** page, choose **Calendar**, and choose whether people in your organization can share their calendars with people outside who have Office 365 or Exchange, or with anyone.</span></span>

   <span data-ttu-id="eb659-355">如果选择"与任何人共享"选项，还可以决定仅共享忙/闲信息。</span><span class="sxs-lookup"><span data-stu-id="eb659-355">If you choose the share with anyone option, you can decide to also only share free/busy information.</span></span>

3. <span data-ttu-id="eb659-356">选择 **页面** 底部的"保存更改"。</span><span class="sxs-lookup"><span data-stu-id="eb659-356">Choose **Save changes** on the bottom of the page.</span></span>

   <span data-ttu-id="eb659-357">下图显示了不允许的日历共享。</span><span class="sxs-lookup"><span data-stu-id="eb659-357">The following figure shows calendar sharing not allowed.</span></span>

   ![显示不允许的外部日历共享的屏幕截图。](../media/nocalendarsharing.png)

   <span data-ttu-id="eb659-359">下图显示了通过仅包含忙/闲信息的电子邮件链接允许日历共享时的设置。</span><span class="sxs-lookup"><span data-stu-id="eb659-359">The following figure shows the settings when calendar sharing is allowed with an email link with only free/busy information.</span></span>

   ![与任何人共享日历忙/闲的屏幕截图。](../media/sharefreebusy.png)

<span data-ttu-id="eb659-361">如果允许用户共享其日历，请参阅以下有关如何从 Outlook[](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5)网页共享的说明。</span><span class="sxs-lookup"><span data-stu-id="eb659-361">If your users are allowed to share their calendars, see [these instructions](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for how to share from Outlook on the web.</span></span>
