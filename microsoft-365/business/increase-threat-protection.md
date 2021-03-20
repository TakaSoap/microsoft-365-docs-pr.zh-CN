---
title: 增强 Microsoft 365 商业版的威胁防护
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
description: 设置适用于 Office 365 的 Microsoft Defender，并保护敏感数据免受网络钓鱼、恶意软件和其他威胁的侵害。
ms.openlocfilehash: 0424fd56e30477f4e8d9e84b7ac78ba6255781fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913278"
---
# <a name="increase-threat-protection"></a><span data-ttu-id="07272-103">增强威胁防护</span><span class="sxs-lookup"><span data-stu-id="07272-103">Increase threat protection</span></span>

<span data-ttu-id="07272-104">本文可帮助你增强 Microsoft 365 订阅中的保护，以抵御网络钓鱼、恶意软件和其他威胁。</span><span class="sxs-lookup"><span data-stu-id="07272-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="07272-105">这些建议适用于对安全性需求不断增加的组织，如执法机构和医疗保健机构。</span><span class="sxs-lookup"><span data-stu-id="07272-105">These recommendations are appropriate for organizations with an increased need for security, like law offices and health care clinics.</span></span>

<span data-ttu-id="07272-106">开始之前，请检查 Office 365 安全分数。</span><span class="sxs-lookup"><span data-stu-id="07272-106">Before you begin, check your Office 365 Secure Score.</span></span> <span data-ttu-id="07272-107">Office 365 安全分数根据常规活动和安全设置分析组织的安全性，并分配分数。</span><span class="sxs-lookup"><span data-stu-id="07272-107">Office 365 Secure Score analyzes your organization's security based on your regular activities and security settings, and assigns a score.</span></span> <span data-ttu-id="07272-108">首先记下当前分数。</span><span class="sxs-lookup"><span data-stu-id="07272-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="07272-109">若要增加分数，请完成本文建议的操作。</span><span class="sxs-lookup"><span data-stu-id="07272-109">To increase your score, complete the actions recommended in this article.</span></span> <span data-ttu-id="07272-110">目标不是达到最高分，而是注意保护环境的机会，这些机会不会对用户的工作效率产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="07272-110">The goal isn't to achieve the maximum score, but to be aware of opportunities to protect your environment that don't negatively affect productivity for your users.</span></span>

