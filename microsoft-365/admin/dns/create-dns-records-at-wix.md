---
title: 在 Wix 处为 Microsoft 创建 DNS 记录
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: 了解如何验证您的域，并在 Wix for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: b5fe216e65954bbcbdd9a1da223258a8362743ca
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400288"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="8bd7e-103">在 Wix 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="8bd7e-103">Create DNS records at Wix for Microsoft</span></span>

 <span data-ttu-id="8bd7e-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8bd7e-105">如果 Wix 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8bd7e-106">下面是要添加的主要记录。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="8bd7e-107">[添加 TXT 记录进行验证](#add-a-txt-record-for-verification)。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="8bd7e-108">[添加 MX 记录，以便你的域的电子邮件将发送给 Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="8bd7e-109">[添加 Microsoft 所需的五个 CNAME 记录](#add-the-five-cname-records-that-are-required-for-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="8bd7e-110">[为 SPF 添加 TXT 记录以帮助防止垃圾邮件](#add-a-txt-record-for-spf-to-help-prevent-email-spam)。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="8bd7e-111">[添加 Microsoft 所需的两条 SRV 记录](#add-the-two-srv-records-that-are-required-for-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="8bd7e-112">在 Wix 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="8bd7e-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8bd7e-116">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="8bd7e-116">Add a TXT record for verification</span></span>
<span data-ttu-id="8bd7e-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd7e-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="8bd7e-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8bd7e-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8bd7e-122">若要开始，请使用[此链接](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)转到 Wix 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="8bd7e-123">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8bd7e-124">在 "**我的域**" 页面上的 "**高级**" 区域中，选择 "**编辑 DNS** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="8bd7e-125">在 DNS 编辑器的**TXT （文本）** 行中选择 " **+ 添加另一个**"。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="8bd7e-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="8bd7e-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-127">**Host Name**</span></span> <br/> |<span data-ttu-id="8bd7e-128">**TXT 值**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="8bd7e-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="8bd7e-130">自动填充</span><span class="sxs-lookup"><span data-stu-id="8bd7e-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="8bd7e-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8bd7e-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8bd7e-132">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-132">**Note:** This is an example.</span></span> <span data-ttu-id="8bd7e-133">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="8bd7e-134">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="8bd7e-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="8bd7e-135">1 小时</span><span class="sxs-lookup"><span data-stu-id="8bd7e-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="8bd7e-136">选择 DNS 编辑器顶部的 "**保存 DNS** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="8bd7e-137">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8bd7e-138">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="8bd7e-139">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8bd7e-140">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="8bd7e-141">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="8bd7e-142">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="8bd7e-143">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8bd7e-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8bd7e-147">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="8bd7e-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8bd7e-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd7e-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="8bd7e-149">若要开始，请使用[此链接](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)转到 Wix 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="8bd7e-150">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8bd7e-151">在 "**我的域**" 页面上的 "**邮箱**" 区域中，选择 "**配置您的 MX 记录**" 链接。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="8bd7e-152">从 "**电子邮件提供商**" 下拉列表中选择 "**其他**"。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="8bd7e-153">选择 " **+ 添加另一个**"。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="8bd7e-154">在新记录的框中，键入或复制并粘贴下表中的值：</span><span class="sxs-lookup"><span data-stu-id="8bd7e-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="8bd7e-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-155">**Host Name**</span></span>|<span data-ttu-id="8bd7e-156">**指向**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-156">**Points to**</span></span>|<span data-ttu-id="8bd7e-157">**优先级**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-157">**Priority**</span></span>|<span data-ttu-id="8bd7e-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8bd7e-159">自动填充</span><span class="sxs-lookup"><span data-stu-id="8bd7e-159">Automatically populated</span></span> <br/> | <span data-ttu-id="8bd7e-160">*\<domain-key\>*。 mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8bd7e-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="8bd7e-161">\**注意：\*\*\*\<domain-key\>* 从你的 Microsoft 帐户获取你的。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-161">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   <span data-ttu-id="8bd7e-162">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="8bd7e-162">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span> |<span data-ttu-id="8bd7e-163">0</span><span class="sxs-lookup"><span data-stu-id="8bd7e-163">0</span></span>  <br/> <span data-ttu-id="8bd7e-164">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="8bd7e-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="8bd7e-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8bd7e-165">1 Hour</span></span>|
   
