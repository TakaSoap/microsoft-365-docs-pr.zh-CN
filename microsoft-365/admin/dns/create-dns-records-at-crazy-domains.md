---
title: 在 Microsoft 的 Crazy Domains 创建 DNS 记录
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: 了解如何在 Crazy Domains for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 425ecfa6f8b6c4085bdffb3d2701008ecb895b84
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910452"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="6d5d6-103">在 Microsoft 的 Crazy Domains 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="6d5d6-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="6d5d6-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6d5d6-105">如果 Crazy Domains 是 DNS 托管提供商，请按照本文中的步骤验证域，并设置电子邮件、Skype for Business Online 等的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="6d5d6-106">在 Crazy Domains 添加这些记录后，你的域将设置为使用 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="6d5d6-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6d5d6-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="6d5d6-110">Add a TXT record for verification</span></span>
<span data-ttu-id="6d5d6-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6d5d6-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6d5d6-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d5d6-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6d5d6-p104">要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="6d5d6-119">在"**我的帐户"部分**，选择"**域"。**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-119">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="6d5d6-121">在 **"域名"** 页上的"域 **"部分，** 选择要更新的域的名称。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-121">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="6d5d6-123">在 **"DNS 设置"** 部分，选择下拉列表图标。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-123">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="6d5d6-125">选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-125">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="6d5d6-127">从" **添加记录**"下拉列表中选择" **TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-127">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verify-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="6d5d6-129">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-129">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="6d5d6-131">在新记录的框中，键入或复制粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="6d5d6-132">**子域**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-132">**Sub Domain**</span></span>|<span data-ttu-id="6d5d6-133">**文本记录**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-133">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6d5d6-134">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="6d5d6-134">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6d5d6-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6d5d6-135">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6d5d6-136">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-136">**Note:** This is an example.</span></span> <span data-ttu-id="6d5d6-137">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-137">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="6d5d6-138">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="6d5d6-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="6d5d6-140">选择“更新”。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-140">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="6d5d6-142">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6d5d6-143">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="6d5d6-144">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6d5d6-145">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="6d5d6-146">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="6d5d6-147">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-147">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="6d5d6-148">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-148">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6d5d6-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="6d5d6-152">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="6d5d6-152">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="6d5d6-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6d5d6-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="6d5d6-p107">要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="6d5d6-157">在"**我的帐户"部分**，选择"**域"。**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-157">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="6d5d6-159">在 **"域名"** 页上的"域 **"部分，** 选择要更新的域的名称。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-159">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="6d5d6-161">在 **"DNS 设置"** 部分，选择下拉列表图标。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-161">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="6d5d6-163">选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-163">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="6d5d6-165">从 **"添加记录\*\*\*\*："下拉列表** 中选择"MX 记录"。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-165">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="6d5d6-167">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-167">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="6d5d6-169">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-169">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="6d5d6-170"> (从下拉列表 **中选择** 优先级值。) </span><span class="sxs-lookup"><span data-stu-id="6d5d6-170">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6d5d6-171">**区域邮件**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-171">**Mail For Zone**</span></span>|<span data-ttu-id="6d5d6-172">**Priority**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-172">**Priority**</span></span>|<span data-ttu-id="6d5d6-173">**分配给服务器**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-173">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="6d5d6-174">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="6d5d6-174">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6d5d6-175">1</span><span class="sxs-lookup"><span data-stu-id="6d5d6-175">1</span></span>  <br/> <span data-ttu-id="6d5d6-176">有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="6d5d6-176">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="6d5d6-177">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6d5d6-177">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="6d5d6-178">**注意：** 从  *\<domain-key\>*  Microsoft 帐户获取你的信息。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-178">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="6d5d6-179">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="6d5d6-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-Configure-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="6d5d6-181">选择“更新”。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-181">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="6d5d6-183">如果"MX 记录"部分列出了任何其他 **MX** 记录，请为其中一条记录选择"修改"。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-183">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="6d5d6-185">选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-185">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-Configure-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="6d5d6-187">选择 **"更新** "以确认删除。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-187">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-Configure-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="6d5d6-189">使用相同的过程删除列表中任何其他 MX 记录，直到仅保留您之前在此过程中添加的记录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-189">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="6d5d6-190">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="6d5d6-190">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="6d5d6-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6d5d6-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="6d5d6-p109">要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="6d5d6-195">在"**我的帐户"部分**，选择"**域"。**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-195">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="6d5d6-197">在 **"域名"** 页上的"域 **"部分，** 选择要更新的域的名称。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-197">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="6d5d6-199">在 **"DNS 设置"** 部分，选择下拉列表图标。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-199">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="6d5d6-201">选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-201">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="6d5d6-203">从 **"添加记录\*\*\*\*："下拉列表** 中选择"CNAME 记录"。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-203">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="6d5d6-205">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-205">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="6d5d6-207">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-207">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="6d5d6-208">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-208">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="6d5d6-209">**子域**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-209">**Sub Domain**</span></span>|<span data-ttu-id="6d5d6-210">**别名**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-210">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6d5d6-211">自动发现</span><span class="sxs-lookup"><span data-stu-id="6d5d6-211">autodiscover</span></span>  <br/> |<span data-ttu-id="6d5d6-212">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6d5d6-212">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="6d5d6-213">sip</span><span class="sxs-lookup"><span data-stu-id="6d5d6-213">sip</span></span>  <br/> |<span data-ttu-id="6d5d6-214">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6d5d6-214">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6d5d6-215">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6d5d6-215">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6d5d6-216">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6d5d6-216">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6d5d6-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6d5d6-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6d5d6-218">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6d5d6-218">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="6d5d6-219">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6d5d6-219">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6d5d6-220">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6d5d6-220">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Configure-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="6d5d6-222">选择 **"添加 CNAME 记录"。**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-222">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="6d5d6-224">添加第二条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-224">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="6d5d6-225">In the boxes for the new record， use the values from the next row in the table， and then again select **Add CNAME Record**.</span><span class="sxs-lookup"><span data-stu-id="6d5d6-225">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="6d5d6-226">重复该过程，直到创建完全部 6 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-226">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="6d5d6-227">选择 **"更新** "保存更改。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-227">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Configure-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6d5d6-229">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="6d5d6-229">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6d5d6-230"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6d5d6-230"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d5d6-231">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-231">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6d5d6-232">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-232">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6d5d6-233">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-233">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="6d5d6-234">相反，将所需的 Microsoft 值添加到当前记录，以便你有一个  *包含这*  两组值的 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-234">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="6d5d6-p111">要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="6d5d6-238">在"**我的帐户"部分**，选择"**域"。**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-238">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="6d5d6-240">在 **"域名"** 页上的"域 **"部分，** 选择要更新的域的名称。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-240">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="6d5d6-242">在 **"DNS 设置"** 部分，选择下拉列表图标。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-242">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="6d5d6-244">选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-244">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="6d5d6-246">从 **添加记录** ： 下拉列表 **中选择** TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-246">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="6d5d6-248">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-248">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="6d5d6-250">在新记录的框中，键入或粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-250">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="6d5d6-251">**子域**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-251">**Sub Domain**</span></span>|<span data-ttu-id="6d5d6-252">**文本记录**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-252">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6d5d6-253">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="6d5d6-253">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6d5d6-254">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6d5d6-254">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6d5d6-255">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-255">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-Configure-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="6d5d6-257">选择“更新”。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-257">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Configure-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="6d5d6-259">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="6d5d6-259">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="6d5d6-260"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6d5d6-260"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="6d5d6-p112">要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-Configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="6d5d6-264">在"**我的帐户"部分**，选择"**域"。**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-264">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="6d5d6-266">在 **"域名"** 页上的"域 **"部分，** 选择要更新的域的名称。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-266">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="6d5d6-268">在 **"DNS 设置"** 部分，选择下拉列表图标。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-268">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-Configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="6d5d6-270">选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-270">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="6d5d6-272">从 **添加记录** ： 下拉列表 **中选择** SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-272">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="6d5d6-274">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-274">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="6d5d6-276">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-276">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="6d5d6-277">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-277">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="6d5d6-278">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-278">**Record Type**</span></span>|<span data-ttu-id="6d5d6-279">**子域**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-279">**Sub Domain**</span></span>|<span data-ttu-id="6d5d6-280">**优先级**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-280">**Priority**</span></span>|<span data-ttu-id="6d5d6-281">**权重**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-281">**Weight**</span></span>|<span data-ttu-id="6d5d6-282">**端口**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-282">**Port**</span></span>|<span data-ttu-id="6d5d6-283">**目标**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-283">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6d5d6-284">SRV 记录</span><span class="sxs-lookup"><span data-stu-id="6d5d6-284">SRV Record</span></span>  <br/> |<span data-ttu-id="6d5d6-285">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="6d5d6-285">_sip._tls</span></span>  <br/> |<span data-ttu-id="6d5d6-286">100</span><span class="sxs-lookup"><span data-stu-id="6d5d6-286">100</span></span>  <br/> |<span data-ttu-id="6d5d6-287">1</span><span class="sxs-lookup"><span data-stu-id="6d5d6-287">1</span></span>  <br/> |<span data-ttu-id="6d5d6-288">443</span><span class="sxs-lookup"><span data-stu-id="6d5d6-288">443</span></span>  <br/> |<span data-ttu-id="6d5d6-289">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6d5d6-289">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="6d5d6-290">SRV 记录</span><span class="sxs-lookup"><span data-stu-id="6d5d6-290">SRV Record</span></span>  <br/> |<span data-ttu-id="6d5d6-291">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="6d5d6-291">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="6d5d6-292">100</span><span class="sxs-lookup"><span data-stu-id="6d5d6-292">100</span></span>  <br/> |<span data-ttu-id="6d5d6-293">1</span><span class="sxs-lookup"><span data-stu-id="6d5d6-293">1</span></span>  <br/> |<span data-ttu-id="6d5d6-294">5061</span><span class="sxs-lookup"><span data-stu-id="6d5d6-294">5061</span></span>  <br/> |<span data-ttu-id="6d5d6-295">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6d5d6-295">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-Configure-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="6d5d6-297">选择 **"添加 SRV 记录"。**</span><span class="sxs-lookup"><span data-stu-id="6d5d6-297">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-Configure-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="6d5d6-299">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-299">Add the other SRV record.</span></span>
    
    <span data-ttu-id="6d5d6-300">在新记录的框中，使用表中第二行的值。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-300">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="6d5d6-301">选择 **"更新** "保存更改。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-301">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-Configure-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="6d5d6-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="6d5d6-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
