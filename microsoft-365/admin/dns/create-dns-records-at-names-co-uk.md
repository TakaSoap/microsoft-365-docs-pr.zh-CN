---
title: 在 Names.co.uk 上为 Office 365 创建 DNS 记录
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: 了解如何在 Names.co.uk for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 8f8d76c1aebaa7fec80b264e0a9d2c8fffec9f41
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211663"
---
# <a name="create-dns-records-at-namescouk-for-office-365"></a><span data-ttu-id="89fe6-103">在 Names.co.uk 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="89fe6-103">Create DNS records at Names.co.uk for Office 365</span></span>

 <span data-ttu-id="89fe6-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="89fe6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="89fe6-105">如果 Names.co.uk 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="89fe6-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="89fe6-106">在 Names.co.uk 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="89fe6-106">After you add these records at Names.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="89fe6-107">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="89fe6-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="89fe6-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="89fe6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="89fe6-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="89fe6-111">Add a TXT record for verification</span></span>
<span data-ttu-id="89fe6-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe6-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="89fe6-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="89fe6-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="89fe6-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="89fe6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="89fe6-p104">若要开始使用，请使用[此链接](https://account.names.co.uk/dashboard#/)转到 Names.co.uk 上的域页面。系统将提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="89fe6-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-配置-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="89fe6-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="89fe6-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="89fe6-121">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-121">(You may have to scroll down.)</span></span>
    
    ![NamesUK-配置-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="89fe6-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="89fe6-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="89fe6-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="89fe6-125">（如果需要添加行，请选择 "**添加/CNAME 记录（+）**"。</span><span class="sxs-lookup"><span data-stu-id="89fe6-125">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="89fe6-126">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="89fe6-126">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="89fe6-127">**主机名**</span><span class="sxs-lookup"><span data-stu-id="89fe6-127">**Host name**</span></span>|<span data-ttu-id="89fe6-128">**类型**</span><span class="sxs-lookup"><span data-stu-id="89fe6-128">**Type**</span></span>|<span data-ttu-id="89fe6-129">**结果**</span><span class="sxs-lookup"><span data-stu-id="89fe6-129">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="89fe6-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="89fe6-131">TXT</span><span class="sxs-lookup"><span data-stu-id="89fe6-131">TXT</span></span>  <br/> |<span data-ttu-id="89fe6-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="89fe6-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="89fe6-133">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="89fe6-133">**Note:** This is an example.</span></span> <span data-ttu-id="89fe6-134">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="89fe6-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="89fe6-135">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="89fe6-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-验证-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="89fe6-137">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89fe6-137">Select **Save**.</span></span>
    
    <span data-ttu-id="89fe6-138">（您可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="89fe6-138">(You may have to scroll down.)</span></span>
    
    ![NamesUK-验证-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="89fe6-140">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="89fe6-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="89fe6-141">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="89fe6-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="89fe6-142">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="89fe6-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="89fe6-143">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="89fe6-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="89fe6-144">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="89fe6-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="89fe6-145">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="89fe6-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="89fe6-146">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="89fe6-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="89fe6-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="89fe6-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="89fe6-150">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="89fe6-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="89fe6-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe6-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="89fe6-p107">若要开始使用，请使用[此链接](https://account.names.co.uk/dashboard#/)转到 Names.co.uk 上的域页面。系统将提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="89fe6-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-配置-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="89fe6-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="89fe6-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="89fe6-156">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-156">(You may have to scroll down.)</span></span>
    
    ![NamesUK-配置-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="89fe6-158">在 "**添加/修改 DNS 区域**" 页上的 "**邮件交换记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="89fe6-158">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="89fe6-159">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="89fe6-159">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="89fe6-160">**主机名**</span><span class="sxs-lookup"><span data-stu-id="89fe6-160">**Host name**</span></span>|<span data-ttu-id="89fe6-161">**Priority**</span><span class="sxs-lookup"><span data-stu-id="89fe6-161">**Priority**</span></span>|<span data-ttu-id="89fe6-162">**结果**</span><span class="sxs-lookup"><span data-stu-id="89fe6-162">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="89fe6-163">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="89fe6-163">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="89fe6-164">1</span><span class="sxs-lookup"><span data-stu-id="89fe6-164">1</span></span>  <br/> <span data-ttu-id="89fe6-165">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="89fe6-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="89fe6-166">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="89fe6-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="89fe6-167">> [!NOTE]> 从您的 Office 365 帐户中获取您\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="89fe6-167">> [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="89fe6-168">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="89fe6-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-配置-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="89fe6-170">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89fe6-170">Select **Save**.</span></span>
    
    <span data-ttu-id="89fe6-171">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-171">(You may have to scroll down.)</span></span>
    
    ![NamesUK-配置-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="89fe6-173">如果 "**邮件交换记录**" 部分中列出了任何其他 MX 记录，请通过选择它，然后按键盘上的**delete**键将其删除。</span><span class="sxs-lookup"><span data-stu-id="89fe6-173">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-配置-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="89fe6-175">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89fe6-175">Select **Save**.</span></span>
    
    <span data-ttu-id="89fe6-176">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-176">(You may have to scroll down.)</span></span>
    
    ![NamesUK-配置-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="89fe6-178">添加 Office 365 所需的 6 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="89fe6-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="89fe6-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe6-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="89fe6-p109">若要开始使用，请使用[此链接](https://account.names.co.uk/dashboard#/)转到 Names.co.uk 上的域页面。系统将提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="89fe6-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-配置-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="89fe6-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="89fe6-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="89fe6-184">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-184">(You may have to scroll down.)</span></span>
    
    ![NamesUK-配置-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="89fe6-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="89fe6-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="89fe6-187">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-187">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="89fe6-188">（如果需要添加行，请选择 "**添加/CNAME 记录（+）**"。</span><span class="sxs-lookup"><span data-stu-id="89fe6-188">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="89fe6-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-189">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="89fe6-190">**主机名**</span><span class="sxs-lookup"><span data-stu-id="89fe6-190">**Host Name**</span></span>|<span data-ttu-id="89fe6-191">**类型**</span><span class="sxs-lookup"><span data-stu-id="89fe6-191">**Type**</span></span>|<span data-ttu-id="89fe6-192">**结果**</span><span class="sxs-lookup"><span data-stu-id="89fe6-192">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="89fe6-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="89fe6-193">autodiscover</span></span>  <br/> |<span data-ttu-id="89fe6-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="89fe6-194">CNAME</span></span>  <br/> |<span data-ttu-id="89fe6-195">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="89fe6-195">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="89fe6-196">sip</span><span class="sxs-lookup"><span data-stu-id="89fe6-196">sip</span></span>  <br/> |<span data-ttu-id="89fe6-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="89fe6-197">CNAME</span></span>  <br/> |<span data-ttu-id="89fe6-198">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="89fe6-198">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="89fe6-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="89fe6-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="89fe6-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="89fe6-200">CNAME</span></span>  <br/> |<span data-ttu-id="89fe6-201">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="89fe6-201">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="89fe6-202">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="89fe6-202">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="89fe6-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="89fe6-203">CNAME</span></span>  <br/> |<span data-ttu-id="89fe6-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="89fe6-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="89fe6-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="89fe6-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="89fe6-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="89fe6-206">CNAME</span></span>  <br/> |<span data-ttu-id="89fe6-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="89fe6-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-配置-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="89fe6-209">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89fe6-209">Select **Save**.</span></span>
    
    ![NamesUK-配置-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="89fe6-211">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="89fe6-211">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="89fe6-212"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe6-212"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="89fe6-213">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="89fe6-213">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="89fe6-214">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="89fe6-214">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="89fe6-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="89fe6-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="89fe6-216">可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="89fe6-216">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="89fe6-p111">若要开始使用，请使用[此链接](https://account.names.co.uk/dashboard#/)转到 Names.co.uk 上的域页面。系统将提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="89fe6-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-配置-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="89fe6-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="89fe6-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="89fe6-221">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-221">(You may have to scroll down.)</span></span>
    
    ![NamesUK-配置-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="89fe6-223">在 "**帐户上的 DNS 区域**" 页上的 "**域名**" 列中，选择要更新的域的名称。</span><span class="sxs-lookup"><span data-stu-id="89fe6-223">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-配置-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="89fe6-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="89fe6-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="89fe6-226">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-226">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="89fe6-227">（如果需要添加行，请选择 "**添加/CNAME 记录（+）**"。</span><span class="sxs-lookup"><span data-stu-id="89fe6-227">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="89fe6-228">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="89fe6-228">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="89fe6-229">**主机名**</span><span class="sxs-lookup"><span data-stu-id="89fe6-229">**Host name**</span></span>|<span data-ttu-id="89fe6-230">**类型**</span><span class="sxs-lookup"><span data-stu-id="89fe6-230">**Type**</span></span>|<span data-ttu-id="89fe6-231">**结果**</span><span class="sxs-lookup"><span data-stu-id="89fe6-231">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="89fe6-232">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-232">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="89fe6-233">TXT</span><span class="sxs-lookup"><span data-stu-id="89fe6-233">TXT</span></span>  <br/> |<span data-ttu-id="89fe6-234">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="89fe6-234">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="89fe6-235">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="89fe6-235">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-配置-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="89fe6-237">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89fe6-237">Select **Save**.</span></span>
    
    <span data-ttu-id="89fe6-238">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-238">(You may have to scroll down.)</span></span>
    
    ![NamesUK-配置-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="89fe6-240">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="89fe6-240">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="89fe6-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe6-241"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="89fe6-p112">若要开始使用，请使用[此链接](https://account.names.co.uk/dashboard#/)转到 Names.co.uk 上的域页面。系统将提示你先登录。</span><span class="sxs-lookup"><span data-stu-id="89fe6-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-配置-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="89fe6-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="89fe6-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="89fe6-246">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-246">(You may have to scroll down.)</span></span>
    
    ![NamesUK-配置-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="89fe6-248">在 "**添加/修改 DNS 区域**" 页上的 "**服务记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="89fe6-248">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="89fe6-249">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-249">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="89fe6-250">**名称**</span><span class="sxs-lookup"><span data-stu-id="89fe6-250">**Name**</span></span>|<span data-ttu-id="89fe6-251">**优先级**</span><span class="sxs-lookup"><span data-stu-id="89fe6-251">**Priority**</span></span>|<span data-ttu-id="89fe6-252">**权重**</span><span class="sxs-lookup"><span data-stu-id="89fe6-252">**Weight**</span></span>|<span data-ttu-id="89fe6-253">**端口**</span><span class="sxs-lookup"><span data-stu-id="89fe6-253">**Port**</span></span>|<span data-ttu-id="89fe6-254">**结果**</span><span class="sxs-lookup"><span data-stu-id="89fe6-254">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="89fe6-255">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="89fe6-255">_sip._tls</span></span>  <br/> |<span data-ttu-id="89fe6-256">100</span><span class="sxs-lookup"><span data-stu-id="89fe6-256">100</span></span>  <br/> |<span data-ttu-id="89fe6-257">1</span><span class="sxs-lookup"><span data-stu-id="89fe6-257">1</span></span>  <br/> |<span data-ttu-id="89fe6-258">443</span><span class="sxs-lookup"><span data-stu-id="89fe6-258">443</span></span>  <br/> |<span data-ttu-id="89fe6-259">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="89fe6-259">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="89fe6-260">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="89fe6-260">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="89fe6-261">100</span><span class="sxs-lookup"><span data-stu-id="89fe6-261">100</span></span>  <br/> |<span data-ttu-id="89fe6-262">1</span><span class="sxs-lookup"><span data-stu-id="89fe6-262">1</span></span>  <br/> |<span data-ttu-id="89fe6-263">5061</span><span class="sxs-lookup"><span data-stu-id="89fe6-263">5061</span></span>  <br/> |<span data-ttu-id="89fe6-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="89fe6-264">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-配置-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="89fe6-266">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="89fe6-266">Select **Save**.</span></span>
    
    <span data-ttu-id="89fe6-267">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="89fe6-267">(You may have to scroll down.)</span></span>
    
    ![NamesUK-配置-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="89fe6-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="89fe6-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
