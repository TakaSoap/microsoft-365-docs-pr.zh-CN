---
title: 在 name.com 处为 Office 365 创建 DNS 记录
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: 了解如何在 name.com for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: f39cf9f241851e555ea23ca7b63453796a5f471b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211651"
---
# <a name="create-dns-records-at-namecom-for-office-365"></a><span data-ttu-id="25820-103">在 name.com 处为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="25820-103">Create DNS records at name.com for Office 365</span></span>

 <span data-ttu-id="25820-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="25820-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="25820-105">如果 DNS 托管提供者是 name.com，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="25820-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="25820-106">在 name.com 添加这些记录后，域将设置为使用 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="25820-106">After you add these records at name.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="25820-107">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="25820-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="25820-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="25820-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="25820-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="25820-111">Add a TXT record for verification</span></span>
<span data-ttu-id="25820-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="25820-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="25820-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="25820-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="25820-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="25820-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="25820-p104">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="25820-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="25820-120">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="25820-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="25820-122">在 "**详细信息**" 列中，选择 "\* \* DNS 记录 \* \*"。</span><span class="sxs-lookup"><span data-stu-id="25820-122">In the **Details** column, select \*\* DNS Records \*\*.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="25820-124">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="25820-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="25820-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="25820-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="25820-126">**类型**</span><span class="sxs-lookup"><span data-stu-id="25820-126">**Type**</span></span> <br/> |<span data-ttu-id="25820-127">**主机**</span><span class="sxs-lookup"><span data-stu-id="25820-127">**Host**</span></span> <br/> |<span data-ttu-id="25820-128">**应答**</span><span class="sxs-lookup"><span data-stu-id="25820-128">**Answer**</span></span> <br/> |<span data-ttu-id="25820-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="25820-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="25820-130">TXT</span><span class="sxs-lookup"><span data-stu-id="25820-130">TXT</span></span>  <br/> |<span data-ttu-id="25820-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="25820-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="25820-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="25820-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="25820-133">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="25820-133">**Note:** This is an example.</span></span> <span data-ttu-id="25820-134">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="25820-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="25820-135">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="25820-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="25820-136">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="25820-136">Use the default value (300).</span></span>  <br/> |
   
    ![Name-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="25820-138">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="25820-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="25820-140">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="25820-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="25820-141">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="25820-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="25820-142">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="25820-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="25820-143">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="25820-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="25820-144">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="25820-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="25820-145">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="25820-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="25820-146">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="25820-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="25820-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="25820-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="25820-150">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="25820-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="25820-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="25820-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="25820-p107">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="25820-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="25820-155">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="25820-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="25820-157">在 "**详细信息**" 列中，选择 " **DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="25820-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="25820-159">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="25820-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="25820-160">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="25820-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="25820-161">**类型**</span><span class="sxs-lookup"><span data-stu-id="25820-161">**Type**</span></span>|<span data-ttu-id="25820-162">**主机**</span><span class="sxs-lookup"><span data-stu-id="25820-162">**Host**</span></span>|<span data-ttu-id="25820-163">**应答**</span><span class="sxs-lookup"><span data-stu-id="25820-163">**Answer**</span></span>|<span data-ttu-id="25820-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="25820-164">**TTL**</span></span>|<span data-ttu-id="25820-165">**优先级**</span><span class="sxs-lookup"><span data-stu-id="25820-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="25820-166">MX</span><span class="sxs-lookup"><span data-stu-id="25820-166">MX</span></span>  <br/> |<span data-ttu-id="25820-167">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="25820-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="25820-168">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="25820-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="25820-169">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="25820-169">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="25820-170">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="25820-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="25820-171">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="25820-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="25820-172">0</span><span class="sxs-lookup"><span data-stu-id="25820-172">0</span></span>  <br/> <span data-ttu-id="25820-173">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="25820-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Name-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="25820-175">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="25820-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="25820-177">如果存在任何其他 MX 记录，请使用以下两步操作删除这些记录：</span><span class="sxs-lookup"><span data-stu-id="25820-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="25820-178">对于每个其他 MX 记录，请在 "**操作**" 列中选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="25820-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="25820-180">若要确认每个删除，请再次选择 "**操作**" 列中的 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="25820-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="25820-182">重复此两步操作，直到删除所有其他 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="25820-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="25820-183">添加 Office 365 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="25820-183">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="25820-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="25820-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="25820-p109">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="25820-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="25820-188">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="25820-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="25820-190">在 "**详细信息**" 列中，选择 " **DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="25820-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="25820-192">添加第一条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="25820-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="25820-193">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="25820-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="25820-194">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="25820-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="25820-195">**类型**</span><span class="sxs-lookup"><span data-stu-id="25820-195">**Type**</span></span>|<span data-ttu-id="25820-196">**主机**</span><span class="sxs-lookup"><span data-stu-id="25820-196">**Host**</span></span>|<span data-ttu-id="25820-197">**应答**</span><span class="sxs-lookup"><span data-stu-id="25820-197">**Answer**</span></span>|<span data-ttu-id="25820-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="25820-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="25820-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="25820-199">CNAME</span></span>  <br/> |<span data-ttu-id="25820-200">自动发现</span><span class="sxs-lookup"><span data-stu-id="25820-200">autodiscover</span></span>  <br/> |<span data-ttu-id="25820-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="25820-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="25820-202">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="25820-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="25820-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="25820-203">CNAME</span></span>  <br/> |<span data-ttu-id="25820-204">sip</span><span class="sxs-lookup"><span data-stu-id="25820-204">sip</span></span>  <br/> |<span data-ttu-id="25820-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="25820-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="25820-206">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="25820-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="25820-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="25820-207">CNAME</span></span>  <br/> |<span data-ttu-id="25820-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="25820-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="25820-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="25820-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="25820-210">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="25820-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="25820-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="25820-211">CNAME</span></span>  <br/> |<span data-ttu-id="25820-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="25820-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="25820-213">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="25820-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="25820-214">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="25820-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="25820-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="25820-215">CNAME</span></span>  <br/> |<span data-ttu-id="25820-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="25820-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="25820-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="25820-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="25820-218">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="25820-218">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="25820-220">选择 "**添加记录**" 以添加第一条记录。</span><span class="sxs-lookup"><span data-stu-id="25820-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="25820-222">添加第二条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="25820-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="25820-223">使用上表中第二行的值，然后选择 "**添加记录**" 以添加第二条记录。</span><span class="sxs-lookup"><span data-stu-id="25820-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="25820-224">按同样的方法，使用表中第 3 到 6 行的值添加其余记录。</span><span class="sxs-lookup"><span data-stu-id="25820-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="25820-225">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="25820-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="25820-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="25820-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="25820-227">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="25820-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="25820-228">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="25820-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="25820-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="25820-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="25820-230">可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="25820-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="25820-p111">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="25820-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="25820-234">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="25820-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="25820-236">在 "**详细信息**" 列中，选择 " **DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="25820-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="25820-238">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="25820-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="25820-239">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="25820-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="25820-240">**类型**</span><span class="sxs-lookup"><span data-stu-id="25820-240">**Type**</span></span>|<span data-ttu-id="25820-241">**主机**</span><span class="sxs-lookup"><span data-stu-id="25820-241">**Host**</span></span>|<span data-ttu-id="25820-242">**应答**</span><span class="sxs-lookup"><span data-stu-id="25820-242">**Answer**</span></span>|<span data-ttu-id="25820-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="25820-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="25820-244">TXT</span><span class="sxs-lookup"><span data-stu-id="25820-244">TXT</span></span>  <br/> |<span data-ttu-id="25820-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="25820-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="25820-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="25820-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="25820-247">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="25820-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="25820-248">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="25820-248">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="25820-250">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="25820-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="25820-252">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="25820-252">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="25820-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="25820-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="25820-p112">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="25820-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="25820-257">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="25820-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="25820-259">在 "**详细信息**" 列中，选择 " **DNS 记录 +**"。</span><span class="sxs-lookup"><span data-stu-id="25820-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="25820-261">添加第一条 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="25820-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="25820-262">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="25820-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="25820-263">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="25820-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="25820-264">**类型**</span><span class="sxs-lookup"><span data-stu-id="25820-264">**Type**</span></span>|<span data-ttu-id="25820-265">**服务**</span><span class="sxs-lookup"><span data-stu-id="25820-265">**Service**</span></span>|<span data-ttu-id="25820-266">**权重**</span><span class="sxs-lookup"><span data-stu-id="25820-266">**Weight**</span></span>|<span data-ttu-id="25820-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="25820-267">**TTL**</span></span>|<span data-ttu-id="25820-268">**优先级**</span><span class="sxs-lookup"><span data-stu-id="25820-268">**Prio**</span></span>|<span data-ttu-id="25820-269">**协议**</span><span class="sxs-lookup"><span data-stu-id="25820-269">**Protocol**</span></span>|<span data-ttu-id="25820-270">**端口**</span><span class="sxs-lookup"><span data-stu-id="25820-270">**Port**</span></span>|<span data-ttu-id="25820-271">**目标**</span><span class="sxs-lookup"><span data-stu-id="25820-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="25820-272">SRV</span><span class="sxs-lookup"><span data-stu-id="25820-272">SRV</span></span>|<span data-ttu-id="25820-273">sip</span><span class="sxs-lookup"><span data-stu-id="25820-273">sip</span></span>|<span data-ttu-id="25820-274">1</span><span class="sxs-lookup"><span data-stu-id="25820-274">1</span></span>|<span data-ttu-id="25820-275">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="25820-275">Use the default value (300).</span></span>|<span data-ttu-id="25820-276">100</span><span class="sxs-lookup"><span data-stu-id="25820-276">100</span></span>|<span data-ttu-id="25820-277">tls</span><span class="sxs-lookup"><span data-stu-id="25820-277">tls</span></span>|<span data-ttu-id="25820-278">443</span><span class="sxs-lookup"><span data-stu-id="25820-278">443</span></span>|<span data-ttu-id="25820-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="25820-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="25820-280">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="25820-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="25820-281">SRV</span><span class="sxs-lookup"><span data-stu-id="25820-281">SRV</span></span>|<span data-ttu-id="25820-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="25820-282">sipfederationtls</span></span>|<span data-ttu-id="25820-283">1</span><span class="sxs-lookup"><span data-stu-id="25820-283">1</span></span>|<span data-ttu-id="25820-284">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="25820-284">Use the default value (300).</span></span>|<span data-ttu-id="25820-285">100</span><span class="sxs-lookup"><span data-stu-id="25820-285">100</span></span>|<span data-ttu-id="25820-286">tcp</span><span class="sxs-lookup"><span data-stu-id="25820-286">tcp</span></span>|<span data-ttu-id="25820-287">5061</span><span class="sxs-lookup"><span data-stu-id="25820-287">5061</span></span>|<span data-ttu-id="25820-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="25820-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="25820-289">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="25820-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="25820-291">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="25820-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="25820-293">添加第二条 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="25820-293">Add the second SRV record:</span></span>

<span data-ttu-id="25820-294">使用上表中下一行的值，然后选择 "**添加记录**" 以添加第二条记录。</span><span class="sxs-lookup"><span data-stu-id="25820-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="25820-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="25820-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