<span data-ttu-id="07272-111">有关详细信息，请参阅 [Microsoft 安全分数](../security/mtp/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="07272-111">For more information, see [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="07272-112">提高邮件中恶意软件防护级别</span><span class="sxs-lookup"><span data-stu-id="07272-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="07272-113">Office 365 或 Microsoft 365 环境包括恶意软件防护。</span><span class="sxs-lookup"><span data-stu-id="07272-113">Your Office 365 or Microsoft 365 environment includes protection against malware.</span></span> <span data-ttu-id="07272-114">您可以通过阻止具有通常用于恶意软件的文件类型的附件来增强此保护。</span><span class="sxs-lookup"><span data-stu-id="07272-114">You can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="07272-115">增强电子邮件中的恶意软件保护：</span><span class="sxs-lookup"><span data-stu-id="07272-115">To increase malware protection in email:</span></span>

1. <span data-ttu-id="07272-116">转到 [https://protection.office.com](https://protection.office.com) ，然后使用管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="07272-116">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account credentials.</span></span>

2. <span data-ttu-id="07272-117">在安全 &amp; 与合规中心的左侧导航窗格中，在"**威胁** 管理"下，选择"**策略** \> **""反恶意软件"。**</span><span class="sxs-lookup"><span data-stu-id="07272-117">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>

3. <span data-ttu-id="07272-118">双击默认策略以编辑此公司范围内的策略。</span><span class="sxs-lookup"><span data-stu-id="07272-118">Double-click the default policy to edit this company-wide policy.</span></span>

4. <span data-ttu-id="07272-119">选择“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="07272-119">Select **Settings**.</span></span>

5. <span data-ttu-id="07272-120">在 **"常见附件类型筛选器"下，** 选择"**打开"。**</span><span class="sxs-lookup"><span data-stu-id="07272-120">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="07272-121">被阻止的文件类型将在此控件正下方的窗口中列出。</span><span class="sxs-lookup"><span data-stu-id="07272-121">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="07272-122">请确保添加以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="07272-122">Make sure that you add these file types:</span></span>

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   <span data-ttu-id="07272-123">如有必要，可以稍后添加或删除文件类型。</span><span class="sxs-lookup"><span data-stu-id="07272-123">If necessary, you can add or delete file types later.</span></span>

6. <span data-ttu-id="07272-124">选择 **"保存"。**</span><span class="sxs-lookup"><span data-stu-id="07272-124">Select **Save.**</span></span>

<span data-ttu-id="07272-125">有关详细信息，请参阅 EOP 中的反 [恶意软件保护](../security/office-365-security/anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="07272-125">For more information, see [Anti-malware protection in EOP](../security/office-365-security/anti-malware-protection.md).</span></span>

## <a name="protect-against-ransomware"></a><span data-ttu-id="07272-126">防范勒索软件</span><span class="sxs-lookup"><span data-stu-id="07272-126">Protect against ransomware</span></span>

<span data-ttu-id="07272-127">勒索软件通过加密文件或锁定计算机屏幕来限制对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="07272-127">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="07272-128">然后，它尝试通过请求"勒索"（通常采用加密货币（如"Itin"）来从犯罪中勒索资金，以交换对数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="07272-128">It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span>

<span data-ttu-id="07272-129">若要防范勒索软件，请创建一个或多个邮件流规则，以阻止通常用于勒索软件的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="07272-129">To protect against ransomware, create one or more mail flow rules to block file extensions that are commonly used for ransomware.</span></span> <span data-ttu-id="07272-130"> (在提高邮件步骤中的恶意软件防护级别中添加[](#raise-the-level-of-protection-against-malware-in-mail)了这些规则) 您还可以警告通过电子邮件接收这些附件的用户。</span><span class="sxs-lookup"><span data-stu-id="07272-130">(You added these rules in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step.) You can also warn users who receive these attachments in email.</span></span>

<span data-ttu-id="07272-131">除了在上一步中阻止的文件之外，最佳做法是创建一个规则，在打开包含宏的 Office 文件附件之前警告用户。</span><span class="sxs-lookup"><span data-stu-id="07272-131">In addition to the files that you blocked in the previous step, it's a good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="07272-132">勒索软件可以隐藏在宏内，因此警告用户不要从他们不知道的人打开这些文件。</span><span class="sxs-lookup"><span data-stu-id="07272-132">Ransomware can be hidden inside macros, so warn users not to open these files from people they don't know.</span></span>

<span data-ttu-id="07272-133">创建邮件传输规则：</span><span class="sxs-lookup"><span data-stu-id="07272-133">To create a mail transport rule:</span></span>

1. <span data-ttu-id="07272-134">转到 管理中心 ， <https://admin.microsoft.com> 然后选择 管理 **中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="07272-134">Go to the admin center at <https://admin.microsoft.com>, and choose **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="07272-135">在"**邮件流"** 类别中，选择"规则 **"。**</span><span class="sxs-lookup"><span data-stu-id="07272-135">In the **mail flow** category, select **rules**.</span></span>

3. <span data-ttu-id="07272-136">选择 **+** ，然后选择创建新 **规则**。</span><span class="sxs-lookup"><span data-stu-id="07272-136">Select **+**, and then select **Create a new rule**.</span></span>

4. <span data-ttu-id="07272-137">选择 **对话框** 底部的"更多选项"以查看完整的选项集。</span><span class="sxs-lookup"><span data-stu-id="07272-137">Select **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="07272-138">为规则应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="07272-138">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="07272-139">对其余设置使用默认值，除非您要更改它们。</span><span class="sxs-lookup"><span data-stu-id="07272-139">Use the default values for the rest of the settings, unless you want to change them.</span></span>

6. <span data-ttu-id="07272-140">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="07272-140">Select **Save**.</span></span>

|<span data-ttu-id="07272-141">Setting</span><span class="sxs-lookup"><span data-stu-id="07272-141">Setting</span></span>|<span data-ttu-id="07272-142">在打开 Office 文件的附件之前警告用户</span><span class="sxs-lookup"><span data-stu-id="07272-142">Warn users before opening attachments of Office files</span></span>||
|---|---|---|
|<span data-ttu-id="07272-143">名称</span><span class="sxs-lookup"><span data-stu-id="07272-143">Name</span></span>|<span data-ttu-id="07272-144">反勒索软件规则：警告用户</span><span class="sxs-lookup"><span data-stu-id="07272-144">Anti-ransomware rule: warn users</span></span>|
|<span data-ttu-id="07272-145">在 中应用此规则。</span><span class="sxs-lookup"><span data-stu-id="07272-145">Apply this rule if .</span></span> <span data-ttu-id="07272-146">.</span><span class="sxs-lookup"><span data-stu-id="07272-146">.</span></span> <span data-ttu-id="07272-147">.</span><span class="sxs-lookup"><span data-stu-id="07272-147">.</span></span>|<span data-ttu-id="07272-148">任何附件 。</span><span class="sxs-lookup"><span data-stu-id="07272-148">Any attachment .</span></span> <span data-ttu-id="07272-149">.</span><span class="sxs-lookup"><span data-stu-id="07272-149">.</span></span> <span data-ttu-id="07272-150">.</span><span class="sxs-lookup"><span data-stu-id="07272-150">.</span></span> <span data-ttu-id="07272-151">文件扩展名匹配 。</span><span class="sxs-lookup"><span data-stu-id="07272-151">file extension matches .</span></span> <span data-ttu-id="07272-152">.</span><span class="sxs-lookup"><span data-stu-id="07272-152">.</span></span> <span data-ttu-id="07272-153">.</span><span class="sxs-lookup"><span data-stu-id="07272-153">.</span></span>|
|<span data-ttu-id="07272-154">指定单词或短语</span><span class="sxs-lookup"><span data-stu-id="07272-154">Specify words or phrases</span></span>|<span data-ttu-id="07272-155">添加以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="07272-155">Add these file types:</span></span>  <br/> <span data-ttu-id="07272-156">dotm、docm、xlsm、sltm、xla、xlam、xll、pptm、potm、ppam、ppsm、sldm</span><span class="sxs-lookup"><span data-stu-id="07272-156">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span></span>|
|<span data-ttu-id="07272-157">执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="07272-157">Do the following .</span></span> <span data-ttu-id="07272-158">.</span><span class="sxs-lookup"><span data-stu-id="07272-158">.</span></span> <span data-ttu-id="07272-159">.</span><span class="sxs-lookup"><span data-stu-id="07272-159">.</span></span>|<span data-ttu-id="07272-160">使用邮件通知收件人</span><span class="sxs-lookup"><span data-stu-id="07272-160">Notify the recipient with a message</span></span>|
|<span data-ttu-id="07272-161">提供消息文本</span><span class="sxs-lookup"><span data-stu-id="07272-161">Provide message text</span></span>|<span data-ttu-id="07272-162">不要从您不知道的人打开这些类型的文件，因为它们可能包含包含恶意代码的宏。</span><span class="sxs-lookup"><span data-stu-id="07272-162">Do not open these types of files from people you do not know because they might contain macros with malicious code.</span></span>|

<span data-ttu-id="07272-163">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="07272-163">For more information, see:</span></span>

- [<span data-ttu-id="07272-164">勒索软件：如何降低风险</span><span class="sxs-lookup"><span data-stu-id="07272-164">Ransomware: how to reduce risk</span></span>](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [<span data-ttu-id="07272-165">还原 OneDrive</span><span class="sxs-lookup"><span data-stu-id="07272-165">Restore your OneDrive</span></span>](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="07272-166">停止电子邮件的自动转发</span><span class="sxs-lookup"><span data-stu-id="07272-166">Stop auto-forwarding for email</span></span>

<span data-ttu-id="07272-167">获取用户邮箱访问权限的黑客可以通过将邮箱设置为自动转发电子邮件来窃取邮件。</span><span class="sxs-lookup"><span data-stu-id="07272-167">Hackers who gain access to a user's mailbox can steal mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="07272-168">即使没有用户感知，也可能发生此情况。</span><span class="sxs-lookup"><span data-stu-id="07272-168">This can happen even without the user's awareness.</span></span> <span data-ttu-id="07272-169">为了防止发生这种情况，请配置邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="07272-169">To prevent this from happening, configure a mail flow rule.</span></span>

<span data-ttu-id="07272-170">若要创建邮件传输规则，请观看此 [简短视频](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) 或执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="07272-170">To create a mail transport rule, either watch [this short video](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>

1. <span data-ttu-id="07272-171">在 Microsoft 365 管理中心中，选择"**管理中心** \> **""Exchange"。**</span><span class="sxs-lookup"><span data-stu-id="07272-171">In the Microsoft 365 admin center, select **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="07272-172">在"**邮件流"** 类别中，选择"规则 **"。**</span><span class="sxs-lookup"><span data-stu-id="07272-172">In the **mail flow** category, select **rules**.</span></span>

3. <span data-ttu-id="07272-173">选择 **+** ，然后选择创建新 **规则**。</span><span class="sxs-lookup"><span data-stu-id="07272-173">Select **+**, and then select **Create a new rule**.</span></span>

4. <span data-ttu-id="07272-174">To see all the options， select **More options** at the bottom of the dialog box.</span><span class="sxs-lookup"><span data-stu-id="07272-174">To see all the options, select **More options** at the bottom of the dialog box.</span></span>

5. <span data-ttu-id="07272-175">应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="07272-175">Apply the settings in the following table.</span></span> <span data-ttu-id="07272-176">对其余设置使用默认值，除非您要更改它们。</span><span class="sxs-lookup"><span data-stu-id="07272-176">Use the default values for the rest of the settings, unless you want to change them.</span></span>

6. <span data-ttu-id="07272-177">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="07272-177">Select **Save**.</span></span>

|<span data-ttu-id="07272-178">Setting</span><span class="sxs-lookup"><span data-stu-id="07272-178">Setting</span></span>|<span data-ttu-id="07272-179">在打开 Office 文件的附件之前警告用户</span><span class="sxs-lookup"><span data-stu-id="07272-179">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="07272-180">名称</span><span class="sxs-lookup"><span data-stu-id="07272-180">Name</span></span>|<span data-ttu-id="07272-181">阻止电子邮件自动转发到外部域</span><span class="sxs-lookup"><span data-stu-id="07272-181">Prevent auto forwarding of email to external domains</span></span>|
|<span data-ttu-id="07272-182">如果 ...</span><span class="sxs-lookup"><span data-stu-id="07272-182">Apply this rule if ...</span></span>|<span data-ttu-id="07272-183">发件人 。</span><span class="sxs-lookup"><span data-stu-id="07272-183">The sender .</span></span> <span data-ttu-id="07272-184">.</span><span class="sxs-lookup"><span data-stu-id="07272-184">.</span></span> <span data-ttu-id="07272-185">.</span><span class="sxs-lookup"><span data-stu-id="07272-185">.</span></span> <span data-ttu-id="07272-186">是外部/内部 。</span><span class="sxs-lookup"><span data-stu-id="07272-186">is external/internal .</span></span> <span data-ttu-id="07272-187">.</span><span class="sxs-lookup"><span data-stu-id="07272-187">.</span></span> <span data-ttu-id="07272-188">.</span><span class="sxs-lookup"><span data-stu-id="07272-188">.</span></span> <span data-ttu-id="07272-189">组织内部</span><span class="sxs-lookup"><span data-stu-id="07272-189">Inside the organization</span></span>|
|<span data-ttu-id="07272-190">添加条件</span><span class="sxs-lookup"><span data-stu-id="07272-190">Add condition</span></span>|<span data-ttu-id="07272-191">邮件属性 。</span><span class="sxs-lookup"><span data-stu-id="07272-191">The message properties .</span></span> <span data-ttu-id="07272-192">.</span><span class="sxs-lookup"><span data-stu-id="07272-192">.</span></span> <span data-ttu-id="07272-193">.</span><span class="sxs-lookup"><span data-stu-id="07272-193">.</span></span> <span data-ttu-id="07272-194">包括邮件类型 。</span><span class="sxs-lookup"><span data-stu-id="07272-194">include the message type .</span></span> <span data-ttu-id="07272-195">.</span><span class="sxs-lookup"><span data-stu-id="07272-195">.</span></span> <span data-ttu-id="07272-196">.</span><span class="sxs-lookup"><span data-stu-id="07272-196">.</span></span> <span data-ttu-id="07272-197">自动转发</span><span class="sxs-lookup"><span data-stu-id="07272-197">Auto-forward</span></span>|
|<span data-ttu-id="07272-198">执行以下操作...</span><span class="sxs-lookup"><span data-stu-id="07272-198">Do the following ...</span></span>|<span data-ttu-id="07272-199">阻止邮件 。</span><span class="sxs-lookup"><span data-stu-id="07272-199">Block the message .</span></span> <span data-ttu-id="07272-200">.</span><span class="sxs-lookup"><span data-stu-id="07272-200">.</span></span> <span data-ttu-id="07272-201">.</span><span class="sxs-lookup"><span data-stu-id="07272-201">.</span></span> <span data-ttu-id="07272-202">拒绝邮件并给出说明。</span><span class="sxs-lookup"><span data-stu-id="07272-202">reject the message and include an explanation.</span></span>|
|<span data-ttu-id="07272-203">提供消息文本</span><span class="sxs-lookup"><span data-stu-id="07272-203">Provide message text</span></span>|<span data-ttu-id="07272-204">出于安全考虑，将阻止在此组织外自动转发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="07272-204">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>|


## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="07272-205">保护电子邮件免受网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="07272-205">Protect your email from phishing attacks</span></span>

<span data-ttu-id="07272-206">如果为 Office 365 或 Microsoft 365 环境配置了一个或多个自定义域，可以配置目标防钓鱼保护。</span><span class="sxs-lookup"><span data-stu-id="07272-206">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="07272-207">反网络钓鱼保护是 Microsoft Defender for Office 365 的一部分，可帮助保护你的组织免受基于恶意模拟的网络钓鱼攻击和其他网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="07272-207">Anti-phishing protection, part of Microsoft Defender for Office 365, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="07272-208">如果尚未配置自定义域，则无需这样做。</span><span class="sxs-lookup"><span data-stu-id="07272-208">If you haven't configured a custom domain, you don't need to do this.</span></span>

<span data-ttu-id="07272-209">我们建议你通过创建一个策略来保护最重要的用户和自定义域来开始使用此保护。</span><span class="sxs-lookup"><span data-stu-id="07272-209">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span>

<span data-ttu-id="07272-210">若要在 Microsoft Defender for Office 365 中创建防钓鱼策略，请观看此简短  [培训](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)视频，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="07272-210">To create an anti-phishing policy in Microsoft Defender for Office 365, watch  [this short training video](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>

1. <span data-ttu-id="07272-211">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="07272-211">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="07272-212">在安全 &amp; 与合规中心的左侧导航窗格中，在"威胁管理"下，选择"策略 **"。**</span><span class="sxs-lookup"><span data-stu-id="07272-212">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="07272-213">在"**策略"** 页面上，选择 **"防钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="07272-213">On the **Policy** page, choose **Anti-phishing**.</span></span>

4. <span data-ttu-id="07272-214">在"**防钓鱼"页面上**，选择 **"+ 创建"。**</span><span class="sxs-lookup"><span data-stu-id="07272-214">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="07272-215">向导将启动，可分步定义防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="07272-215">A wizard launches that steps you through defining your anti-phishing policy.</span></span>

5. <span data-ttu-id="07272-216">按照下表中的建议指定策略的名称、说明和设置。</span><span class="sxs-lookup"><span data-stu-id="07272-216">Specify the name, description, and settings for your policy as recommended in the following table.</span></span> <span data-ttu-id="07272-217">有关更多详细信息，请参阅 [了解 Microsoft Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md)选项中的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="07272-217">For more details, see [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

6. <span data-ttu-id="07272-218">查看设置后，选择"创建此策略" **或** " **保存**"（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="07272-218">After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="07272-219">设置或选项</span><span class="sxs-lookup"><span data-stu-id="07272-219">Setting or option</span></span>|<span data-ttu-id="07272-220">推荐设置</span><span class="sxs-lookup"><span data-stu-id="07272-220">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="07272-221">名称</span><span class="sxs-lookup"><span data-stu-id="07272-221">Name</span></span>|<span data-ttu-id="07272-222">域和最有价值的宣传活动人员</span><span class="sxs-lookup"><span data-stu-id="07272-222">Domain and most valuable campaign staff</span></span>|
|<span data-ttu-id="07272-223">说明</span><span class="sxs-lookup"><span data-stu-id="07272-223">Description</span></span>|<span data-ttu-id="07272-224">确保不会模拟最重要的员工和域。</span><span class="sxs-lookup"><span data-stu-id="07272-224">Ensure most important staff and our domain are not being impersonated.</span></span>|
|<span data-ttu-id="07272-225">添加要保护的用户</span><span class="sxs-lookup"><span data-stu-id="07272-225">Add users to protect</span></span>|<span data-ttu-id="07272-226">选择 **+ 添加条件，收件人是**。</span><span class="sxs-lookup"><span data-stu-id="07272-226">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="07272-227">键入用户名或输入候选人、市场活动经理和其他重要员工成员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="07272-227">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="07272-228">您最多可以添加 20 个要防止模拟的内部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="07272-228">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>|
|<span data-ttu-id="07272-229">添加要保护的域</span><span class="sxs-lookup"><span data-stu-id="07272-229">Add domains to protect</span></span>|<span data-ttu-id="07272-230">选择 **+ 添加条件，收件人域为**。</span><span class="sxs-lookup"><span data-stu-id="07272-230">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="07272-231">输入与 Microsoft 365 订阅关联的自定义域（如果已定义）。</span><span class="sxs-lookup"><span data-stu-id="07272-231">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="07272-232">可以输入多个域。</span><span class="sxs-lookup"><span data-stu-id="07272-232">You can enter more than one domain.</span></span>|
|<span data-ttu-id="07272-233">选择操作</span><span class="sxs-lookup"><span data-stu-id="07272-233">Choose actions</span></span>|<span data-ttu-id="07272-234">如果电子邮件是由模拟用户发送的：选择"将邮件重定向到其他电子邮件地址"，然后键入安全管理员的电子邮件地址;例如 *，Alice <span> <span> @contoso.com*。</span><span class="sxs-lookup"><span data-stu-id="07272-234">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span> <span data-ttu-id="07272-235">如果电子邮件是由模拟域发送的：请选择“隔离邮件”。</span><span class="sxs-lookup"><span data-stu-id="07272-235">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>|
|<span data-ttu-id="07272-236">邮箱智能</span><span class="sxs-lookup"><span data-stu-id="07272-236">Mailbox intelligence</span></span>|<span data-ttu-id="07272-237">默认情况下，创建新的反钓鱼策略时，将选择邮箱智能。</span><span class="sxs-lookup"><span data-stu-id="07272-237">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="07272-238">最好将此设置保留为“打开”。</span><span class="sxs-lookup"><span data-stu-id="07272-238">Leave this setting **On** for best results.</span></span>|
|<span data-ttu-id="07272-239">添加受信任的发件人和域</span><span class="sxs-lookup"><span data-stu-id="07272-239">Add trusted senders and domains</span></span>|<span data-ttu-id="07272-240">可以在此处添加您自己的域，或任何其他受信任域。</span><span class="sxs-lookup"><span data-stu-id="07272-240">Here you can add your own domain, or any other trusted domains.</span></span>|
|<span data-ttu-id="07272-241">应用于</span><span class="sxs-lookup"><span data-stu-id="07272-241">Applied to</span></span>|<span data-ttu-id="07272-242">选择“收件人域为”。</span><span class="sxs-lookup"><span data-stu-id="07272-242">Select **The recipient domain is**.</span></span> <span data-ttu-id="07272-243">在“以下任何项”中，选择“选择”。</span><span class="sxs-lookup"><span data-stu-id="07272-243">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="07272-244">选择“+ 添加”。</span><span class="sxs-lookup"><span data-stu-id="07272-244">Select **+ Add**.</span></span> <span data-ttu-id="07272-245">选中域名称旁边的复选框，例如 *contoso。 <span> <span>com*，在列表中，**然后选择添加**。</span><span class="sxs-lookup"><span data-stu-id="07272-245">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="07272-246">选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="07272-246">Select **Done**.</span></span>|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a><span data-ttu-id="07272-247">防范恶意附件和带安全附件的文件</span><span class="sxs-lookup"><span data-stu-id="07272-247">Protect against malicious attachments and files with Safe Attachments</span></span>

<span data-ttu-id="07272-248">人们定期发送、接收和共享附件，如文档、演示文稿、电子表格等。</span><span class="sxs-lookup"><span data-stu-id="07272-248">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="07272-249">通过查看电子邮件来判断附件是安全还是恶意并不总是那么容易。</span><span class="sxs-lookup"><span data-stu-id="07272-249">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="07272-250">Microsoft Defender for Office 365 包括安全附件保护，但此保护默认未打开。</span><span class="sxs-lookup"><span data-stu-id="07272-250">Microsoft Defender for Office 365 includes Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="07272-251">我们建议您创建一个新规则以开始使用此保护。</span><span class="sxs-lookup"><span data-stu-id="07272-251">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="07272-252">此保护扩展到 SharePoint、OneDrive 和 Microsoft Teams 中的文件。</span><span class="sxs-lookup"><span data-stu-id="07272-252">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>

<span data-ttu-id="07272-253">若要创建安全附件策略，请观看此 [简短视频](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="07272-253">To create an Safe Attachment policy, either watch [this short video](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>

1. <span data-ttu-id="07272-254">转到 [https://protection.office.com](https://protection.office.com) ，然后使用管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="07272-254">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span>

2. <span data-ttu-id="07272-255">在安全 &amp; 与合规中心的左侧导航窗格中，在"威胁管理"下，选择"策略 **"。**</span><span class="sxs-lookup"><span data-stu-id="07272-255">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="07272-256">在"策略"页面上，选择"**安全附件"。**</span><span class="sxs-lookup"><span data-stu-id="07272-256">On the Policy page, choose **Safe Attachments**.</span></span>

4. <span data-ttu-id="07272-257">在"安全附件"页上，通过选中"打开 **适用于 SharePoint、OneDrive** 和 Microsoft Teams 的 ATP"复选框来广泛应用此保护。</span><span class="sxs-lookup"><span data-stu-id="07272-257">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span>

5. <span data-ttu-id="07272-258">选择 **+** 以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="07272-258">Select **+** to create a new policy.</span></span>

6. <span data-ttu-id="07272-259">应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="07272-259">Apply the settings in the following table.</span></span>

7. <span data-ttu-id="07272-260">查看设置后，选择"创建 **此策略"或** " **保存**"（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="07272-260">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="07272-261">设置或选项</span><span class="sxs-lookup"><span data-stu-id="07272-261">Setting or option</span></span>|<span data-ttu-id="07272-262">推荐设置</span><span class="sxs-lookup"><span data-stu-id="07272-262">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="07272-263">名称</span><span class="sxs-lookup"><span data-stu-id="07272-263">Name</span></span>|<span data-ttu-id="07272-264">使用检测到的恶意软件阻止当前和将来的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="07272-264">Block current and future emails with detected malware.</span></span>|
|<span data-ttu-id="07272-265">说明</span><span class="sxs-lookup"><span data-stu-id="07272-265">Description</span></span>|<span data-ttu-id="07272-266">使用检测到的恶意软件阻止当前和未来的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="07272-266">Block current and future emails and attachments with detected malware.</span></span>|
|<span data-ttu-id="07272-267">保存附件未知恶意软件响应</span><span class="sxs-lookup"><span data-stu-id="07272-267">Save attachments unknown malware response</span></span>|<span data-ttu-id="07272-268">选择 **"阻止 - 阻止当前和将来的电子邮件和带检测到的恶意软件的附件"。**</span><span class="sxs-lookup"><span data-stu-id="07272-268">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>|
|<span data-ttu-id="07272-269">检测时重定向附件</span><span class="sxs-lookup"><span data-stu-id="07272-269">Redirect attachment on detection</span></span>|<span data-ttu-id="07272-270">启用重定向 (选中此框) 输入要隔离的管理员帐户或邮箱设置。</span><span class="sxs-lookup"><span data-stu-id="07272-270">Enable redirection (select this box)          Enter the admin account or a mailbox setup for quarantine.</span></span>          <span data-ttu-id="07272-271">如果恶意软件扫描附件出现时间过或出现错误，请应用 (选中此框) 。</span><span class="sxs-lookup"><span data-stu-id="07272-271">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>|
|<span data-ttu-id="07272-272">应用于</span><span class="sxs-lookup"><span data-stu-id="07272-272">Applied to</span></span>|<span data-ttu-id="07272-273">收件人域为 。</span><span class="sxs-lookup"><span data-stu-id="07272-273">The recipient domain is .</span></span> <span data-ttu-id="07272-274">.</span><span class="sxs-lookup"><span data-stu-id="07272-274">.</span></span> <span data-ttu-id="07272-275">.</span><span class="sxs-lookup"><span data-stu-id="07272-275">.</span></span> <span data-ttu-id="07272-276">选择你的域。</span><span class="sxs-lookup"><span data-stu-id="07272-276">select your domain.</span></span>|

<span data-ttu-id="07272-277">有关详细信息，请参阅在 [Microsoft Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md)中设置防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="07272-277">For more information, see [Set up anti-phishing policies in Microsoft Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

## <a name="protect-against-phishing-attacks-with-safe-links"></a><span data-ttu-id="07272-278">使用安全链接抵御网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="07272-278">Protect against phishing attacks with Safe Links</span></span>

<span data-ttu-id="07272-279">黑客有时会在电子邮件或其他文件中的链接中隐藏恶意网站。</span><span class="sxs-lookup"><span data-stu-id="07272-279">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="07272-280">安全链接是 Microsoft Defender for Office 365 的一部分，通过提供电子邮件和 Office 文档中 Web 地址 (URL) 的点击时间验证，可帮助保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="07272-280">Safe Links, part of Microsoft Defender for Office 365, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="07272-281">保护通过安全链接策略定义。</span><span class="sxs-lookup"><span data-stu-id="07272-281">Protection is defined through Safe Links policies.</span></span>

<span data-ttu-id="07272-282">我们建议您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="07272-282">We recommend that you do the following:</span></span>

- <span data-ttu-id="07272-283">修改默认策略以提高保护。</span><span class="sxs-lookup"><span data-stu-id="07272-283">Modify the default policy to increase protection.</span></span>

- <span data-ttu-id="07272-284">添加面向域中所有收件人的新策略。</span><span class="sxs-lookup"><span data-stu-id="07272-284">Add a new policy targeted to all recipients in your domain.</span></span>

<span data-ttu-id="07272-285">若要设置安全链接，请观看此 [简短培训视频](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="07272-285">To set up Safe Links, watch [this short training video](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>

1. <span data-ttu-id="07272-286">转到 [https://protection.office.com](https://protection.office.com) ，然后使用管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="07272-286">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span>

2. <span data-ttu-id="07272-287">在安全 &amp; 与合规中心的左侧导航窗格中，在"威胁管理"下，选择"策略 **"。**</span><span class="sxs-lookup"><span data-stu-id="07272-287">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="07272-288">在"策略"页面上，选择"**安全链接"。**</span><span class="sxs-lookup"><span data-stu-id="07272-288">On the Policy page, choose **Safe Links**.</span></span>

<span data-ttu-id="07272-289">修改默认策略：</span><span class="sxs-lookup"><span data-stu-id="07272-289">To modify the default policy:</span></span>

1. <span data-ttu-id="07272-290">在"安全链接"页上，在"适用于整个组织 **的策略"下**，选择" **默认策略** "。</span><span class="sxs-lookup"><span data-stu-id="07272-290">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span>

2. <span data-ttu-id="07272-291">在 **"应用于电子邮件以外的内容的设置**"下，选择 **"Microsoft 365 企业应用版、Office for iOS 和 Android"。**</span><span class="sxs-lookup"><span data-stu-id="07272-291">Under **Settings that apply to content except email**, select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.</span></span>

3. <span data-ttu-id="07272-292">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="07272-292">Select **Save**.</span></span>

<span data-ttu-id="07272-293">要创建面向域中所有收件人的新策略，请执行：</span><span class="sxs-lookup"><span data-stu-id="07272-293">To create a new policy targeted to all recipients in your domain:</span></span>

1. <span data-ttu-id="07272-294">在"安全链接"页面上，在"适用于整个组织的策略" **下**，选择 **+** 创建新策略。</span><span class="sxs-lookup"><span data-stu-id="07272-294">On the Safe links page, under **Policies that apply to the entire organization**, select **+** to create a new policy.</span></span>

2. <span data-ttu-id="07272-295">应用下表中列出的设置。</span><span class="sxs-lookup"><span data-stu-id="07272-295">Apply the settings listed in the following table.</span></span>

3. <span data-ttu-id="07272-296">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="07272-296">Select **Save**.</span></span>

|<span data-ttu-id="07272-297">设置或选项</span><span class="sxs-lookup"><span data-stu-id="07272-297">Setting or option</span></span>|<span data-ttu-id="07272-298">推荐设置</span><span class="sxs-lookup"><span data-stu-id="07272-298">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="07272-299">名称</span><span class="sxs-lookup"><span data-stu-id="07272-299">Name</span></span>|<span data-ttu-id="07272-300">域中所有收件人的安全链接策略</span><span class="sxs-lookup"><span data-stu-id="07272-300">Safe links policy for all recipients in the domain</span></span>|
|<span data-ttu-id="07272-301">选择邮件中未知潜在恶意 URL 的操作</span><span class="sxs-lookup"><span data-stu-id="07272-301">Select the action for unknown potentially malicious URLs in messages</span></span>|<span data-ttu-id="07272-302">选择打开 - 当用户单击链接时，URL 将被重写，并针对 **已知恶意链接列表进行检查**。</span><span class="sxs-lookup"><span data-stu-id="07272-302">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>|
|<span data-ttu-id="07272-303">使用安全附件扫描可下载内容</span><span class="sxs-lookup"><span data-stu-id="07272-303">Use Safe Attachments to scan downloadable content</span></span>|<span data-ttu-id="07272-304">选中此框。</span><span class="sxs-lookup"><span data-stu-id="07272-304">Select this box.</span></span>|
|<span data-ttu-id="07272-305">应用于</span><span class="sxs-lookup"><span data-stu-id="07272-305">Applied to</span></span>|<span data-ttu-id="07272-306">收件人域为 。</span><span class="sxs-lookup"><span data-stu-id="07272-306">The recipient domain is .</span></span> <span data-ttu-id="07272-307">.</span><span class="sxs-lookup"><span data-stu-id="07272-307">.</span></span> <span data-ttu-id="07272-308">.</span><span class="sxs-lookup"><span data-stu-id="07272-308">.</span></span> <span data-ttu-id="07272-309">选择你的域。</span><span class="sxs-lookup"><span data-stu-id="07272-309">select your domain.</span></span>|

<span data-ttu-id="07272-310">有关详细信息，请参阅安全 [链接](../security/office-365-security/atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="07272-310">For more information, see [Safe Links](../security/office-365-security/atp-safe-links.md).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="07272-311">转到 Intune 管理中心</span><span class="sxs-lookup"><span data-stu-id="07272-311">Go to Intune admin center</span></span>

1. <span data-ttu-id="07272-312">登录到 [Azure 门户](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="07272-312">Sign in to [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="07272-313">选择 **"所有服务**"，在 *"搜索框"\*\*\*中键入*\* Intune。</span><span class="sxs-lookup"><span data-stu-id="07272-313">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="07272-314">显示结果后，选择 **Microsoft Intune** 旁边的"开始"屏幕，使其成为收藏项，并且易于稍后查找。</span><span class="sxs-lookup"><span data-stu-id="07272-314">Once the results appear, select the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="07272-315">除了管理中心外，您还可以使用 Intune 注册和管理组织的设备。</span><span class="sxs-lookup"><span data-stu-id="07272-315">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="07272-316">有关详细信息，请参阅 [Windows](/intune/enrollment/enrollment-method-capab) 设备的注册方法的功能和 [Intune](/intune/enrollment-options)管理的设备的注册选项。</span><span class="sxs-lookup"><span data-stu-id="07272-316">For more information, see [Capabilities by enrollment method for Windows devices](/intune/enrollment/enrollment-method-capab) and [Enrollment options for devices managed by Intune](/intune/enrollment-options).</span></span>