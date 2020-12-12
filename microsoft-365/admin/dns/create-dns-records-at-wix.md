---
title: 在 Wix 为 Microsoft 创建 DNS 记录
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: 了解如何验证域，并设置电子邮件、Skype for Business Online 和其他 Microsoft Wix 服务的 DNS 记录。
ms.openlocfilehash: 01317f7e2da87b532c93f12269fd65b7d4fe2dd6
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656875"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="b9022-103">在 Wix 为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="b9022-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="b9022-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="b9022-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="b9022-105">如果 Wix 是 DNS 托管提供商，请按照本文中的步骤验证域，并设置电子邮件、Skype for Business Online 等的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="b9022-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="b9022-106">下面是要添加的主要记录。</span><span class="sxs-lookup"><span data-stu-id="b9022-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="b9022-107">[添加 TXT 记录进行验证](#add-a-txt-record-for-verification)。</span><span class="sxs-lookup"><span data-stu-id="b9022-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="b9022-108">[添加 MX 记录，以便你的域的电子邮件发送到 Microsoft。](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="b9022-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="b9022-109">[添加 Microsoft 所需的五条 CNAME 记录](#add-the-five-cname-records-that-are-required-for-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="b9022-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="b9022-110">[为 SPF 添加 TXT 记录以帮助防止垃圾邮件](#add-a-txt-record-for-spf-to-help-prevent-email-spam)。</span><span class="sxs-lookup"><span data-stu-id="b9022-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="b9022-111">[添加 Microsoft 所需的两条 SRV 记录](#add-the-two-srv-records-that-are-required-for-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="b9022-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="b9022-112">在 Wix 添加这些记录后，你的域将设置为使用 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="b9022-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b9022-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b9022-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b9022-116">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="b9022-116">Add a TXT record for verification</span></span>
<span data-ttu-id="b9022-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="b9022-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="b9022-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="b9022-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9022-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="b9022-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="b9022-122">WIX 不支持子域的 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="b9022-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="b9022-123">To get started， go to your domains page at Wix by using [this link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="b9022-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="b9022-124">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="b9022-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b9022-125">在 **"我的域"** 页上的 **"高级** "区域中，选择 **"编辑 DNS"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="b9022-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="b9022-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span><span class="sxs-lookup"><span data-stu-id="b9022-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="b9022-127">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="b9022-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="b9022-128">主机名</span><span class="sxs-lookup"><span data-stu-id="b9022-128">Host Name</span></span> <br/> | <span data-ttu-id="b9022-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="b9022-129">TXT Value</span></span> <br/> | <span data-ttu-id="b9022-130">TTL</span><span class="sxs-lookup"><span data-stu-id="b9022-130">TTL</span></span> <br/> |
   |<span data-ttu-id="b9022-131">自动填充</span><span class="sxs-lookup"><span data-stu-id="b9022-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="b9022-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b9022-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b9022-133">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="b9022-133">**Note:** This is an example.</span></span> <span data-ttu-id="b9022-134">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="b9022-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="b9022-135">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="b9022-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="b9022-136">1 小时</span><span class="sxs-lookup"><span data-stu-id="b9022-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="b9022-137">选择 **DNS** 编辑器顶部的"保存 DNS"按钮。</span><span class="sxs-lookup"><span data-stu-id="b9022-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="b9022-138">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="b9022-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b9022-139">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="b9022-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="b9022-140">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="b9022-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b9022-141">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="b9022-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="b9022-142">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="b9022-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="b9022-143">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="b9022-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="b9022-144">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="b9022-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b9022-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b9022-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="b9022-148">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="b9022-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="b9022-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="b9022-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="b9022-150">To get started， go to your domains page at Wix by using [this link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="b9022-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="b9022-151">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="b9022-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b9022-152">在 **"我的域** "页上的" **邮箱** "区域中，选择" **配置 MX 记录** "链接。</span><span class="sxs-lookup"><span data-stu-id="b9022-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="b9022-153">从 **"** 电子邮件提供商 **"** 下拉列表中选择"其他"。</span><span class="sxs-lookup"><span data-stu-id="b9022-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="b9022-154">选择 **+ 添加另一个**。</span><span class="sxs-lookup"><span data-stu-id="b9022-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="b9022-155">在新记录的框中，键入或复制并粘贴下表中的值：</span><span class="sxs-lookup"><span data-stu-id="b9022-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="b9022-156">主机名</span><span class="sxs-lookup"><span data-stu-id="b9022-156">Host Name</span></span> | <span data-ttu-id="b9022-157">Points to </span><span class="sxs-lookup"><span data-stu-id="b9022-157">Points to</span></span> | <span data-ttu-id="b9022-158">优先级</span><span class="sxs-lookup"><span data-stu-id="b9022-158">Priority</span></span> | <span data-ttu-id="b9022-159">TTL</span><span class="sxs-lookup"><span data-stu-id="b9022-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="b9022-160">自动填充</span><span class="sxs-lookup"><span data-stu-id="b9022-160">Automatically populated</span></span> <br/> | <span data-ttu-id="b9022-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b9022-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="b9022-162">**注意：** 从  *\<domain-key\>*  Microsoft 帐户获取你的帐户。</span><span class="sxs-lookup"><span data-stu-id="b9022-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   <span data-ttu-id="b9022-163">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="b9022-163">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span> |<span data-ttu-id="b9022-164">0</span><span class="sxs-lookup"><span data-stu-id="b9022-164">0</span></span>  <br/> <span data-ttu-id="b9022-165">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="b9022-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="b9022-166">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b9022-166">1 Hour</span></span>|
   
6. <span data-ttu-id="b9022-167">如果列出了任何其他 MX 记录，请删除其中每个记录。</span><span class="sxs-lookup"><span data-stu-id="b9022-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="b9022-168">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="b9022-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="b9022-169">在确认对话框中，选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="b9022-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="b9022-170">添加 Microsoft 所需的 5 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="b9022-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="b9022-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="b9022-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="b9022-172">To get started， go to your domains page at Wix by using [this link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="b9022-172">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="b9022-173">You'll be prompted to login first.</span><span class="sxs-lookup"><span data-stu-id="b9022-173">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="b9022-174">在 **"我的域"** 页上的 **"高级** "区域中，选择 **"编辑 DNS"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="b9022-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="b9022-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span><span class="sxs-lookup"><span data-stu-id="b9022-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="b9022-176">在新记录的框中，键入或复制并粘贴下表中的值：</span><span class="sxs-lookup"><span data-stu-id="b9022-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="b9022-177">主机名</span><span class="sxs-lookup"><span data-stu-id="b9022-177">Host Name</span></span> | <span data-ttu-id="b9022-178">Points to </span><span class="sxs-lookup"><span data-stu-id="b9022-178">Points to</span></span> | <span data-ttu-id="b9022-179">TTL</span><span class="sxs-lookup"><span data-stu-id="b9022-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="b9022-180">自动发现</span><span class="sxs-lookup"><span data-stu-id="b9022-180">autodiscover</span></span>  <br/> |<span data-ttu-id="b9022-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="b9022-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="b9022-182">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b9022-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="b9022-183">sip</span><span class="sxs-lookup"><span data-stu-id="b9022-183">sip</span></span>  <br/> |<span data-ttu-id="b9022-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b9022-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="b9022-185">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b9022-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="b9022-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="b9022-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="b9022-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b9022-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="b9022-188">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b9022-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="b9022-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="b9022-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="b9022-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="b9022-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="b9022-191">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b9022-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="b9022-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="b9022-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="b9022-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b9022-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="b9022-194">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b9022-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="b9022-195">选择 **DNS** 编辑器顶部的"保存 DNS"按钮。</span><span class="sxs-lookup"><span data-stu-id="b9022-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="b9022-196">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="b9022-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="b9022-197">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="b9022-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="b9022-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="b9022-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9022-199">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="b9022-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="b9022-200">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="b9022-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="b9022-201">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="b9022-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="b9022-202">相反，将所需的 Microsoft 值添加到当前记录，以便具有一个  *包含这*  两组值的 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="b9022-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="b9022-203">To get started， go to your domains page at Wix by using [this link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="b9022-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="b9022-204">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="b9022-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b9022-205">在 **"我的域"** 页上的 **"高级** "区域中，选择 **"编辑 DNS"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="b9022-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="b9022-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span><span class="sxs-lookup"><span data-stu-id="b9022-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="b9022-207">在新记录的框中，键入或复制并粘贴下表中的值：</span><span class="sxs-lookup"><span data-stu-id="b9022-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="b9022-208">主机名</span><span class="sxs-lookup"><span data-stu-id="b9022-208">Host Name</span></span> | <span data-ttu-id="b9022-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="b9022-209">TXT Value</span></span> | <span data-ttu-id="b9022-210">TTL</span><span class="sxs-lookup"><span data-stu-id="b9022-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="b9022-211">[保留此空白]</span><span class="sxs-lookup"><span data-stu-id="b9022-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="b9022-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="b9022-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="b9022-213">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="b9022-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="b9022-214">TXT</span><span class="sxs-lookup"><span data-stu-id="b9022-214">TXT</span></span>  <br/> | <span data-ttu-id="b9022-215">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b9022-215">1 Hour</span></span> |
   
5. <span data-ttu-id="b9022-216">选择 **DNS** 编辑器顶部的"保存 DNS"按钮。</span><span class="sxs-lookup"><span data-stu-id="b9022-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="b9022-217">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="b9022-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="b9022-218">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="b9022-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="b9022-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="b9022-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="b9022-220">To get started， go to your domains page at Wix by using [this link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account)</span><span class="sxs-lookup"><span data-stu-id="b9022-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="b9022-221">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="b9022-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b9022-222">在 **"我的域"** 页上的 **"高级** "区域中，选择 **"编辑 DNS"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="b9022-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="b9022-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span><span class="sxs-lookup"><span data-stu-id="b9022-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="b9022-224">在新记录的框中，键入或复制并粘贴下表中的值：</span><span class="sxs-lookup"><span data-stu-id="b9022-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="b9022-225">服务</span><span class="sxs-lookup"><span data-stu-id="b9022-225">Service</span></span> | <span data-ttu-id="b9022-226">协议</span><span class="sxs-lookup"><span data-stu-id="b9022-226">Protocol</span></span> | <span data-ttu-id="b9022-227">名称</span><span class="sxs-lookup"><span data-stu-id="b9022-227">Name</span></span> | <span data-ttu-id="b9022-228">粗细</span><span class="sxs-lookup"><span data-stu-id="b9022-228">Weight</span></span> | <span data-ttu-id="b9022-229">端口</span><span class="sxs-lookup"><span data-stu-id="b9022-229">Port</span></span> | <span data-ttu-id="b9022-230">Target</span><span class="sxs-lookup"><span data-stu-id="b9022-230">Target</span></span> | <span data-ttu-id="b9022-231">优先级</span><span class="sxs-lookup"><span data-stu-id="b9022-231">Priority</span></span> | <span data-ttu-id="b9022-232">TTL</span><span class="sxs-lookup"><span data-stu-id="b9022-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="b9022-233">sip</span><span class="sxs-lookup"><span data-stu-id="b9022-233">sip</span></span>  |<span data-ttu-id="b9022-234">tls</span><span class="sxs-lookup"><span data-stu-id="b9022-234">tls</span></span>  |<span data-ttu-id="b9022-235">自动填充</span><span class="sxs-lookup"><span data-stu-id="b9022-235">Automatically populated</span></span> |<span data-ttu-id="b9022-236">1 </span><span class="sxs-lookup"><span data-stu-id="b9022-236">1</span></span>  |<span data-ttu-id="b9022-237">443</span><span class="sxs-lookup"><span data-stu-id="b9022-237">443</span></span>   |<span data-ttu-id="b9022-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b9022-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="b9022-239">100</span><span class="sxs-lookup"><span data-stu-id="b9022-239">100</span></span> |<span data-ttu-id="b9022-240">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b9022-240">1 Hour</span></span> |
   |<span data-ttu-id="b9022-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="b9022-241">sipfed</span></span>|<span data-ttu-id="b9022-242">tcp</span><span class="sxs-lookup"><span data-stu-id="b9022-242">tcp</span></span> |<span data-ttu-id="b9022-243">自动填充</span><span class="sxs-lookup"><span data-stu-id="b9022-243">Automatically populated</span></span>|<span data-ttu-id="b9022-244">1 </span><span class="sxs-lookup"><span data-stu-id="b9022-244">1</span></span> |<span data-ttu-id="b9022-245">5061</span><span class="sxs-lookup"><span data-stu-id="b9022-245">5061</span></span> |<span data-ttu-id="b9022-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="b9022-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="b9022-247">100</span><span class="sxs-lookup"><span data-stu-id="b9022-247">100</span></span> | <span data-ttu-id="b9022-248">1 Hour</span><span class="sxs-lookup"><span data-stu-id="b9022-248">1 Hour</span></span> |
   
5. <span data-ttu-id="b9022-249">选择 **DNS** 编辑器顶部的"保存 DNS"按钮。</span><span class="sxs-lookup"><span data-stu-id="b9022-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="b9022-250">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="b9022-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b9022-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="b9022-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
