---
title: 为 Microsoft 365 商业版增加威胁防护
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
search.appverid:
- BCS160
- MET150
description: 设置 Office 365 高级威胁防护，并保护敏感数据。
ms.openlocfilehash: fb63ca7e3cf38ecf31aab98e425b02e8b9983bf8
ms.sourcegitcommit: 4d5e4cb3fa3ab45ad15f103c720c77277b22fc23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "37636744"
---
# <a name="increase-threat-protection"></a><span data-ttu-id="736e6-103">增强威胁防护</span><span class="sxs-lookup"><span data-stu-id="736e6-103">Increase threat protection</span></span>

<span data-ttu-id="736e6-104">本文可帮助你提高 Microsoft 365 订阅中的保护，以防止出现网络钓鱼、恶意软件和其他威胁。</span><span class="sxs-lookup"><span data-stu-id="736e6-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="736e6-105">这些建议适用于具有更高安全性需求的组织，如法律办公室和卫生保健诊所。</span><span class="sxs-lookup"><span data-stu-id="736e6-105">These recommendations are appropriate for organizations with an increased need for security, like law offices, and health care clinics.</span></span>

<span data-ttu-id="736e6-106">在开始之前，请检查您的 Office 365 安全分数。</span><span class="sxs-lookup"><span data-stu-id="736e6-106">Before you begin, check your Office 365 Secure Score.</span></span> <span data-ttu-id="736e6-107">Office 365 安全分数根据您的常规活动和安全设置来分析 Office 365 组织的安全性，并给出分数。</span><span class="sxs-lookup"><span data-stu-id="736e6-107">Office 365 Secure Score analyzes your Office 365 organization's security based on your regular activities and security settings and assigns a score.</span></span> <span data-ttu-id="736e6-108">首先记录你的当前分数。</span><span class="sxs-lookup"><span data-stu-id="736e6-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="736e6-109">采取本文中建议的操作可提高您的成绩。</span><span class="sxs-lookup"><span data-stu-id="736e6-109">Taking the actions recommended in this article increases your score.</span></span> <span data-ttu-id="736e6-110">目标不能达到最大分数，但请注意保护您的环境不会对用户的工作效率造成负面影响的机会。</span><span class="sxs-lookup"><span data-stu-id="736e6-110">The goal is not to achieve the max score, but to be aware of opportunities to protect your environment that do not negatively affect productivity for your users.</span></span> 

<span data-ttu-id="736e6-111">有关详细信息，请参阅[Microsoft 安全分数](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score)。</span><span class="sxs-lookup"><span data-stu-id="736e6-111">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="736e6-112">提高针对邮件中的恶意软件的保护级别</span><span class="sxs-lookup"><span data-stu-id="736e6-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="736e6-113">你的 Office 365 或 Microsoft 365 环境包括针对恶意软件的防护，但你可以通过阻止常见恶意软件使用的文件类型的附件来提高此保护。</span><span class="sxs-lookup"><span data-stu-id="736e6-113">Your Office 365 or Microsoft 365 environment includes protection against malware, but you can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="736e6-114">若要提高电子邮件的恶意软件保护：</span><span class="sxs-lookup"><span data-stu-id="736e6-114">To increase malware protection in email:</span></span>
  
