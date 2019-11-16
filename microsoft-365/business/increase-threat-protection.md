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
ms.openlocfilehash: bca5400a04ca2986496c4a704289474887eb834b
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676000"
---
# <a name="increase-threat-protection"></a><span data-ttu-id="434f5-103">增强威胁防护</span><span class="sxs-lookup"><span data-stu-id="434f5-103">Increase threat protection</span></span>

<span data-ttu-id="434f5-104">本文可帮助你提高 Microsoft 365 订阅中的保护，以防止出现网络钓鱼、恶意软件和其他威胁。</span><span class="sxs-lookup"><span data-stu-id="434f5-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="434f5-105">这些建议适用于具有更高安全性需求的组织，如法律办公室和卫生保健诊所。</span><span class="sxs-lookup"><span data-stu-id="434f5-105">These recommendations are appropriate for organizations with an increased need for security, like law offices and health care clinics.</span></span>

<span data-ttu-id="434f5-106">在开始之前，请检查您的 Office 365 安全分数。</span><span class="sxs-lookup"><span data-stu-id="434f5-106">Before you begin, check your Office 365 Secure Score.</span></span> <span data-ttu-id="434f5-107">Office 365 安全分数根据您的常规活动和安全设置来分析 Office 365 组织的安全性，并分配分数。</span><span class="sxs-lookup"><span data-stu-id="434f5-107">Office 365 Secure Score analyzes your Office 365 organization's security based on your regular activities and security settings, and assigns a score.</span></span> <span data-ttu-id="434f5-108">首先记录你的当前分数。</span><span class="sxs-lookup"><span data-stu-id="434f5-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="434f5-109">若要增加成绩，请完成本文中建议的操作。</span><span class="sxs-lookup"><span data-stu-id="434f5-109">To increase your score, complete the actions recommended in this article.</span></span> <span data-ttu-id="434f5-110">目标不能达到最大分数，但请注意保护您的环境不会对用户的工作效率造成负面影响的机会。</span><span class="sxs-lookup"><span data-stu-id="434f5-110">The goal isn't to achieve the maximum score, but to be aware of opportunities to protect your environment that don't negatively affect productivity for your users.</span></span> 

<span data-ttu-id="434f5-111">有关详细信息，请参阅[Microsoft 安全分数](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)。</span><span class="sxs-lookup"><span data-stu-id="434f5-111">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="434f5-112">提高针对邮件中的恶意软件的保护级别</span><span class="sxs-lookup"><span data-stu-id="434f5-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="434f5-113">您的 Office 365 或 Microsoft 365 环境包括针对恶意软件的防护。</span><span class="sxs-lookup"><span data-stu-id="434f5-113">Your Office 365 or Microsoft 365 environment includes protection against malware.</span></span> <span data-ttu-id="434f5-114">您可以通过阻止经常用于恶意软件的文件类型来阻止附件，从而提高此保护。</span><span class="sxs-lookup"><span data-stu-id="434f5-114">You can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="434f5-115">若要提高电子邮件的恶意软件保护：</span><span class="sxs-lookup"><span data-stu-id="434f5-115">To increase malware protection in email:</span></span>
  
