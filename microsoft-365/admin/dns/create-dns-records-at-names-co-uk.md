---
title: 在 Microsoft Names.co.uk 创建 DNS 记录
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: 了解如何验证域，并设置电子邮件、Skype for Business Online 和 Microsoft Names.co.uk 的其他服务的 DNS 记录。
ms.openlocfilehash: ddd7286d983a0f180c9aefdbf5218eb9765c8669
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910038"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="55a4e-103">在 Microsoft Names.co.uk 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="55a4e-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="55a4e-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="55a4e-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="55a4e-105">如果 Names.co.uk DNS 托管提供商，请按照本文中的步骤验证域，并设置电子邮件、Skype for Business Online 等的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="55a4e-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="55a4e-106">在添加这些记录 Names.co.uk，域将设置为使用 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="55a4e-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="55a4e-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="55a4e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="55a4e-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="55a4e-110">Add a TXT record for verification</span></span>
<span data-ttu-id="55a4e-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="55a4e-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="55a4e-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="55a4e-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="55a4e-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="55a4e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="55a4e-p104">若要开始使用，请使用[此链接](https://account.names.co.uk/dashboard#/)转到 Names.co.uk 上的域页面。系统将提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="55a4e-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="55a4e-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="55a4e-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="55a4e-120">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="55a4e-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="55a4e-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="55a4e-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="55a4e-123">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="55a4e-124"> (如果需要添加行，请选择"添加 **A/CNAME** 记录" (+) .) </span><span class="sxs-lookup"><span data-stu-id="55a4e-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="55a4e-125">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="55a4e-126">**主机名**</span><span class="sxs-lookup"><span data-stu-id="55a4e-126">**Host name**</span></span>|<span data-ttu-id="55a4e-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="55a4e-127">**Type**</span></span>|<span data-ttu-id="55a4e-128">**结果**</span><span class="sxs-lookup"><span data-stu-id="55a4e-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="55a4e-129">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="55a4e-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="55a4e-130">TXT</span><span class="sxs-lookup"><span data-stu-id="55a4e-130">TXT</span></span>  <br/> |<span data-ttu-id="55a4e-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="55a4e-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="55a4e-132">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="55a4e-132">**Note:** This is an example.</span></span> <span data-ttu-id="55a4e-133">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="55a4e-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="55a4e-134">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="55a4e-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="55a4e-136">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="55a4e-136">Select **Save**.</span></span>
    
    <span data-ttu-id="55a4e-137">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="55a4e-139">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="55a4e-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="55a4e-140">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="55a4e-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="55a4e-141">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="55a4e-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="55a4e-142">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="55a4e-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="55a4e-143">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="55a4e-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="55a4e-144">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="55a4e-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="55a4e-145">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="55a4e-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="55a4e-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="55a4e-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="55a4e-149">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="55a4e-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="55a4e-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="55a4e-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="55a4e-p107">若要开始使用，请使用[此链接](https://account.names.co.uk/dashboard#/)转到 Names.co.uk 上的域页面。系统将提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="55a4e-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="55a4e-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="55a4e-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="55a4e-155">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="55a4e-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="55a4e-157">在" **添加/修改 DNS** 区域"页上的" **邮件交换** 记录"部分，在新记录的框内键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="55a4e-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="55a4e-158">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="55a4e-159">**主机名**</span><span class="sxs-lookup"><span data-stu-id="55a4e-159">**Host name**</span></span>|<span data-ttu-id="55a4e-160">**Priority**</span><span class="sxs-lookup"><span data-stu-id="55a4e-160">**Priority**</span></span>|<span data-ttu-id="55a4e-161">**结果**</span><span class="sxs-lookup"><span data-stu-id="55a4e-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="55a4e-162">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="55a4e-163">1</span><span class="sxs-lookup"><span data-stu-id="55a4e-163">1</span></span>  <br/> <span data-ttu-id="55a4e-164">有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="55a4e-164">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="55a4e-165">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="55a4e-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="55a4e-166">> [!NOTE]>从  *\<domain-key\>*  Microsoft 帐户获取你的帐户。</span><span class="sxs-lookup"><span data-stu-id="55a4e-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="55a4e-167">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="55a4e-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="55a4e-169">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="55a4e-169">Select **Save**.</span></span>
    
    <span data-ttu-id="55a4e-170">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="55a4e-172">如果"邮件交换记录"部分列出了任何其他 MX 记录，请通过选择每条记录，然后按键盘上的 **Delete** 键将其删除。 </span><span class="sxs-lookup"><span data-stu-id="55a4e-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="55a4e-174">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="55a4e-174">Select **Save**.</span></span>
    
    <span data-ttu-id="55a4e-175">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="55a4e-177">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="55a4e-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="55a4e-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="55a4e-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="55a4e-p109">若要开始使用，请使用[此链接](https://account.names.co.uk/dashboard#/)转到 Names.co.uk 上的域页面。系统将提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="55a4e-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="55a4e-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="55a4e-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="55a4e-183">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="55a4e-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="55a4e-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="55a4e-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="55a4e-186">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="55a4e-187"> (如果需要添加行，请选择"添加 **A/CNAME** 记录" (+) .) </span><span class="sxs-lookup"><span data-stu-id="55a4e-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="55a4e-188">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="55a4e-189">**主机名**</span><span class="sxs-lookup"><span data-stu-id="55a4e-189">**Host Name**</span></span>|<span data-ttu-id="55a4e-190">**类型**</span><span class="sxs-lookup"><span data-stu-id="55a4e-190">**Type**</span></span>|<span data-ttu-id="55a4e-191">**结果**</span><span class="sxs-lookup"><span data-stu-id="55a4e-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="55a4e-192">自动发现</span><span class="sxs-lookup"><span data-stu-id="55a4e-192">autodiscover</span></span>  <br/> |<span data-ttu-id="55a4e-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="55a4e-193">CNAME</span></span>  <br/> |<span data-ttu-id="55a4e-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="55a4e-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="55a4e-195">sip</span><span class="sxs-lookup"><span data-stu-id="55a4e-195">sip</span></span>  <br/> |<span data-ttu-id="55a4e-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="55a4e-196">CNAME</span></span>  <br/> |<span data-ttu-id="55a4e-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="55a4e-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="55a4e-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="55a4e-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="55a4e-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="55a4e-199">CNAME</span></span>  <br/> |<span data-ttu-id="55a4e-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="55a4e-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="55a4e-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="55a4e-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="55a4e-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="55a4e-202">CNAME</span></span>  <br/> |<span data-ttu-id="55a4e-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="55a4e-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="55a4e-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="55a4e-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="55a4e-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="55a4e-205">CNAME</span></span>  <br/> |<span data-ttu-id="55a4e-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="55a4e-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="55a4e-208">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="55a4e-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-Configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="55a4e-210">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="55a4e-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="55a4e-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="55a4e-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="55a4e-212">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="55a4e-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="55a4e-213">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="55a4e-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="55a4e-214">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="55a4e-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="55a4e-215">相反，将所需的 Microsoft 值添加到当前记录，以便你有一个  *包含这*  两组值的 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="55a4e-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="55a4e-p111">若要开始使用，请使用[此链接](https://account.names.co.uk/dashboard#/)转到 Names.co.uk 上的域页面。系统将提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="55a4e-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="55a4e-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="55a4e-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="55a4e-220">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="55a4e-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="55a4e-222">在"**帐户上的 DNS** 区域"页上的"域名"列中，选择要更新的域的名称。</span><span class="sxs-lookup"><span data-stu-id="55a4e-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="55a4e-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="55a4e-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="55a4e-225">（从下拉列表中选择“**类型**”值。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="55a4e-226"> (如果需要添加行，请选择"添加 **A/CNAME** 记录" (+) .) </span><span class="sxs-lookup"><span data-stu-id="55a4e-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="55a4e-227">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="55a4e-228">**主机名**</span><span class="sxs-lookup"><span data-stu-id="55a4e-228">**Host name**</span></span>|<span data-ttu-id="55a4e-229">**类型**</span><span class="sxs-lookup"><span data-stu-id="55a4e-229">**Type**</span></span>|<span data-ttu-id="55a4e-230">**结果**</span><span class="sxs-lookup"><span data-stu-id="55a4e-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="55a4e-231">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="55a4e-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="55a4e-232">TXT</span><span class="sxs-lookup"><span data-stu-id="55a4e-232">TXT</span></span>  <br/> |<span data-ttu-id="55a4e-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="55a4e-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="55a4e-234">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="55a4e-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="55a4e-236">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="55a4e-236">Select **Save**.</span></span>
    
    <span data-ttu-id="55a4e-237">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="55a4e-239">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="55a4e-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="55a4e-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="55a4e-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="55a4e-p112">若要开始使用，请使用[此链接](https://account.names.co.uk/dashboard#/)转到 Names.co.uk 上的域页面。系统将提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="55a4e-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="55a4e-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="55a4e-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="55a4e-245">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="55a4e-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="55a4e-247">在"**添加/修改 DNS** 区域"页上的"服务记录"部分，在新记录的框内，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="55a4e-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="55a4e-248">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="55a4e-249">**名称**</span><span class="sxs-lookup"><span data-stu-id="55a4e-249">**Name**</span></span>|<span data-ttu-id="55a4e-250">**优先级**</span><span class="sxs-lookup"><span data-stu-id="55a4e-250">**Priority**</span></span>|<span data-ttu-id="55a4e-251">**权重**</span><span class="sxs-lookup"><span data-stu-id="55a4e-251">**Weight**</span></span>|<span data-ttu-id="55a4e-252">**端口**</span><span class="sxs-lookup"><span data-stu-id="55a4e-252">**Port**</span></span>|<span data-ttu-id="55a4e-253">**结果**</span><span class="sxs-lookup"><span data-stu-id="55a4e-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="55a4e-254">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="55a4e-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="55a4e-255">100</span><span class="sxs-lookup"><span data-stu-id="55a4e-255">100</span></span>  <br/> |<span data-ttu-id="55a4e-256">1</span><span class="sxs-lookup"><span data-stu-id="55a4e-256">1</span></span>  <br/> |<span data-ttu-id="55a4e-257">443</span><span class="sxs-lookup"><span data-stu-id="55a4e-257">443</span></span>  <br/> |<span data-ttu-id="55a4e-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="55a4e-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="55a4e-259">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="55a4e-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="55a4e-260">100</span><span class="sxs-lookup"><span data-stu-id="55a4e-260">100</span></span>  <br/> |<span data-ttu-id="55a4e-261">1</span><span class="sxs-lookup"><span data-stu-id="55a4e-261">1</span></span>  <br/> |<span data-ttu-id="55a4e-262">5061</span><span class="sxs-lookup"><span data-stu-id="55a4e-262">5061</span></span>  <br/> |<span data-ttu-id="55a4e-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="55a4e-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="55a4e-265">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="55a4e-265">Select **Save**.</span></span>
    
    <span data-ttu-id="55a4e-266">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="55a4e-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="55a4e-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="55a4e-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