1. <span data-ttu-id="736e6-115">转到[https://protection.office.com](https://protection.office.com)并使用你的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="736e6-115">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account credentials.</span></span> 
    
2. <span data-ttu-id="736e6-116">在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略** \> **反恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-116">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>
    
3. <span data-ttu-id="736e6-117">双击默认策略以编辑此公司范围的策略。</span><span class="sxs-lookup"><span data-stu-id="736e6-117">Double-click the default policy to edit this company-wide policy.</span></span>
    
4. <span data-ttu-id="736e6-118">单击 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-118">Click **Settings**.</span></span>
    
5. <span data-ttu-id="736e6-119">在 "**常用附件类型筛选器**" 下，选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="736e6-119">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="736e6-120">被阻止的文件类型在此控件正下方的窗口中列出。</span><span class="sxs-lookup"><span data-stu-id="736e6-120">The file types that are blocked are listed in the window directly below this control.</span></span>  <span data-ttu-id="736e6-121">请确保添加以下 filetypes：</span><span class="sxs-lookup"><span data-stu-id="736e6-121">Make sure you add these filetypes:</span></span>
   - <span data-ttu-id="736e6-122">ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、.hlp、超线程、hta、inf、jse、mdz、作业、js、、.lnk、mda、mdb、mde、、msc、msi、msp、mst、vb、vbe、scr、pcd、shs、wsh、</span><span class="sxs-lookup"><span data-stu-id="736e6-122">ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif</span></span>  <br/> <span data-ttu-id="736e6-123">如果需要，您可以稍后添加或删除文件类型。</span><span class="sxs-lookup"><span data-stu-id="736e6-123">You can add or delete file types later, if needed.</span></span>
    
6. <span data-ttu-id="736e6-124">单击“保存”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="736e6-124">Click **Save.**</span></span>
    
<span data-ttu-id="736e6-125">有关详细信息，请参阅[反恶意软件保护](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="736e6-125">For more information, see [Anti-malware protection](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).</span></span>
  
## <a name="protect-against-ransomware"></a><span data-ttu-id="736e6-126">防御勒索软件</span><span class="sxs-lookup"><span data-stu-id="736e6-126">Protect against ransomware</span></span>

<span data-ttu-id="736e6-127">勒索软件通过加密文件或锁定计算机屏幕来限制对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="736e6-127">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="736e6-128">然后，它会通过在 exchange 中请求 "勒索" （通常为 "Bitcoin" 形式）（通常为 ""），在 exchange 中获取数据访问权限，从而从受害人 extort。</span><span class="sxs-lookup"><span data-stu-id="736e6-128">It then attempts to extort money from victims by asking for "ransom," usually in form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span> 
  
<span data-ttu-id="736e6-129">您可以通过创建一个或多个邮件流规则来阻止用于勒索软件的文件扩展名（在 "在[邮件中提高保护级别](#raise-the-level-of-protection-against-malware-in-mail)" 一步骤中添加的）或警告用户接收这些信息，从而防止勒索软件电子邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="736e6-129">You can protect against ransomware by creating one or more mail flow rules to block file extensions that are commonly used for ransomware (these were added in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step), or to warn users who receive these attachments in email.</span></span>

<span data-ttu-id="736e6-130">除了在上一步中阻止的文件，在打开包含宏的 Office 文件附件之前，创建规则来警告用户也是一种很好的做法。</span><span class="sxs-lookup"><span data-stu-id="736e6-130">In addition to the files that you blocked in the previous step, it is also good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="736e6-131">勒索软件可以隐藏在宏中，因此我们将警告用户不要从他们不知道的人打开这些文件。</span><span class="sxs-lookup"><span data-stu-id="736e6-131">Ransomware can be hidden inside macros, so we'll warn users to not open these files from people they do not know.</span></span>

<span data-ttu-id="736e6-132">若要创建邮件传输规则，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="736e6-132">To create a mail transport rule:</span></span>
  
1. <span data-ttu-id="736e6-133"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>转到 "管理中心"，然后选择 "**管理中心** \> **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-133">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Admin centers** \> **Exchange**.</span></span>
    
2. <span data-ttu-id="736e6-134">在 "**邮件流**" 类别中，单击 "**规则**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-134">In the **mail flow** category, click **rules**.</span></span>
    
3. <span data-ttu-id="736e6-135">单击**+**""，然后单击 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-135">Click **+**, and then click **Create a new rule**.</span></span>
    
4. <span data-ttu-id="736e6-136">单击对话框底部的 "**更多选项**" 以查看完整的选项集。</span><span class="sxs-lookup"><span data-stu-id="736e6-136">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span> 
    
5. <span data-ttu-id="736e6-137">对规则应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="736e6-137">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="736e6-138">将其余设置保留为默认值，除非您要对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="736e6-138">Leave the rest of the settings at the default, unless you want to change these.</span></span>
    
6. <span data-ttu-id="736e6-139">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="736e6-139">Click **Save**.</span></span>
    
|<span data-ttu-id="736e6-140">**设置**</span><span class="sxs-lookup"><span data-stu-id="736e6-140">**Setting**</span></span>|<span data-ttu-id="736e6-141">**在打开 Office 文件附件之前警告用户**</span><span class="sxs-lookup"><span data-stu-id="736e6-141">**Warn users before opening attachments of Office files**</span></span>||
|:-----|:-----|:-----|
|<span data-ttu-id="736e6-142">名称</span><span class="sxs-lookup"><span data-stu-id="736e6-142">Name</span></span>  <br/> |<span data-ttu-id="736e6-143">反勒索软件规则：警告用户</span><span class="sxs-lookup"><span data-stu-id="736e6-143">Anti-ransomware rule: warn users</span></span>  <br/>  |
|<span data-ttu-id="736e6-144">在以下情况应用此规则。</span><span class="sxs-lookup"><span data-stu-id="736e6-144">Apply this rule if .</span></span> <span data-ttu-id="736e6-145">.</span><span class="sxs-lookup"><span data-stu-id="736e6-145"></span></span> <span data-ttu-id="736e6-146">.</span><span class="sxs-lookup"><span data-stu-id="736e6-146"></span></span>  <br/> |<span data-ttu-id="736e6-147">任何附件。</span><span class="sxs-lookup"><span data-stu-id="736e6-147">Any attachment .</span></span> <span data-ttu-id="736e6-148">.</span><span class="sxs-lookup"><span data-stu-id="736e6-148"></span></span> <span data-ttu-id="736e6-149">.</span><span class="sxs-lookup"><span data-stu-id="736e6-149"></span></span> <span data-ttu-id="736e6-150">文件扩展名匹配。</span><span class="sxs-lookup"><span data-stu-id="736e6-150">file extension matches .</span></span> <span data-ttu-id="736e6-151">.</span><span class="sxs-lookup"><span data-stu-id="736e6-151"></span></span> <span data-ttu-id="736e6-152">.</span><span class="sxs-lookup"><span data-stu-id="736e6-152"></span></span>  <br/> |
|<span data-ttu-id="736e6-153">指定字词或短语</span><span class="sxs-lookup"><span data-stu-id="736e6-153">Specify words or phrases</span></span>  <br/> |<span data-ttu-id="736e6-154">添加以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="736e6-154">Add these file types:</span></span>  <br/> <span data-ttu-id="736e6-155">normal.dotm、.docm、xlsm、sltm、xlodbc.xla 加载、.xlam、xll、.pptm、potm、.ppam、ppsm、sldm</span><span class="sxs-lookup"><span data-stu-id="736e6-155">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span></span>  <br/>|
|<span data-ttu-id="736e6-156">执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="736e6-156">Do the following .</span></span> <span data-ttu-id="736e6-157">.</span><span class="sxs-lookup"><span data-stu-id="736e6-157"></span></span> <span data-ttu-id="736e6-158">.</span><span class="sxs-lookup"><span data-stu-id="736e6-158"></span></span>  <br/> |<span data-ttu-id="736e6-159">使用邮件通知收件人</span><span class="sxs-lookup"><span data-stu-id="736e6-159">Notify the recipient with a message</span></span>  <br/> |
|<span data-ttu-id="736e6-160">提供邮件文本</span><span class="sxs-lookup"><span data-stu-id="736e6-160">Provide message text</span></span>  <br/> |<span data-ttu-id="736e6-161">请勿从不知道的人打开这些类型的文件，因为它们可能包含恶意代码的宏。</span><span class="sxs-lookup"><span data-stu-id="736e6-161">Do not open these type of files from people you do not know because they might contain macros with malicious code.</span></span>  <br/> |
   
<span data-ttu-id="736e6-162">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="736e6-162">For more information, see:</span></span>
  
- [<span data-ttu-id="736e6-163">如何处理勒索软件</span><span class="sxs-lookup"><span data-stu-id="736e6-163">How to deal with ransomware</span></span>](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [<span data-ttu-id="736e6-164">还原你的 OneDrive</span><span class="sxs-lookup"><span data-stu-id="736e6-164">Restore your OneDrive</span></span>](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    


## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="736e6-165">停止电子邮件的自动转发</span><span class="sxs-lookup"><span data-stu-id="736e6-165">Stop auto-forwarding for email</span></span>

<span data-ttu-id="736e6-166">通过将邮箱设置为自动转发电子邮件，获取对用户邮箱的访问权限的黑客可以盗取您的邮件。</span><span class="sxs-lookup"><span data-stu-id="736e6-166">Hackers who gain access to a user's mailbox can steal your mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="736e6-167">即使没有用户的意识，也会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="736e6-167">This can happen even without the user's awareness.</span></span> <span data-ttu-id="736e6-168">您可以通过配置邮件流规则来防止这种情况发生。</span><span class="sxs-lookup"><span data-stu-id="736e6-168">You can prevent this from happening by configuring a mail flow rule.</span></span> 
  
<span data-ttu-id="736e6-169">若要创建邮件传输规则，请观看[此简短视频](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7)或按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="736e6-169">To create a mail transport rule, either watch [this short video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>
  
1. <span data-ttu-id="736e6-170">在 Microsoft 365 管理中心，单击 "**管理中心** \> **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-170">In the Microsoft 365 admin center, click **Admin centers** \> **Exchange**.</span></span>
    
2. <span data-ttu-id="736e6-171">在 "**邮件流**" 类别中，单击 "**规则**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-171">In the **mail flow** category, click **rules**.</span></span>
    
3. <span data-ttu-id="736e6-172">单击**+**""，然后单击 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-172">Click **+**, and then click **Create a new rule**.</span></span>
    
4. <span data-ttu-id="736e6-173">单击对话框底部的 "**更多选项**" 以查看完整的选项集。</span><span class="sxs-lookup"><span data-stu-id="736e6-173">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span> 
    
5. <span data-ttu-id="736e6-174">应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="736e6-174">Apply the settings in the following table.</span></span> <span data-ttu-id="736e6-175">将其余设置保留为默认值，除非您要对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="736e6-175">Leave the rest of the settings at the default, unless you want to change these.</span></span>
    
6. <span data-ttu-id="736e6-176">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="736e6-176">Click **Save**.</span></span>
    
|<span data-ttu-id="736e6-177">**设置**</span><span class="sxs-lookup"><span data-stu-id="736e6-177">**Setting**</span></span>|<span data-ttu-id="736e6-178">**在打开 Office 文件附件之前警告用户**</span><span class="sxs-lookup"><span data-stu-id="736e6-178">**Warn users before opening attachments of Office files**</span></span>|
|:-----|:-----|
|<span data-ttu-id="736e6-179">名称</span><span class="sxs-lookup"><span data-stu-id="736e6-179">Name</span></span>  <br/> |<span data-ttu-id="736e6-180">阻止电子邮件自动转发到外部域</span><span class="sxs-lookup"><span data-stu-id="736e6-180">Prevent auto forwarding of email to external domains</span></span>  <br/> |
|<span data-ttu-id="736e6-181">在以下情况应用此规则 .。。</span><span class="sxs-lookup"><span data-stu-id="736e6-181">Apply this rule if ...</span></span>  <br/> |<span data-ttu-id="736e6-182">发件人。</span><span class="sxs-lookup"><span data-stu-id="736e6-182">The sender .</span></span> <span data-ttu-id="736e6-183">.</span><span class="sxs-lookup"><span data-stu-id="736e6-183"></span></span> <span data-ttu-id="736e6-184">.</span><span class="sxs-lookup"><span data-stu-id="736e6-184"></span></span> <span data-ttu-id="736e6-185">为外部/内部。</span><span class="sxs-lookup"><span data-stu-id="736e6-185">is external/internal .</span></span> <span data-ttu-id="736e6-186">.</span><span class="sxs-lookup"><span data-stu-id="736e6-186"></span></span> <span data-ttu-id="736e6-187">.</span><span class="sxs-lookup"><span data-stu-id="736e6-187"></span></span> <span data-ttu-id="736e6-188">组织内部</span><span class="sxs-lookup"><span data-stu-id="736e6-188">Inside the organization</span></span>  <br/> |
|<span data-ttu-id="736e6-189">添加条件</span><span class="sxs-lookup"><span data-stu-id="736e6-189">Add condition</span></span>  <br/> |<span data-ttu-id="736e6-190">邮件属性。</span><span class="sxs-lookup"><span data-stu-id="736e6-190">The message properties .</span></span> <span data-ttu-id="736e6-191">.</span><span class="sxs-lookup"><span data-stu-id="736e6-191"></span></span> <span data-ttu-id="736e6-192">.</span><span class="sxs-lookup"><span data-stu-id="736e6-192"></span></span> <span data-ttu-id="736e6-193">包含邮件类型。</span><span class="sxs-lookup"><span data-stu-id="736e6-193">include the message type .</span></span> <span data-ttu-id="736e6-194">.</span><span class="sxs-lookup"><span data-stu-id="736e6-194"></span></span> <span data-ttu-id="736e6-195">.</span><span class="sxs-lookup"><span data-stu-id="736e6-195"></span></span> <span data-ttu-id="736e6-196">自动转发</span><span class="sxs-lookup"><span data-stu-id="736e6-196">Auto-forward</span></span>  <br/> |
|<span data-ttu-id="736e6-197">执行以下操作 .。。</span><span class="sxs-lookup"><span data-stu-id="736e6-197">Do the following ...</span></span>  <br/> |<span data-ttu-id="736e6-198">阻止邮件。</span><span class="sxs-lookup"><span data-stu-id="736e6-198">Block the message .</span></span> <span data-ttu-id="736e6-199">.</span><span class="sxs-lookup"><span data-stu-id="736e6-199"></span></span> <span data-ttu-id="736e6-200">.</span><span class="sxs-lookup"><span data-stu-id="736e6-200"></span></span> <span data-ttu-id="736e6-201">拒绝邮件并提供说明。</span><span class="sxs-lookup"><span data-stu-id="736e6-201">reject the message and include an explanation.</span></span>  <br/> |
|<span data-ttu-id="736e6-202">提供邮件文本</span><span class="sxs-lookup"><span data-stu-id="736e6-202">Provide message text</span></span>  <br/> |<span data-ttu-id="736e6-203">出于安全考虑，将阻止此组织外部的自动转发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="736e6-203">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="736e6-204">保护你的电子邮件免受网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="736e6-204">Protect your email from phishing attacks</span></span>

<span data-ttu-id="736e6-205">如果您为 Office 365 或 Microsoft 365 环境配置了一个或多个自定义域，则可以配置目标的反网络钓鱼保护。</span><span class="sxs-lookup"><span data-stu-id="736e6-205">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="736e6-206">ATP 反网络钓鱼保护是 Office 365 高级威胁防护的一部分，可帮助保护您的组织免受基于恶意模拟的网络钓鱼攻击和其他网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="736e6-206">ATP anti-phishing protection, part of Office 365 Advanced Threat Protection, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="736e6-207">如果尚未配置自定义域，则无需执行此操作。</span><span class="sxs-lookup"><span data-stu-id="736e6-207">If you haven't configured a custom domain, you do not need to do this.</span></span>
  
<span data-ttu-id="736e6-208">我们建议您通过创建策略来保护最重要的用户和您的自定义域，以此来开始保护。</span><span class="sxs-lookup"><span data-stu-id="736e6-208">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span> 

  
<span data-ttu-id="736e6-209">若要创建 ATP 反网络钓鱼策略，请观看[此简短的培训视频](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="736e6-209">To create an ATP anti-phishing policy, watch  [this short training video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>
  
1. <span data-ttu-id="736e6-210">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="736e6-210">Go to [https://protection.office.com](https://protection.office.com).</span></span> 
    
2. <span data-ttu-id="736e6-211">在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-211">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="736e6-212">在 "**策略**" 页上，选择 " **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-212">On the **Policy** page, choose **ATP anti-phishing**.</span></span>
    
4. <span data-ttu-id="736e6-213">在 "**反钓鱼网站**" 页上，选择 " **+ 创建**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-213">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="736e6-214">向导将启动，引导您完成定义您的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="736e6-214">A wizard launches that steps you through defining your anti-phishing policy.</span></span>
    
5. <span data-ttu-id="736e6-215">按照下表中的建议，指定策略的名称、说明和设置。</span><span class="sxs-lookup"><span data-stu-id="736e6-215">Specify the name, description, and settings for your policy as recommended in the chart below.</span></span> <span data-ttu-id="736e6-216">有关详细信息，请参阅[了解 ATP 反网络钓鱼策略选项](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options)。</span><span class="sxs-lookup"><span data-stu-id="736e6-216">See [Learn about ATP anti-phishing policy options](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options) for more details.</span></span> 
    
6. <span data-ttu-id="736e6-217">查看设置后，根据需要选择 "**创建此策略**" 或 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-217">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>
    

|<span data-ttu-id="736e6-218">**设置或选项**</span><span class="sxs-lookup"><span data-stu-id="736e6-218">**Setting or option**</span></span><br/>|<span data-ttu-id="736e6-219">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="736e6-219">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="736e6-220">名称</span><span class="sxs-lookup"><span data-stu-id="736e6-220">Name</span></span>  <br/> |<span data-ttu-id="736e6-221">域和最有价值的市场活动员工</span><span class="sxs-lookup"><span data-stu-id="736e6-221">Domain and most valuable campaign staff</span></span>  <br/> |
|<span data-ttu-id="736e6-222">说明</span><span class="sxs-lookup"><span data-stu-id="736e6-222">Description</span></span>  <br/> |<span data-ttu-id="736e6-223">确保不会模拟大多数重要的人员和我们的域。</span><span class="sxs-lookup"><span data-stu-id="736e6-223">Ensure most important staff and our domain are not being impersonated.</span></span>  <br/> |
|<span data-ttu-id="736e6-224">添加要保护的用户</span><span class="sxs-lookup"><span data-stu-id="736e6-224">Add users to protect</span></span>  <br/> |<span data-ttu-id="736e6-225">选择 **+ 添加条件，收件人为**。</span><span class="sxs-lookup"><span data-stu-id="736e6-225">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="736e6-226">键入用户名称或输入候选人、活动经理和其他重要教职员工成员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="736e6-226">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="736e6-227">您最大可以添加20个要从模拟中保护的内部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="736e6-227">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>  <br/> |
|<span data-ttu-id="736e6-228">添加要保护的域</span><span class="sxs-lookup"><span data-stu-id="736e6-228">Add domains to protect</span></span>  <br/> |<span data-ttu-id="736e6-229">选择 **"+ 添加条件，收件人域为"**。</span><span class="sxs-lookup"><span data-stu-id="736e6-229">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="736e6-230">输入与 Microsoft 365 订阅关联的自定义域（如果已定义一个）。</span><span class="sxs-lookup"><span data-stu-id="736e6-230">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="736e6-231">您可以输入一个以上的域。</span><span class="sxs-lookup"><span data-stu-id="736e6-231">You can enter more than one domain.</span></span>  <br/> |
|<span data-ttu-id="736e6-232">选择操作</span><span class="sxs-lookup"><span data-stu-id="736e6-232">Choose actions</span></span>  <br/> |<span data-ttu-id="736e6-233">如果模拟用户发送电子邮件：选择 "**将邮件重定向到另一个电子邮件地址**"，然后键入安全管理员的电子邮件地址;例如，*刘爱琳<span><span>@contoso .com*。</span><span class="sxs-lookup"><span data-stu-id="736e6-233">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span>          <span data-ttu-id="736e6-234">如果由模拟域发送电子邮件：选择 "**隔离邮件**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-234">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>  <br/> |
|<span data-ttu-id="736e6-235">邮箱智能</span><span class="sxs-lookup"><span data-stu-id="736e6-235">Mailbox intelligence</span></span>  <br/> |<span data-ttu-id="736e6-236">默认情况下，当您创建新的反网络钓鱼策略时，将选择邮箱智能。</span><span class="sxs-lookup"><span data-stu-id="736e6-236">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="736e6-237">将此设置保留为 **"开"** 以获得最佳效果。</span><span class="sxs-lookup"><span data-stu-id="736e6-237">Leave this setting **On** for best results.</span></span>  <br/> |
|<span data-ttu-id="736e6-238">添加受信任的发件人和域</span><span class="sxs-lookup"><span data-stu-id="736e6-238">Add trusted senders and domains</span></span>  <br/> |<span data-ttu-id="736e6-239">你可以在此处添加你自己的域或任何其他受信任域。</span><span class="sxs-lookup"><span data-stu-id="736e6-239">Here you can add your own domain, or any other trusted domains.</span></span>  <br/> |
|<span data-ttu-id="736e6-240">应用于</span><span class="sxs-lookup"><span data-stu-id="736e6-240">Applied to</span></span>  <br/> |<span data-ttu-id="736e6-241">选择 **"收件人域"**。</span><span class="sxs-lookup"><span data-stu-id="736e6-241">Select **The recipient domain is**.</span></span> <span data-ttu-id="736e6-242">在**以下任一情况**下，选择 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-242">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="736e6-243">选择 " **+ 添加**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-243">Select **+ Add**.</span></span> <span data-ttu-id="736e6-244">选中域名称旁边的复选框，例如 " *contoso"。<span>com <span>*，请在列表中，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-244">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="736e6-245">选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-245">Select **Done**.</span></span>  <br/> |
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a><span data-ttu-id="736e6-246">使用 ATP 安全附件防止恶意附件和文件</span><span class="sxs-lookup"><span data-stu-id="736e6-246">Protect against malicious attachments and files with ATP Safe Attachments</span></span>

<span data-ttu-id="736e6-247">用户定期发送、接收和共享附件，如文档、演示文稿、电子表格等。</span><span class="sxs-lookup"><span data-stu-id="736e6-247">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="736e6-248">只需查看一封电子邮件，就能判断附件是安全还是恶意的，并不总是容易。</span><span class="sxs-lookup"><span data-stu-id="736e6-248">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="736e6-249">Office 365 高级威胁防护包括 ATP 安全附件保护，但默认情况下不启用此保护。</span><span class="sxs-lookup"><span data-stu-id="736e6-249">Office 365 Advanced Threat Protection includes ATP Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="736e6-250">我们建议您创建一个新规则以开始使用此保护。</span><span class="sxs-lookup"><span data-stu-id="736e6-250">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="736e6-251">此保护功能扩展到 SharePoint、OneDrive 和 Microsoft 团队中的文件。</span><span class="sxs-lookup"><span data-stu-id="736e6-251">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>
  
<span data-ttu-id="736e6-252">若要创建 ATP 安全附件策略，请观看[此简短视频](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="736e6-252">To create an ATP safe attachment policy, either watch [this short video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>
  
1. <span data-ttu-id="736e6-253">转到[https://protection.office.com](https://protection.office.com)并使用管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="736e6-253">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account.</span></span> 
    
2. <span data-ttu-id="736e6-254">在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-254">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="736e6-255">在 "策略" 页上，选择 " **ATP 安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-255">On the Policy page, choose **ATP safe attachments**.</span></span>
    
4. <span data-ttu-id="736e6-256">在 "安全附件" 页面上，选中 "**启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP** " 复选框，以应用广泛的保护。</span><span class="sxs-lookup"><span data-stu-id="736e6-256">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span> 
    
5. <span data-ttu-id="736e6-257">选择**+** 以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="736e6-257">Select **+** to create a new policy.</span></span> 
    
6. <span data-ttu-id="736e6-258">应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="736e6-258">Apply the settings in the following table.</span></span> 
    
7. <span data-ttu-id="736e6-259">查看设置后，根据需要选择 "**创建此策略**" 或 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-259">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>
    

|<span data-ttu-id="736e6-260">**设置或选项**</span><span class="sxs-lookup"><span data-stu-id="736e6-260">**Setting or option**</span></span>|<span data-ttu-id="736e6-261">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="736e6-261">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="736e6-262">名称</span><span class="sxs-lookup"><span data-stu-id="736e6-262">Name</span></span>  <br/> |<span data-ttu-id="736e6-263">使用检测到的恶意软件阻止当前和将来的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="736e6-263">Block current and future emails with detected malware.</span></span>  <br/> |
|<span data-ttu-id="736e6-264">说明</span><span class="sxs-lookup"><span data-stu-id="736e6-264">Description</span></span>  <br/> |<span data-ttu-id="736e6-265">使用检测到的恶意软件阻止当前和将来的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="736e6-265">Block current and future emails and attachments with detected malware.</span></span>  <br/> |
|<span data-ttu-id="736e6-266">保存附件未知的恶意软件响应</span><span class="sxs-lookup"><span data-stu-id="736e6-266">Save attachments unknown malware response</span></span>  <br/> |<span data-ttu-id="736e6-267">Select **block-阻止当前和将来的包含检测到的恶意软件的电子邮件和附件**。</span><span class="sxs-lookup"><span data-stu-id="736e6-267">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>  <br/> |
|<span data-ttu-id="736e6-268">在检测时重定向附件</span><span class="sxs-lookup"><span data-stu-id="736e6-268">Redirect attachment on detection</span></span>  <br/> |<span data-ttu-id="736e6-269">启用重定向（选择此框）输入管理员帐户或邮箱设置进行隔离。</span><span class="sxs-lookup"><span data-stu-id="736e6-269">Enable redirection (select this box)          Enter the admin account or a mailbox setup for quarantine.</span></span>          <span data-ttu-id="736e6-270">如果恶意软件扫描附件超时或发生错误（选中此框），请应用上面的选择。</span><span class="sxs-lookup"><span data-stu-id="736e6-270">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>  <br/> |
|<span data-ttu-id="736e6-271">应用于</span><span class="sxs-lookup"><span data-stu-id="736e6-271">Applied to</span></span>  <br/> |<span data-ttu-id="736e6-272">收件人域为。</span><span class="sxs-lookup"><span data-stu-id="736e6-272">The recipient domain is .</span></span> <span data-ttu-id="736e6-273">.</span><span class="sxs-lookup"><span data-stu-id="736e6-273"></span></span> <span data-ttu-id="736e6-274">.</span><span class="sxs-lookup"><span data-stu-id="736e6-274"></span></span> <span data-ttu-id="736e6-275">选择您的域。</span><span class="sxs-lookup"><span data-stu-id="736e6-275">select your domain.</span></span>  <br/> |
   
<span data-ttu-id="736e6-276">有关详细信息，请参阅[设置 Office 365 ATP 反网络钓鱼策略](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="736e6-276">For more information, see [Set up Office 365 ATP anti-phishing policies](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).</span></span>
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a><span data-ttu-id="736e6-277">使用 ATP 安全链接防御网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="736e6-277">Protect against phishing attacks with ATP Safe Links</span></span>

<span data-ttu-id="736e6-278">黑客有时会在电子邮件或其他文件的链接中隐藏恶意网站。</span><span class="sxs-lookup"><span data-stu-id="736e6-278">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="736e6-279">Office 365 ATP 安全链接（ATP 安全链接）是 Office 365 高级威胁防护的一部分，可通过在电子邮件和 Office 文档中提供 web 地址（Url）的单击验证时间来帮助保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="736e6-279">Office 365 ATP Safe Links (ATP Safe Links), part of Office 365 Advanced Threat Protection, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="736e6-280">通过 ATP 安全链接策略定义保护。</span><span class="sxs-lookup"><span data-stu-id="736e6-280">Protection is defined through ATP Safe Links policies.</span></span>
  
<span data-ttu-id="736e6-281">我们建议您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="736e6-281">We recommend that you do the following:</span></span>
  
- <span data-ttu-id="736e6-282">修改默认策略以提高保护。</span><span class="sxs-lookup"><span data-stu-id="736e6-282">Modify the default policy to increase protection.</span></span>
    
- <span data-ttu-id="736e6-283">添加目标为域中所有收件人的新策略。</span><span class="sxs-lookup"><span data-stu-id="736e6-283">Add a new policy targeted to all recipients in your domain.</span></span>
    
<span data-ttu-id="736e6-284">若要设置 ATP 安全链接，请观看[此简短的培训视频](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="736e6-284">To set up ATP Safe Links, watch [this short training video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>
  
1. <span data-ttu-id="736e6-285">转到[https://protection.office.com](https://protection.office.com)并使用管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="736e6-285">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account.</span></span> 
    
2. <span data-ttu-id="736e6-286">在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-286">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="736e6-287">在 "策略" 页上，选择 " **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-287">On the Policy page, choose **ATP Safe Links**.</span></span>
    
<span data-ttu-id="736e6-288">若要修改默认策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="736e6-288">To modify the default policy:</span></span>
  
1. <span data-ttu-id="736e6-289">在 "安全链接" 页面上，在 "**适用于整个组织的策略**" 下，选择 "**默认**策略"。</span><span class="sxs-lookup"><span data-stu-id="736e6-289">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span> 
    
2. <span data-ttu-id="736e6-290">在 "**适用于除电子邮件以外的内容的设置**" 下，选择 " **office 365 专业增强版，office For iOS 和 Android**"。</span><span class="sxs-lookup"><span data-stu-id="736e6-290">Under **Settings that apply to content except email**, select **Office 365 ProPlus, Office for iOS and Android**.</span></span>
    
3. <span data-ttu-id="736e6-291">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="736e6-291">Click **Save**.</span></span> 
    
<span data-ttu-id="736e6-292">创建一个面向域中所有收件人的新策略：</span><span class="sxs-lookup"><span data-stu-id="736e6-292">To create a new policy targeted to all recipients in your domain:</span></span>
  
1. <span data-ttu-id="736e6-293">在 "安全链接" 页面上，在 "**适用于整个组织**的策略**+** " 下，单击 "创建新策略"。</span><span class="sxs-lookup"><span data-stu-id="736e6-293">On the Safe links page, under **Policies that apply to the entire organization**, click **+** to create a new policy.</span></span> 
    
2. <span data-ttu-id="736e6-294">应用下表中列出的设置。</span><span class="sxs-lookup"><span data-stu-id="736e6-294">Apply the settings listed in the following table.</span></span>
    
3. <span data-ttu-id="736e6-295">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="736e6-295">Click **Save**.</span></span> 

|<span data-ttu-id="736e6-296">**设置或选项**</span><span class="sxs-lookup"><span data-stu-id="736e6-296">**Setting or option**</span></span>|<span data-ttu-id="736e6-297">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="736e6-297">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="736e6-298">名称</span><span class="sxs-lookup"><span data-stu-id="736e6-298">Name</span></span>  <br/> |<span data-ttu-id="736e6-299">域中所有收件人的安全链接策略</span><span class="sxs-lookup"><span data-stu-id="736e6-299">Safe links policy for all recipients in the domain</span></span>  <br/> |
|<span data-ttu-id="736e6-300">选择邮件中未知的潜在恶意 Url 的操作</span><span class="sxs-lookup"><span data-stu-id="736e6-300">Select the action for unknown potentially malicious URLs in messages</span></span>  <br/> |<span data-ttu-id="736e6-301">**当用户单击链接时，将会重写并检查在已知恶意链接列表中的 "按 Url"，并对其进行检查**。</span><span class="sxs-lookup"><span data-stu-id="736e6-301">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>  <br/> |
|<span data-ttu-id="736e6-302">使用安全附件扫描可下载的内容</span><span class="sxs-lookup"><span data-stu-id="736e6-302">Use Safe Attachments to scan downloadable content</span></span>  <br/> |<span data-ttu-id="736e6-303">选中此框。</span><span class="sxs-lookup"><span data-stu-id="736e6-303">Select this box.</span></span>  <br/> |
|<span data-ttu-id="736e6-304">应用于</span><span class="sxs-lookup"><span data-stu-id="736e6-304">Applied to</span></span>  <br/> |<span data-ttu-id="736e6-305">收件人域为。</span><span class="sxs-lookup"><span data-stu-id="736e6-305">The recipient domain is .</span></span> <span data-ttu-id="736e6-306">.</span><span class="sxs-lookup"><span data-stu-id="736e6-306"></span></span> <span data-ttu-id="736e6-307">.</span><span class="sxs-lookup"><span data-stu-id="736e6-307"></span></span> <span data-ttu-id="736e6-308">选择您的域。</span><span class="sxs-lookup"><span data-stu-id="736e6-308">select your domain.</span></span>  <br/> |
   
<span data-ttu-id="736e6-309">有关详细信息，请参阅[Office 365 ATP 安全链接](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="736e6-309">For more information, see [Office 365 ATP safe links](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="736e6-310">转到 Intune 管理中心</span><span class="sxs-lookup"><span data-stu-id="736e6-310">Go to Intune admin center</span></span>

1. <span data-ttu-id="736e6-311">登录到[Azure 门户](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="736e6-311">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="736e6-312">在 "**搜索" 框**中选择 "**所有服务**"，然后键入*Intune* 。</span><span class="sxs-lookup"><span data-stu-id="736e6-312">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="736e6-313">显示结果后，单击 " **Microsoft Intune** " 旁边的 "开始"，使其成为收藏，以便稍后查找。</span><span class="sxs-lookup"><span data-stu-id="736e6-313">Once the results display, click the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="736e6-314">除了管理中心之外，你还可以使用 Intune 注册和管理你的组织的设备。</span><span class="sxs-lookup"><span data-stu-id="736e6-314">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="736e6-315">有关详细信息，请参阅[Windows 设备注册方法](https://docs.microsoft.com/intune/enrollment-method-capabs)和由[Intune 管理的设备的注册选项](https://docs.microsoft.com/intune/enrollment-options)的功能。</span><span class="sxs-lookup"><span data-stu-id="736e6-315">For more information, see [Capabilities by enrollment method for Windows devices](https://docs.microsoft.com/intune/enrollment-method-capabs) and [Enrollment options for devices managed by Intune](https://docs.microsoft.com/intune/enrollment-options).</span></span>