1. <span data-ttu-id="434f5-116">转到[https://protection.office.com](https://protection.office.com)并使用你的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="434f5-116">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account credentials.</span></span> 
    
2. <span data-ttu-id="434f5-117">在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略** \> **反恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-117">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>
    
3. <span data-ttu-id="434f5-118">双击默认策略以编辑此公司范围的策略。</span><span class="sxs-lookup"><span data-stu-id="434f5-118">Double-click the default policy to edit this company-wide policy.</span></span>
    
4. <span data-ttu-id="434f5-119">选择“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="434f5-119">Select **Settings**.</span></span>
    
5. <span data-ttu-id="434f5-120">在 "**常用附件类型筛选器**" 下，选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="434f5-120">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="434f5-121">被阻止的文件类型在此控件正下方的窗口中列出。</span><span class="sxs-lookup"><span data-stu-id="434f5-121">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="434f5-122">请确保添加以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="434f5-122">Make sure that you add these file types:</span></span>
   - <span data-ttu-id="434f5-123">ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、.hlp、超线程、hta、inf、jse、mdz、作业、js、、.lnk、mda、mdb、mde、、msc、msi、msp、mst、vb、vbe、scr、pcd、shs、wsh、</span><span class="sxs-lookup"><span data-stu-id="434f5-123">ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif</span></span>  <br/> 
   
   <span data-ttu-id="434f5-124">如有必要，您可以稍后添加或删除文件类型。</span><span class="sxs-lookup"><span data-stu-id="434f5-124">If necessary, you can add or delete file types later.</span></span>
    
6. <span data-ttu-id="434f5-125">选择 "**保存"。**</span><span class="sxs-lookup"><span data-stu-id="434f5-125">Select **Save.**</span></span>
    
<span data-ttu-id="434f5-126">有关详细信息，请参阅[反恶意软件保护](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="434f5-126">For more information, see [Anti-malware protection](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).</span></span>
  
## <a name="protect-against-ransomware"></a><span data-ttu-id="434f5-127">防御勒索软件</span><span class="sxs-lookup"><span data-stu-id="434f5-127">Protect against ransomware</span></span>

<span data-ttu-id="434f5-128">勒索软件通过加密文件或锁定计算机屏幕来限制对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="434f5-128">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="434f5-129">然后，它会通过在 exchange 中请求 "勒索" （通常为 "cryptocurrencies" 的形式为 "Bitcoin"），从受害者处 extort 钱，以供 exchange 访问数据。</span><span class="sxs-lookup"><span data-stu-id="434f5-129">It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span> 
  
<span data-ttu-id="434f5-130">若要针对勒索软件进行保护，请创建一个或多个邮件流规则，以阻止用于勒索软件的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="434f5-130">To protect against ransomware, create one or more mail flow rules to block file extensions that are commonly used for ransomware.</span></span> <span data-ttu-id="434f5-131">（在 "邮件" 步骤中添加了这些规则以[防止恶意软件的保护级别](#raise-the-level-of-protection-against-malware-in-mail)。）您还可以在电子邮件中警告收到这些附件的用户。</span><span class="sxs-lookup"><span data-stu-id="434f5-131">(You added these rules in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step.) You can also warn users who receive these attachments in email.</span></span>

<span data-ttu-id="434f5-132">除了在上一步中阻止的文件，在打开包含宏的 Office 文件附件之前，最好先创建一个规则来警告用户。</span><span class="sxs-lookup"><span data-stu-id="434f5-132">In addition to the files that you blocked in the previous step, it's a good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="434f5-133">勒索软件可以隐藏在宏中，因此警告用户不要从他们不知道的人那里打开这些文件。</span><span class="sxs-lookup"><span data-stu-id="434f5-133">Ransomware can be hidden inside macros, so warn users not to open these files from people they don't know.</span></span>

<span data-ttu-id="434f5-134">若要创建邮件传输规则，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="434f5-134">To create a mail transport rule:</span></span>
  
1. <span data-ttu-id="434f5-135"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>转到 "管理中心"，然后选择 "**管理中心** \> " " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-135">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>, and choose **Admin centers** \> **Exchange**.</span></span>
    
2. <span data-ttu-id="434f5-136">在 "**邮件流**" 类别中，选择 "**规则**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-136">In the **mail flow** category, select **rules**.</span></span>
    
3. <span data-ttu-id="434f5-137">选择**+**""，然后选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-137">Select **+**, and then select **Create a new rule**.</span></span>
    
4. <span data-ttu-id="434f5-138">选择对话框底部的 "**更多选项**" 可查看完整的选项集。</span><span class="sxs-lookup"><span data-stu-id="434f5-138">Select **More options** at the bottom of the dialog box to see the full set of options.</span></span> 
    
5. <span data-ttu-id="434f5-139">对规则应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="434f5-139">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="434f5-140">对其余设置使用默认值，除非您要对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="434f5-140">Use the default values for the rest of the settings, unless you want to change them.</span></span>
    
6. <span data-ttu-id="434f5-141">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="434f5-141">Select **Save**.</span></span>
    
|<span data-ttu-id="434f5-142">**设置**</span><span class="sxs-lookup"><span data-stu-id="434f5-142">**Setting**</span></span>|<span data-ttu-id="434f5-143">**在打开 Office 文件附件之前警告用户**</span><span class="sxs-lookup"><span data-stu-id="434f5-143">**Warn users before opening attachments of Office files**</span></span>||
|:-----|:-----|:-----|
|<span data-ttu-id="434f5-144">名称</span><span class="sxs-lookup"><span data-stu-id="434f5-144">Name</span></span>  <br/> |<span data-ttu-id="434f5-145">反勒索软件规则：警告用户</span><span class="sxs-lookup"><span data-stu-id="434f5-145">Anti-ransomware rule: warn users</span></span>  <br/>  |
|<span data-ttu-id="434f5-146">在以下情况应用此规则。</span><span class="sxs-lookup"><span data-stu-id="434f5-146">Apply this rule if .</span></span> <span data-ttu-id="434f5-147">.</span><span class="sxs-lookup"><span data-stu-id="434f5-147"></span></span> <span data-ttu-id="434f5-148">.</span><span class="sxs-lookup"><span data-stu-id="434f5-148"></span></span>  <br/> |<span data-ttu-id="434f5-149">任何附件。</span><span class="sxs-lookup"><span data-stu-id="434f5-149">Any attachment .</span></span> <span data-ttu-id="434f5-150">.</span><span class="sxs-lookup"><span data-stu-id="434f5-150"></span></span> <span data-ttu-id="434f5-151">.</span><span class="sxs-lookup"><span data-stu-id="434f5-151"></span></span> <span data-ttu-id="434f5-152">文件扩展名匹配。</span><span class="sxs-lookup"><span data-stu-id="434f5-152">file extension matches .</span></span> <span data-ttu-id="434f5-153">.</span><span class="sxs-lookup"><span data-stu-id="434f5-153"></span></span> <span data-ttu-id="434f5-154">.</span><span class="sxs-lookup"><span data-stu-id="434f5-154"></span></span>  <br/> |
|<span data-ttu-id="434f5-155">指定字词或短语</span><span class="sxs-lookup"><span data-stu-id="434f5-155">Specify words or phrases</span></span>  <br/> |<span data-ttu-id="434f5-156">添加以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="434f5-156">Add these file types:</span></span>  <br/> <span data-ttu-id="434f5-157">normal.dotm、.docm、xlsm、sltm、xlodbc.xla 加载、.xlam、xll、.pptm、potm、.ppam、ppsm、sldm</span><span class="sxs-lookup"><span data-stu-id="434f5-157">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span></span>  <br/>|
|<span data-ttu-id="434f5-158">执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="434f5-158">Do the following .</span></span> <span data-ttu-id="434f5-159">.</span><span class="sxs-lookup"><span data-stu-id="434f5-159"></span></span> <span data-ttu-id="434f5-160">.</span><span class="sxs-lookup"><span data-stu-id="434f5-160"></span></span>  <br/> |<span data-ttu-id="434f5-161">使用邮件通知收件人</span><span class="sxs-lookup"><span data-stu-id="434f5-161">Notify the recipient with a message</span></span>  <br/> |
|<span data-ttu-id="434f5-162">提供邮件文本</span><span class="sxs-lookup"><span data-stu-id="434f5-162">Provide message text</span></span>  <br/> |<span data-ttu-id="434f5-163">请勿从不知道的人打开这些类型的文件，因为它们可能包含恶意代码的宏。</span><span class="sxs-lookup"><span data-stu-id="434f5-163">Do not open these types of files from people you do not know because they might contain macros with malicious code.</span></span>  <br/> |
   
<span data-ttu-id="434f5-164">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="434f5-164">For more information, see:</span></span>
  
- [<span data-ttu-id="434f5-165">如何处理勒索软件</span><span class="sxs-lookup"><span data-stu-id="434f5-165">How to deal with ransomware</span></span>](https://go.microsoft.com/fwlink/?linkid=2016501)
    
- [<span data-ttu-id="434f5-166">还原你的 OneDrive</span><span class="sxs-lookup"><span data-stu-id="434f5-166">Restore your OneDrive</span></span>](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="434f5-167">停止电子邮件的自动转发</span><span class="sxs-lookup"><span data-stu-id="434f5-167">Stop auto-forwarding for email</span></span>

<span data-ttu-id="434f5-168">获取对用户邮箱的访问权限的黑客可以通过将邮箱设置为自动转发电子邮件来盗取邮件。</span><span class="sxs-lookup"><span data-stu-id="434f5-168">Hackers who gain access to a user's mailbox can steal mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="434f5-169">即使没有用户的意识，也会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="434f5-169">This can happen even without the user's awareness.</span></span> <span data-ttu-id="434f5-170">若要防止这种情况发生，请配置邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="434f5-170">To prevent this from happening, configure a mail flow rule.</span></span> 
  
<span data-ttu-id="434f5-171">若要创建邮件传输规则，请观看[此简短视频](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7)或按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="434f5-171">To create a mail transport rule, either watch [this short video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>
  
1. <span data-ttu-id="434f5-172">在 Microsoft 365 管理中心，选择 "**管理中心** \> " " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-172">In the Microsoft 365 admin center, select **Admin centers** \> **Exchange**.</span></span>
    
2. <span data-ttu-id="434f5-173">在 "**邮件流**" 类别中，选择 "**规则**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-173">In the **mail flow** category, select **rules**.</span></span>
    
3. <span data-ttu-id="434f5-174">选择**+**""，然后选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-174">Select **+**, and then select **Create a new rule**.</span></span>
    
4. <span data-ttu-id="434f5-175">若要查看所有选项，请在对话框底部选择 "**更多选项**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-175">To see all the options, select **More options** at the bottom of the dialog box.</span></span> 
    
5. <span data-ttu-id="434f5-176">应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="434f5-176">Apply the settings in the following table.</span></span> <span data-ttu-id="434f5-177">对其余设置使用默认值，除非您要对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="434f5-177">Use the default values for the rest of the settings, unless you want to change them.</span></span>
    
6. <span data-ttu-id="434f5-178">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="434f5-178">Select **Save**.</span></span>
    
|<span data-ttu-id="434f5-179">**设置**</span><span class="sxs-lookup"><span data-stu-id="434f5-179">**Setting**</span></span>|<span data-ttu-id="434f5-180">**在打开 Office 文件附件之前警告用户**</span><span class="sxs-lookup"><span data-stu-id="434f5-180">**Warn users before opening attachments of Office files**</span></span>|
|:-----|:-----|
|<span data-ttu-id="434f5-181">名称</span><span class="sxs-lookup"><span data-stu-id="434f5-181">Name</span></span>  <br/> |<span data-ttu-id="434f5-182">阻止电子邮件自动转发到外部域</span><span class="sxs-lookup"><span data-stu-id="434f5-182">Prevent auto forwarding of email to external domains</span></span>  <br/> |
|<span data-ttu-id="434f5-183">在以下情况应用此规则 .。。</span><span class="sxs-lookup"><span data-stu-id="434f5-183">Apply this rule if ...</span></span>  <br/> |<span data-ttu-id="434f5-184">发件人。</span><span class="sxs-lookup"><span data-stu-id="434f5-184">The sender .</span></span> <span data-ttu-id="434f5-185">.</span><span class="sxs-lookup"><span data-stu-id="434f5-185"></span></span> <span data-ttu-id="434f5-186">.</span><span class="sxs-lookup"><span data-stu-id="434f5-186"></span></span> <span data-ttu-id="434f5-187">为外部/内部。</span><span class="sxs-lookup"><span data-stu-id="434f5-187">is external/internal .</span></span> <span data-ttu-id="434f5-188">.</span><span class="sxs-lookup"><span data-stu-id="434f5-188"></span></span> <span data-ttu-id="434f5-189">.</span><span class="sxs-lookup"><span data-stu-id="434f5-189"></span></span> <span data-ttu-id="434f5-190">组织内部</span><span class="sxs-lookup"><span data-stu-id="434f5-190">Inside the organization</span></span>  <br/> |
|<span data-ttu-id="434f5-191">添加条件</span><span class="sxs-lookup"><span data-stu-id="434f5-191">Add condition</span></span>  <br/> |<span data-ttu-id="434f5-192">邮件属性。</span><span class="sxs-lookup"><span data-stu-id="434f5-192">The message properties .</span></span> <span data-ttu-id="434f5-193">.</span><span class="sxs-lookup"><span data-stu-id="434f5-193"></span></span> <span data-ttu-id="434f5-194">.</span><span class="sxs-lookup"><span data-stu-id="434f5-194"></span></span> <span data-ttu-id="434f5-195">包含邮件类型。</span><span class="sxs-lookup"><span data-stu-id="434f5-195">include the message type .</span></span> <span data-ttu-id="434f5-196">.</span><span class="sxs-lookup"><span data-stu-id="434f5-196"></span></span> <span data-ttu-id="434f5-197">.</span><span class="sxs-lookup"><span data-stu-id="434f5-197"></span></span> <span data-ttu-id="434f5-198">自动转发</span><span class="sxs-lookup"><span data-stu-id="434f5-198">Auto-forward</span></span>  <br/> |
|<span data-ttu-id="434f5-199">执行以下操作 .。。</span><span class="sxs-lookup"><span data-stu-id="434f5-199">Do the following ...</span></span>  <br/> |<span data-ttu-id="434f5-200">阻止邮件。</span><span class="sxs-lookup"><span data-stu-id="434f5-200">Block the message .</span></span> <span data-ttu-id="434f5-201">.</span><span class="sxs-lookup"><span data-stu-id="434f5-201"></span></span> <span data-ttu-id="434f5-202">.</span><span class="sxs-lookup"><span data-stu-id="434f5-202"></span></span> <span data-ttu-id="434f5-203">拒绝邮件并提供说明。</span><span class="sxs-lookup"><span data-stu-id="434f5-203">reject the message and include an explanation.</span></span>  <br/> |
|<span data-ttu-id="434f5-204">提供邮件文本</span><span class="sxs-lookup"><span data-stu-id="434f5-204">Provide message text</span></span>  <br/> |<span data-ttu-id="434f5-205">出于安全考虑，将阻止此组织外部的自动转发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="434f5-205">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="434f5-206">保护你的电子邮件免受网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="434f5-206">Protect your email from phishing attacks</span></span>

<span data-ttu-id="434f5-207">如果您为 Office 365 或 Microsoft 365 环境配置了一个或多个自定义域，则可以配置目标的反网络钓鱼保护。</span><span class="sxs-lookup"><span data-stu-id="434f5-207">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="434f5-208">ATP 反网络钓鱼保护是 Office 365 高级威胁防护的一部分，可帮助保护您的组织免受基于恶意模拟的网络钓鱼攻击和其他网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="434f5-208">ATP anti-phishing protection, part of Office 365 Advanced Threat Protection, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="434f5-209">如果尚未配置自定义域，则无需执行此操作。</span><span class="sxs-lookup"><span data-stu-id="434f5-209">If you haven't configured a custom domain, you don't need to do this.</span></span>
  
<span data-ttu-id="434f5-210">我们建议您通过创建策略来保护最重要的用户和您的自定义域，以此来开始保护。</span><span class="sxs-lookup"><span data-stu-id="434f5-210">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span> 

<span data-ttu-id="434f5-211">若要创建 ATP 反网络钓鱼策略，请观看[此简短的培训视频](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="434f5-211">To create an ATP anti-phishing policy, watch  [this short training video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>
  
1. <span data-ttu-id="434f5-212">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="434f5-212">Go to [https://protection.office.com](https://protection.office.com).</span></span> 
    
2. <span data-ttu-id="434f5-213">在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-213">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="434f5-214">在 "**策略**" 页上，选择 " **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-214">On the **Policy** page, choose **ATP anti-phishing**.</span></span>
    
4. <span data-ttu-id="434f5-215">在 "**反钓鱼网站**" 页上，选择 " **+ 创建**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-215">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="434f5-216">向导将启动，引导您完成定义您的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="434f5-216">A wizard launches that steps you through defining your anti-phishing policy.</span></span>
    
5. <span data-ttu-id="434f5-217">按下表中的建议指定策略的名称、说明和设置。</span><span class="sxs-lookup"><span data-stu-id="434f5-217">Specify the name, description, and settings for your policy as recommended in the following table.</span></span> <span data-ttu-id="434f5-218">有关更多详细信息，请参阅[了解 ATP 反网络钓鱼策略选项](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options)。</span><span class="sxs-lookup"><span data-stu-id="434f5-218">For more details, see [Learn about ATP anti-phishing policy options](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options).</span></span> 
    
6. <span data-ttu-id="434f5-219">查看设置后，根据需要选择 "**创建此策略**" 或 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-219">After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>
    

|<span data-ttu-id="434f5-220">**设置或选项**</span><span class="sxs-lookup"><span data-stu-id="434f5-220">**Setting or option**</span></span><br/>|<span data-ttu-id="434f5-221">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="434f5-221">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="434f5-222">名称</span><span class="sxs-lookup"><span data-stu-id="434f5-222">Name</span></span>  <br/> |<span data-ttu-id="434f5-223">域和最有价值的市场活动员工</span><span class="sxs-lookup"><span data-stu-id="434f5-223">Domain and most valuable campaign staff</span></span>  <br/> |
|<span data-ttu-id="434f5-224">说明</span><span class="sxs-lookup"><span data-stu-id="434f5-224">Description</span></span>  <br/> |<span data-ttu-id="434f5-225">确保不会模拟大多数重要的人员和我们的域。</span><span class="sxs-lookup"><span data-stu-id="434f5-225">Ensure most important staff and our domain are not being impersonated.</span></span>  <br/> |
|<span data-ttu-id="434f5-226">添加要保护的用户</span><span class="sxs-lookup"><span data-stu-id="434f5-226">Add users to protect</span></span>  <br/> |<span data-ttu-id="434f5-227">选择 **+ 添加条件，收件人为**。</span><span class="sxs-lookup"><span data-stu-id="434f5-227">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="434f5-228">键入用户名称或输入候选人、活动经理和其他重要教职员工成员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="434f5-228">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="434f5-229">您最大可以添加20个要从模拟中保护的内部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="434f5-229">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>  <br/> |
|<span data-ttu-id="434f5-230">添加要保护的域</span><span class="sxs-lookup"><span data-stu-id="434f5-230">Add domains to protect</span></span>  <br/> |<span data-ttu-id="434f5-231">选择 **"+ 添加条件，收件人域为"**。</span><span class="sxs-lookup"><span data-stu-id="434f5-231">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="434f5-232">输入与 Microsoft 365 订阅关联的自定义域（如果已定义一个）。</span><span class="sxs-lookup"><span data-stu-id="434f5-232">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="434f5-233">您可以输入一个以上的域。</span><span class="sxs-lookup"><span data-stu-id="434f5-233">You can enter more than one domain.</span></span>  <br/> |
|<span data-ttu-id="434f5-234">选择操作</span><span class="sxs-lookup"><span data-stu-id="434f5-234">Choose actions</span></span>  <br/> |<span data-ttu-id="434f5-235">如果模拟用户发送电子邮件：选择 "**将邮件重定向到另一个电子邮件地址**"，然后键入安全管理员的电子邮件地址;例如，*刘爱琳<span><span>@contoso .com*。</span><span class="sxs-lookup"><span data-stu-id="434f5-235">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span> <span data-ttu-id="434f5-236">如果由模拟域发送电子邮件：选择 "**隔离邮件**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-236">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>  <br/> |
|<span data-ttu-id="434f5-237">邮箱智能</span><span class="sxs-lookup"><span data-stu-id="434f5-237">Mailbox intelligence</span></span>  <br/> |<span data-ttu-id="434f5-238">默认情况下，当您创建新的反网络钓鱼策略时，将选择邮箱智能。</span><span class="sxs-lookup"><span data-stu-id="434f5-238">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="434f5-239">将此设置保留为 **"开"** 以获得最佳效果。</span><span class="sxs-lookup"><span data-stu-id="434f5-239">Leave this setting **On** for best results.</span></span>  <br/> |
|<span data-ttu-id="434f5-240">添加受信任的发件人和域</span><span class="sxs-lookup"><span data-stu-id="434f5-240">Add trusted senders and domains</span></span>  <br/> |<span data-ttu-id="434f5-241">你可以在此处添加你自己的域或任何其他受信任域。</span><span class="sxs-lookup"><span data-stu-id="434f5-241">Here you can add your own domain, or any other trusted domains.</span></span>  <br/> |
|<span data-ttu-id="434f5-242">应用于</span><span class="sxs-lookup"><span data-stu-id="434f5-242">Applied to</span></span>  <br/> |<span data-ttu-id="434f5-243">选择 **"收件人域"**。</span><span class="sxs-lookup"><span data-stu-id="434f5-243">Select **The recipient domain is**.</span></span> <span data-ttu-id="434f5-244">在**以下任一情况**下，选择 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-244">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="434f5-245">选择 " **+ 添加**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-245">Select **+ Add**.</span></span> <span data-ttu-id="434f5-246">选中域名称旁边的复选框，例如 " *contoso"。<span>com <span>*，请在列表中，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-246">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="434f5-247">选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-247">Select **Done**.</span></span>  <br/> |
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a><span data-ttu-id="434f5-248">使用 ATP 安全附件防止恶意附件和文件</span><span class="sxs-lookup"><span data-stu-id="434f5-248">Protect against malicious attachments and files with ATP Safe Attachments</span></span>

<span data-ttu-id="434f5-249">用户定期发送、接收和共享附件，如文档、演示文稿、电子表格等。</span><span class="sxs-lookup"><span data-stu-id="434f5-249">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="434f5-250">只需查看一封电子邮件，就能判断附件是安全还是恶意的，并不总是容易。</span><span class="sxs-lookup"><span data-stu-id="434f5-250">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="434f5-251">Office 365 高级威胁防护包括 ATP 安全附件保护，但默认情况下不启用此保护。</span><span class="sxs-lookup"><span data-stu-id="434f5-251">Office 365 Advanced Threat Protection includes ATP Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="434f5-252">我们建议您创建一个新规则以开始使用此保护。</span><span class="sxs-lookup"><span data-stu-id="434f5-252">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="434f5-253">此保护功能扩展到 SharePoint、OneDrive 和 Microsoft 团队中的文件。</span><span class="sxs-lookup"><span data-stu-id="434f5-253">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>
  
<span data-ttu-id="434f5-254">若要创建 ATP 安全附件策略，请观看[此简短视频](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="434f5-254">To create an ATP safe attachment policy, either watch [this short video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>
  
1. <span data-ttu-id="434f5-255">转到[https://protection.office.com](https://protection.office.com)，然后使用你的管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="434f5-255">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span> 
    
2. <span data-ttu-id="434f5-256">在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-256">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="434f5-257">在 "策略" 页上，选择 " **ATP 安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-257">On the Policy page, choose **ATP safe attachments**.</span></span>
    
4. <span data-ttu-id="434f5-258">在 "安全附件" 页面上，选中 "**启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP** " 复选框，以应用广泛的保护。</span><span class="sxs-lookup"><span data-stu-id="434f5-258">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span> 
    
5. <span data-ttu-id="434f5-259">选择**+** 以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="434f5-259">Select **+** to create a new policy.</span></span> 
    
6. <span data-ttu-id="434f5-260">应用下表中的设置。</span><span class="sxs-lookup"><span data-stu-id="434f5-260">Apply the settings in the following table.</span></span> 
    
7. <span data-ttu-id="434f5-261">查看设置后，根据需要选择 "**创建此策略**" 或 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-261">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>
    

|<span data-ttu-id="434f5-262">**设置或选项**</span><span class="sxs-lookup"><span data-stu-id="434f5-262">**Setting or option**</span></span>|<span data-ttu-id="434f5-263">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="434f5-263">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="434f5-264">名称</span><span class="sxs-lookup"><span data-stu-id="434f5-264">Name</span></span>  <br/> |<span data-ttu-id="434f5-265">使用检测到的恶意软件阻止当前和将来的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="434f5-265">Block current and future emails with detected malware.</span></span>  <br/> |
|<span data-ttu-id="434f5-266">说明</span><span class="sxs-lookup"><span data-stu-id="434f5-266">Description</span></span>  <br/> |<span data-ttu-id="434f5-267">使用检测到的恶意软件阻止当前和将来的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="434f5-267">Block current and future emails and attachments with detected malware.</span></span>  <br/> |
|<span data-ttu-id="434f5-268">保存附件未知的恶意软件响应</span><span class="sxs-lookup"><span data-stu-id="434f5-268">Save attachments unknown malware response</span></span>  <br/> |<span data-ttu-id="434f5-269">Select **block-阻止当前和将来的包含检测到的恶意软件的电子邮件和附件**。</span><span class="sxs-lookup"><span data-stu-id="434f5-269">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>  <br/> |
|<span data-ttu-id="434f5-270">在检测时重定向附件</span><span class="sxs-lookup"><span data-stu-id="434f5-270">Redirect attachment on detection</span></span>  <br/> |<span data-ttu-id="434f5-271">启用重定向（选择此框）输入管理员帐户或邮箱设置进行隔离。</span><span class="sxs-lookup"><span data-stu-id="434f5-271">Enable redirection (select this box)          Enter the admin account or a mailbox setup for quarantine.</span></span>          <span data-ttu-id="434f5-272">如果恶意软件扫描附件超时或发生错误（选中此框），请应用上面的选择。</span><span class="sxs-lookup"><span data-stu-id="434f5-272">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>  <br/> |
|<span data-ttu-id="434f5-273">应用于</span><span class="sxs-lookup"><span data-stu-id="434f5-273">Applied to</span></span>  <br/> |<span data-ttu-id="434f5-274">收件人域为。</span><span class="sxs-lookup"><span data-stu-id="434f5-274">The recipient domain is .</span></span> <span data-ttu-id="434f5-275">.</span><span class="sxs-lookup"><span data-stu-id="434f5-275"></span></span> <span data-ttu-id="434f5-276">.</span><span class="sxs-lookup"><span data-stu-id="434f5-276"></span></span> <span data-ttu-id="434f5-277">选择您的域。</span><span class="sxs-lookup"><span data-stu-id="434f5-277">select your domain.</span></span>  <br/> |
   
<span data-ttu-id="434f5-278">有关详细信息，请参阅[设置 Office 365 ATP 反网络钓鱼策略](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)。</span><span class="sxs-lookup"><span data-stu-id="434f5-278">For more information, see [Set up Office 365 ATP anti-phishing policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).</span></span>
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a><span data-ttu-id="434f5-279">使用 ATP 安全链接防御网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="434f5-279">Protect against phishing attacks with ATP Safe Links</span></span>

<span data-ttu-id="434f5-280">黑客有时会在电子邮件或其他文件的链接中隐藏恶意网站。</span><span class="sxs-lookup"><span data-stu-id="434f5-280">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="434f5-281">Office 365 ATP 安全链接（ATP 安全链接）是 Office 365 高级威胁防护的一部分，可通过在电子邮件和 Office 文档中提供 web 地址（Url）的单击验证时间来帮助保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="434f5-281">Office 365 ATP Safe Links (ATP Safe Links), part of Office 365 Advanced Threat Protection, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="434f5-282">通过 ATP 安全链接策略定义保护。</span><span class="sxs-lookup"><span data-stu-id="434f5-282">Protection is defined through ATP Safe Links policies.</span></span>
  
<span data-ttu-id="434f5-283">我们建议您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="434f5-283">We recommend that you do the following:</span></span>
  
- <span data-ttu-id="434f5-284">修改默认策略以提高保护。</span><span class="sxs-lookup"><span data-stu-id="434f5-284">Modify the default policy to increase protection.</span></span>
    
- <span data-ttu-id="434f5-285">添加目标为域中所有收件人的新策略。</span><span class="sxs-lookup"><span data-stu-id="434f5-285">Add a new policy targeted to all recipients in your domain.</span></span>
    
<span data-ttu-id="434f5-286">若要设置 ATP 安全链接，请观看[此简短的培训视频](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)，或完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="434f5-286">To set up ATP Safe Links, watch [this short training video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>
  
1. <span data-ttu-id="434f5-287">转到[https://protection.office.com](https://protection.office.com)，然后使用你的管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="434f5-287">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span> 
    
2. <span data-ttu-id="434f5-288">在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下，选择 "**策略**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-288">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="434f5-289">在 "策略" 页上，选择 " **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-289">On the Policy page, choose **ATP Safe Links**.</span></span>
    
<span data-ttu-id="434f5-290">若要修改默认策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="434f5-290">To modify the default policy:</span></span>
  
1. <span data-ttu-id="434f5-291">在 "安全链接" 页面上，在 "**适用于整个组织的策略**" 下，选择 "**默认**策略"。</span><span class="sxs-lookup"><span data-stu-id="434f5-291">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span> 
    
2. <span data-ttu-id="434f5-292">在 "**适用于除电子邮件以外的内容的设置**" 下，选择 " **office 365 专业增强版，office For iOS 和 Android**"。</span><span class="sxs-lookup"><span data-stu-id="434f5-292">Under **Settings that apply to content except email**, select **Office 365 ProPlus, Office for iOS and Android**.</span></span>
    
3. <span data-ttu-id="434f5-293">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="434f5-293">Select **Save**.</span></span> 
    
<span data-ttu-id="434f5-294">创建一个面向域中所有收件人的新策略：</span><span class="sxs-lookup"><span data-stu-id="434f5-294">To create a new policy targeted to all recipients in your domain:</span></span>
  
1. <span data-ttu-id="434f5-295">在 "安全链接" 页面上，在 "**适用于整个组织**的策略**+** " 下，选择 "创建新策略"。</span><span class="sxs-lookup"><span data-stu-id="434f5-295">On the Safe links page, under **Policies that apply to the entire organization**, select **+** to create a new policy.</span></span> 
    
2. <span data-ttu-id="434f5-296">应用下表中列出的设置。</span><span class="sxs-lookup"><span data-stu-id="434f5-296">Apply the settings listed in the following table.</span></span>
    
3. <span data-ttu-id="434f5-297">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="434f5-297">Select **Save**.</span></span> 

|<span data-ttu-id="434f5-298">**设置或选项**</span><span class="sxs-lookup"><span data-stu-id="434f5-298">**Setting or option**</span></span>|<span data-ttu-id="434f5-299">**推荐设置**</span><span class="sxs-lookup"><span data-stu-id="434f5-299">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="434f5-300">名称</span><span class="sxs-lookup"><span data-stu-id="434f5-300">Name</span></span>  <br/> |<span data-ttu-id="434f5-301">域中所有收件人的安全链接策略</span><span class="sxs-lookup"><span data-stu-id="434f5-301">Safe links policy for all recipients in the domain</span></span>  <br/> |
|<span data-ttu-id="434f5-302">选择邮件中未知的潜在恶意 Url 的操作</span><span class="sxs-lookup"><span data-stu-id="434f5-302">Select the action for unknown potentially malicious URLs in messages</span></span>  <br/> |<span data-ttu-id="434f5-303">**当用户单击链接时，将会重写并检查在已知恶意链接列表中的 "按 Url"，并对其进行检查**。</span><span class="sxs-lookup"><span data-stu-id="434f5-303">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>  <br/> |
|<span data-ttu-id="434f5-304">使用安全附件扫描可下载的内容</span><span class="sxs-lookup"><span data-stu-id="434f5-304">Use Safe Attachments to scan downloadable content</span></span>  <br/> |<span data-ttu-id="434f5-305">选中此框。</span><span class="sxs-lookup"><span data-stu-id="434f5-305">Select this box.</span></span>  <br/> |
|<span data-ttu-id="434f5-306">应用于</span><span class="sxs-lookup"><span data-stu-id="434f5-306">Applied to</span></span>  <br/> |<span data-ttu-id="434f5-307">收件人域为。</span><span class="sxs-lookup"><span data-stu-id="434f5-307">The recipient domain is .</span></span> <span data-ttu-id="434f5-308">.</span><span class="sxs-lookup"><span data-stu-id="434f5-308"></span></span> <span data-ttu-id="434f5-309">.</span><span class="sxs-lookup"><span data-stu-id="434f5-309"></span></span> <span data-ttu-id="434f5-310">选择您的域。</span><span class="sxs-lookup"><span data-stu-id="434f5-310">select your domain.</span></span>  <br/> |
   
<span data-ttu-id="434f5-311">有关详细信息，请参阅[Office 365 ATP 安全链接](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="434f5-311">For more information, see [Office 365 ATP safe links](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="434f5-312">转到 Intune 管理中心</span><span class="sxs-lookup"><span data-stu-id="434f5-312">Go to Intune admin center</span></span>

1. <span data-ttu-id="434f5-313">登录到[Azure 门户](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="434f5-313">Sign in to [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="434f5-314">在 "**搜索" 框**中选择 "**所有服务**"，然后键入*Intune* 。</span><span class="sxs-lookup"><span data-stu-id="434f5-314">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="434f5-315">在结果出现后，选择 " **Microsoft Intune** " 旁边的 "开始"，使其成为收藏且易于查找。</span><span class="sxs-lookup"><span data-stu-id="434f5-315">Once the results appear, select the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="434f5-316">除了管理中心之外，你还可以使用 Intune 注册和管理你的组织的设备。</span><span class="sxs-lookup"><span data-stu-id="434f5-316">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="434f5-317">有关详细信息，请参阅[Windows 设备注册方法](https://docs.microsoft.com/intune/enrollment-method-capabs)和由[Intune 管理的设备的注册选项](https://docs.microsoft.com/intune/enrollment-options)的功能。</span><span class="sxs-lookup"><span data-stu-id="434f5-317">For more information, see [Capabilities by enrollment method for Windows devices](https://docs.microsoft.com/intune/enrollment-method-capabs) and [Enrollment options for devices managed by Intune](https://docs.microsoft.com/intune/enrollment-options).</span></span>