6. <span data-ttu-id="8bd7e-166">如果列出了任何其他 MX 记录，请将其删除。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="8bd7e-167">选择“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="8bd7e-168">在确认对话框中，选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8bd7e-169">添加 Microsoft 所需的五个 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="8bd7e-169">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8bd7e-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd7e-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="8bd7e-171">若要开始，请使用[此链接](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)转到 Wix 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-171">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="8bd7e-172">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="8bd7e-172">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="8bd7e-173">在 "**我的域**" 页面上的 "**高级**" 区域中，选择 "**编辑 DNS** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="8bd7e-174">在 DNS 编辑器的 " **cname （别名）** " 行中选择 "+ 向每个 Cname 记录**添加另一个**"。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="8bd7e-175">在新记录的框中，键入或复制并粘贴下表中的值：</span><span class="sxs-lookup"><span data-stu-id="8bd7e-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="8bd7e-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-176">**Host Name**</span></span>|<span data-ttu-id="8bd7e-177">**指向**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-177">**Points to**</span></span>|<span data-ttu-id="8bd7e-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8bd7e-179">自动发现</span><span class="sxs-lookup"><span data-stu-id="8bd7e-179">autodiscover</span></span>  <br/> |<span data-ttu-id="8bd7e-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8bd7e-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="8bd7e-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8bd7e-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="8bd7e-182">sip</span><span class="sxs-lookup"><span data-stu-id="8bd7e-182">sip</span></span>  <br/> |<span data-ttu-id="8bd7e-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8bd7e-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="8bd7e-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8bd7e-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="8bd7e-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8bd7e-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8bd7e-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8bd7e-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="8bd7e-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8bd7e-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="8bd7e-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8bd7e-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8bd7e-189">EnterpriseRegistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8bd7e-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="8bd7e-190">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8bd7e-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="8bd7e-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8bd7e-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8bd7e-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8bd7e-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="8bd7e-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8bd7e-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="8bd7e-194">选择 DNS 编辑器顶部的 "**保存 DNS** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="8bd7e-195">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8bd7e-196">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="8bd7e-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8bd7e-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd7e-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bd7e-198">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8bd7e-199">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8bd7e-200">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-200">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8bd7e-201">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-201">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="8bd7e-202">若要开始，请使用[此链接](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)转到 Wix 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="8bd7e-203">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8bd7e-204">在 "**我的域**" 页面上的 "**高级**" 区域中，选择 "**编辑 DNS** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="8bd7e-205">在 DNS 编辑器的**TXT （文本）** 行中选择 " **+ 添加另一个**"。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="8bd7e-206">在新记录的框中，键入或复制并粘贴下表中的值：</span><span class="sxs-lookup"><span data-stu-id="8bd7e-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="8bd7e-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-207">**Host Name**</span></span>|<span data-ttu-id="8bd7e-208">**TXT 值**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-208">**TXT Value**</span></span>|<span data-ttu-id="8bd7e-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8bd7e-210">[保留此空白]</span><span class="sxs-lookup"><span data-stu-id="8bd7e-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="8bd7e-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8bd7e-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8bd7e-212">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="8bd7e-213">TXT</span><span class="sxs-lookup"><span data-stu-id="8bd7e-213">TXT</span></span>  <br/> | <span data-ttu-id="8bd7e-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8bd7e-214">1 Hour</span></span> |
   
5. <span data-ttu-id="8bd7e-215">选择 DNS 编辑器顶部的 "**保存 DNS** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="8bd7e-216">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8bd7e-217">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="8bd7e-217">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8bd7e-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="8bd7e-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="8bd7e-219">若要开始，请使用[此链接](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)转到 Wix 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="8bd7e-220">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="8bd7e-221">在 "**我的域**" 页面上的 "**高级**" 区域中，选择 "**编辑 DNS** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="8bd7e-222">在 DNS 编辑器的**SRV**行中选择 " **+ 添加另一个**"。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="8bd7e-223">在新记录的框中，键入或复制并粘贴下表中的值：</span><span class="sxs-lookup"><span data-stu-id="8bd7e-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="8bd7e-224">**服务**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-224">**Service**</span></span>|<span data-ttu-id="8bd7e-225">**协议**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-225">**Protocol**</span></span>|<span data-ttu-id="8bd7e-226">**名称**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-226">**Name**</span></span>|<span data-ttu-id="8bd7e-227">**权重**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-227">**Weight**</span></span>|<span data-ttu-id="8bd7e-228">**端口**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-228">**Port**</span></span>|<span data-ttu-id="8bd7e-229">**目标**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-229">**Target**</span></span>|<span data-ttu-id="8bd7e-230">**优先级**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-230">**Priority**</span></span>|<span data-ttu-id="8bd7e-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8bd7e-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8bd7e-232">sip</span><span class="sxs-lookup"><span data-stu-id="8bd7e-232">sip</span></span>  |<span data-ttu-id="8bd7e-233">tls</span><span class="sxs-lookup"><span data-stu-id="8bd7e-233">tls</span></span>  |<span data-ttu-id="8bd7e-234">自动填充</span><span class="sxs-lookup"><span data-stu-id="8bd7e-234">Automatically populated</span></span> |<span data-ttu-id="8bd7e-235">1 </span><span class="sxs-lookup"><span data-stu-id="8bd7e-235">1</span></span>  |<span data-ttu-id="8bd7e-236">443</span><span class="sxs-lookup"><span data-stu-id="8bd7e-236">443</span></span>   |<span data-ttu-id="8bd7e-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8bd7e-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="8bd7e-238">100</span><span class="sxs-lookup"><span data-stu-id="8bd7e-238">100</span></span> |<span data-ttu-id="8bd7e-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8bd7e-239">1 Hour</span></span> |
|<span data-ttu-id="8bd7e-240">sipfed.online.lync.com></span><span class="sxs-lookup"><span data-stu-id="8bd7e-240">sipfed</span></span>|<span data-ttu-id="8bd7e-241">tcp</span><span class="sxs-lookup"><span data-stu-id="8bd7e-241">tcp</span></span> |<span data-ttu-id="8bd7e-242">自动填充</span><span class="sxs-lookup"><span data-stu-id="8bd7e-242">Automatically populated</span></span>|<span data-ttu-id="8bd7e-243">1 </span><span class="sxs-lookup"><span data-stu-id="8bd7e-243">1</span></span> |<span data-ttu-id="8bd7e-244">5061</span><span class="sxs-lookup"><span data-stu-id="8bd7e-244">5061</span></span> |<span data-ttu-id="8bd7e-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8bd7e-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="8bd7e-246">100</span><span class="sxs-lookup"><span data-stu-id="8bd7e-246">100</span></span> | <span data-ttu-id="8bd7e-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="8bd7e-247">1 Hour</span></span> |
   
5. <span data-ttu-id="8bd7e-248">选择 DNS 编辑器顶部的 "**保存 DNS** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="8bd7e-249">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="8bd7e-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="8bd7e-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

