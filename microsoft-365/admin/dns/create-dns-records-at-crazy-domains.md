---
title: 在适用于 Office 365 的古怪域中创建 DNS 记录
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: 了解如何验证您的域并为 Office 365 的电子邮件、Skype for Business Online 和古怪域中的其他服务设置 DNS 记录。
ms.openlocfilehash: 157c33a52403efbefe673bf11465de525ffb4f33
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351153"
---
# <a name="create-dns-records-at-crazy-domains-for-office-365"></a><span data-ttu-id="a3b59-103">在适用于 Office 365 的古怪域中创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="a3b59-103">Create DNS records at Crazy Domains for Office 365</span></span>

 <span data-ttu-id="a3b59-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="a3b59-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a3b59-105">如果古怪域是 DNS 托管提供商，请按照本文中的步骤验证您的域，并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="a3b59-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a3b59-106">在古怪域中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="a3b59-106">After you add these records at Crazy Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="a3b59-107">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="a3b59-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3b59-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a3b59-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a3b59-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="a3b59-111">Add a TXT record for verification</span></span>
<span data-ttu-id="a3b59-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a3b59-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a3b59-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="a3b59-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3b59-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="a3b59-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a3b59-p104">要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="a3b59-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-配置-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="a3b59-120">在 "**我的帐户**" 部分，选择 "**域**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-配置-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="a3b59-122">在 "**域名**" 页上的 "**域**" 部分，选择要更新的域的名称。</span><span class="sxs-lookup"><span data-stu-id="a3b59-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-配置-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="a3b59-124">在 " **DNS 设置**" 部分中，选择下拉列表图标。</span><span class="sxs-lookup"><span data-stu-id="a3b59-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-配置-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="a3b59-126">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-126">Select **Add Record**.</span></span>
    
    ![CrazyDomains-配置-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="a3b59-128">从" **添加记录**"下拉列表中选择" **TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-验证-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="a3b59-130">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a3b59-130">Select **Add**.</span></span>
    
    ![CrazyDomains-验证-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="a3b59-132">在新记录的框中，键入或复制粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a3b59-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a3b59-133">**子域**</span><span class="sxs-lookup"><span data-stu-id="a3b59-133">**Sub Domain**</span></span>|<span data-ttu-id="a3b59-134">**文本记录**</span><span class="sxs-lookup"><span data-stu-id="a3b59-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a3b59-135">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="a3b59-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a3b59-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a3b59-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a3b59-137">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="a3b59-137">**Note:** This is an example.</span></span> <span data-ttu-id="a3b59-138">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="a3b59-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="a3b59-139">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="a3b59-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-验证-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="a3b59-141">选择“更新”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3b59-141">Select **Update**.</span></span>
    
    ![CrazyDomains-验证-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="a3b59-143">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="a3b59-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a3b59-144">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="a3b59-144">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="a3b59-145">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="a3b59-145">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a3b59-146">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="a3b59-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a3b59-147">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="a3b59-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a3b59-148">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="a3b59-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a3b59-149">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="a3b59-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a3b59-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a3b59-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="a3b59-153">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="a3b59-153">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="a3b59-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a3b59-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a3b59-p107">要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="a3b59-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-配置-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="a3b59-158">在 "**我的帐户**" 部分，选择 "**域**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-配置-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="a3b59-160">在 "**域名**" 页上的 "**域**" 部分，选择要更新的域的名称。</span><span class="sxs-lookup"><span data-stu-id="a3b59-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-配置-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="a3b59-162">在 " **DNS 设置**" 部分中，选择下拉列表图标。</span><span class="sxs-lookup"><span data-stu-id="a3b59-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-配置-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="a3b59-164">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-164">Select **Add Record**.</span></span>
    
    ![CrazyDomains-配置-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="a3b59-166">从 "**添加记录：** " 下拉列表中选择 " **MX 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-配置-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="a3b59-168">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a3b59-168">Select **Add**.</span></span>
    
    ![CrazyDomains-配置-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="a3b59-170">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a3b59-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a3b59-171">（从下拉列表中选择 "**优先级**" 值。）</span><span class="sxs-lookup"><span data-stu-id="a3b59-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="a3b59-172">**区域邮件**</span><span class="sxs-lookup"><span data-stu-id="a3b59-172">**Mail For Zone**</span></span>|<span data-ttu-id="a3b59-173">**优先级**</span><span class="sxs-lookup"><span data-stu-id="a3b59-173">**Priority**</span></span>|<span data-ttu-id="a3b59-174">**分配给服务器**</span><span class="sxs-lookup"><span data-stu-id="a3b59-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a3b59-175">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="a3b59-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a3b59-176">1</span><span class="sxs-lookup"><span data-stu-id="a3b59-176">1</span></span>  <br/> <span data-ttu-id="a3b59-177">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a3b59-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="a3b59-178">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a3b59-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a3b59-179">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="a3b59-179">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="a3b59-180">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="a3b59-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-配置-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="a3b59-182">选择“更新”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3b59-182">Select **Update**.</span></span>
    
    ![CrazyDomains-配置-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="a3b59-184">如果 " **Mx 记录**" 部分中列出了任何其他 MX 记录，请为其中一个记录选择 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-配置-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="a3b59-186">选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-186">Select **Delete**.</span></span>
    
    ![CrazyDomains-配置-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="a3b59-188">选择 "**更新**" 以确认删除。</span><span class="sxs-lookup"><span data-stu-id="a3b59-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-配置-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="a3b59-190">使用相同的过程删除列表中的任何其他 MX 记录，只有在此过程之前添加的任何 MX 记录保持不变。</span><span class="sxs-lookup"><span data-stu-id="a3b59-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="a3b59-191">添加 Office 365 所需的 6 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="a3b59-191">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="a3b59-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a3b59-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a3b59-p109">要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="a3b59-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-配置-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="a3b59-196">在 "**我的帐户**" 部分，选择 "**域**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-配置-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="a3b59-198">在 "**域名**" 页上的 "**域**" 部分，选择要更新的域的名称。</span><span class="sxs-lookup"><span data-stu-id="a3b59-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-配置-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="a3b59-200">在 " **DNS 设置**" 部分中，选择下拉列表图标。</span><span class="sxs-lookup"><span data-stu-id="a3b59-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-配置-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="a3b59-202">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-202">Select **Add Record**.</span></span>
    
    ![CrazyDomains-配置-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="a3b59-204">从 "**添加记录：** " 下拉列表中选择 " **CNAME 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-配置-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="a3b59-206">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a3b59-206">Select **Add**.</span></span>
    
    ![CrazyDomains-配置-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="a3b59-208">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="a3b59-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="a3b59-209">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="a3b59-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="a3b59-210">**子域**</span><span class="sxs-lookup"><span data-stu-id="a3b59-210">**Sub Domain**</span></span>|<span data-ttu-id="a3b59-211">**的别名**</span><span class="sxs-lookup"><span data-stu-id="a3b59-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a3b59-212">自动发现</span><span class="sxs-lookup"><span data-stu-id="a3b59-212">autodiscover</span></span>  <br/> |<span data-ttu-id="a3b59-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a3b59-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a3b59-214">sip</span><span class="sxs-lookup"><span data-stu-id="a3b59-214">sip</span></span>  <br/> |<span data-ttu-id="a3b59-215">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a3b59-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a3b59-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a3b59-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a3b59-217">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a3b59-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a3b59-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a3b59-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a3b59-219">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a3b59-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="a3b59-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a3b59-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a3b59-221">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a3b59-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-配置-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="a3b59-223">选择 "**添加 CNAME 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-223">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-配置-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="a3b59-225">添加第二条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="a3b59-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="a3b59-226">在新记录的框中，使用表中下一行的值，然后再次选择 "**添加 CNAME 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="a3b59-227">重复该过程，直到创建完全部 6 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="a3b59-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="a3b59-228">选择 "**更新**" 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a3b59-228">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-配置-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a3b59-230">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="a3b59-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a3b59-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a3b59-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3b59-232">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="a3b59-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a3b59-233">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="a3b59-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a3b59-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3b59-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="a3b59-235">可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="a3b59-235">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a3b59-p111">要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="a3b59-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-配置-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="a3b59-239">在 "**我的帐户**" 部分，选择 "**域**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-配置-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="a3b59-241">在 "**域名**" 页上的 "**域**" 部分，选择要更新的域的名称。</span><span class="sxs-lookup"><span data-stu-id="a3b59-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-配置-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="a3b59-243">在 " **DNS 设置**" 部分中，选择下拉列表图标。</span><span class="sxs-lookup"><span data-stu-id="a3b59-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-配置-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="a3b59-245">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-245">Select **Add Record**.</span></span>
    
    ![CrazyDomains-配置-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="a3b59-247">从 "**添加记录：** " 下拉列表中选择 " **TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-配置-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="a3b59-249">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a3b59-249">Select **Add**.</span></span>
    
    ![CrazyDomains-配置-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="a3b59-251">在新记录的框中，键入或粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a3b59-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="a3b59-252">**子域**</span><span class="sxs-lookup"><span data-stu-id="a3b59-252">**Sub Domain**</span></span>|<span data-ttu-id="a3b59-253">**文本记录**</span><span class="sxs-lookup"><span data-stu-id="a3b59-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a3b59-254">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="a3b59-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="a3b59-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a3b59-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a3b59-256">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="a3b59-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-配置-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="a3b59-258">选择“更新”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3b59-258">Select **Update**.</span></span>
    
    ![CrazyDomains-配置-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="a3b59-260">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="a3b59-260">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="a3b59-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a3b59-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="a3b59-p112">要开始，请使用[此链接](https://manage.crazydomains.com/members/domains/)转到你在 Crazy Domains 上的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="a3b59-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-配置-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="a3b59-265">在 "**我的帐户**" 部分，选择 "**域**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-配置-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="a3b59-267">在 "**域名**" 页上的 "**域**" 部分，选择要更新的域的名称。</span><span class="sxs-lookup"><span data-stu-id="a3b59-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-配置-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="a3b59-269">在 " **DNS 设置**" 部分中，选择下拉列表图标。</span><span class="sxs-lookup"><span data-stu-id="a3b59-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-配置-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="a3b59-271">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-271">Select **Add Record**.</span></span>
    
    ![CrazyDomains-配置-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="a3b59-273">从 "**添加记录：** " 下拉列表中选择 " **SRV 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-配置-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="a3b59-275">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="a3b59-275">Select **Add**.</span></span>
    
    ![CrazyDomains-配置-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="a3b59-277">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="a3b59-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="a3b59-278">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="a3b59-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="a3b59-279">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="a3b59-279">**Record Type**</span></span>|<span data-ttu-id="a3b59-280">**子域**</span><span class="sxs-lookup"><span data-stu-id="a3b59-280">**Sub Domain**</span></span>|<span data-ttu-id="a3b59-281">**优先级**</span><span class="sxs-lookup"><span data-stu-id="a3b59-281">**Priority**</span></span>|<span data-ttu-id="a3b59-282">**权重**</span><span class="sxs-lookup"><span data-stu-id="a3b59-282">**Weight**</span></span>|<span data-ttu-id="a3b59-283">**端口**</span><span class="sxs-lookup"><span data-stu-id="a3b59-283">**Port**</span></span>|<span data-ttu-id="a3b59-284">**目标**</span><span class="sxs-lookup"><span data-stu-id="a3b59-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a3b59-285">SRV 记录</span><span class="sxs-lookup"><span data-stu-id="a3b59-285">SRV Record</span></span>  <br/> |<span data-ttu-id="a3b59-286">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="a3b59-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="a3b59-287">100</span><span class="sxs-lookup"><span data-stu-id="a3b59-287">100</span></span>  <br/> |<span data-ttu-id="a3b59-288">1</span><span class="sxs-lookup"><span data-stu-id="a3b59-288">1</span></span>  <br/> |<span data-ttu-id="a3b59-289">443</span><span class="sxs-lookup"><span data-stu-id="a3b59-289">443</span></span>  <br/> |<span data-ttu-id="a3b59-290">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a3b59-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a3b59-291">SRV 记录</span><span class="sxs-lookup"><span data-stu-id="a3b59-291">SRV Record</span></span>  <br/> |<span data-ttu-id="a3b59-292">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="a3b59-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="a3b59-293">100</span><span class="sxs-lookup"><span data-stu-id="a3b59-293">100</span></span>  <br/> |<span data-ttu-id="a3b59-294">1</span><span class="sxs-lookup"><span data-stu-id="a3b59-294">1</span></span>  <br/> |<span data-ttu-id="a3b59-295">5061</span><span class="sxs-lookup"><span data-stu-id="a3b59-295">5061</span></span>  <br/> |<span data-ttu-id="a3b59-296">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a3b59-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-配置-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="a3b59-298">选择 "**添加 SRV 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a3b59-298">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-配置-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="a3b59-300">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="a3b59-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="a3b59-301">在新记录的框中，使用表中第二行的值。</span><span class="sxs-lookup"><span data-stu-id="a3b59-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="a3b59-302">选择 "**更新**" 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a3b59-302">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-配置-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="a3b59-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a3b59-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
