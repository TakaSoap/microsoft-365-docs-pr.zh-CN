---
title: 在 name.com 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: 了解如何验证您的域，并在 name.com for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 646f486e73705f4b1e1bab63866fc7601d34cf92
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400396"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="6d6bd-103">在 name.com 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="6d6bd-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="6d6bd-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6d6bd-105">如果 DNS 托管提供者是 name.com，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="6d6bd-106">在 name.com 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
> <span data-ttu-id="6d6bd-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6d6bd-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="6d6bd-110">Add a TXT record for verification</span></span>
<span data-ttu-id="6d6bd-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6d6bd-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6d6bd-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d6bd-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="6d6bd-p104">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="6d6bd-119">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-119">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="6d6bd-121">在 "**详细信息**" 列中，选择 " **DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-121">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="6d6bd-123">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-123">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="6d6bd-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6d6bd-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6d6bd-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-125">**Type**</span></span> <br/> |<span data-ttu-id="6d6bd-126">**主机**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-126">**Host**</span></span> <br/> |<span data-ttu-id="6d6bd-127">**应答**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-127">**Answer**</span></span> <br/> |<span data-ttu-id="6d6bd-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="6d6bd-129">TXT</span><span class="sxs-lookup"><span data-stu-id="6d6bd-129">TXT</span></span>  <br/> |<span data-ttu-id="6d6bd-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="6d6bd-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6d6bd-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6d6bd-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6d6bd-132">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-132">**Note:** This is an example.</span></span> <span data-ttu-id="6d6bd-133">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="6d6bd-134">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="6d6bd-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="6d6bd-135">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="6d6bd-135">Use the default value (300).</span></span>  <br/> |
   
    ![Name-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="6d6bd-137">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-137">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="6d6bd-139">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6d6bd-140">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="6d6bd-141">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6d6bd-142">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6d6bd-143">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="6d6bd-144">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="6d6bd-145">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="6d6bd-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="6d6bd-149">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="6d6bd-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="6d6bd-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6d6bd-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="6d6bd-p107">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="6d6bd-154">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-154">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="6d6bd-156">在 "**详细信息**" 列中，选择 " **DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-156">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="6d6bd-158">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-158">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="6d6bd-159">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6d6bd-159">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6d6bd-160">**类型**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-160">**Type**</span></span>|<span data-ttu-id="6d6bd-161">**主机**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-161">**Host**</span></span>|<span data-ttu-id="6d6bd-162">**应答**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-162">**Answer**</span></span>|<span data-ttu-id="6d6bd-163">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-163">**TTL**</span></span>|<span data-ttu-id="6d6bd-164">**优先级**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-164">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6d6bd-165">MX</span><span class="sxs-lookup"><span data-stu-id="6d6bd-165">MX</span></span>  <br/> |<span data-ttu-id="6d6bd-166">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="6d6bd-166">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="6d6bd-167">*\<domain-key\>*。 mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6d6bd-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="6d6bd-168">\**注意：\*\*\*\<domain-key\>* 从你的 Microsoft 帐户获取你的。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="6d6bd-169">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="6d6bd-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="6d6bd-170">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="6d6bd-170">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="6d6bd-171">0</span><span class="sxs-lookup"><span data-stu-id="6d6bd-171">0</span></span>  <br/> <span data-ttu-id="6d6bd-172">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="6d6bd-172">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Name-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="6d6bd-174">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-174">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="6d6bd-176">如果存在任何其他 MX 记录，请使用以下两步操作删除这些记录：</span><span class="sxs-lookup"><span data-stu-id="6d6bd-176">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="6d6bd-177">对于每个其他 MX 记录，请在 "**操作**" 列中选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-177">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="6d6bd-179">若要确认每个删除，请再次选择 "**操作**" 列中的 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-179">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="6d6bd-181">重复此两步操作，直到删除所有其他 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-181">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="6d6bd-182">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="6d6bd-182">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="6d6bd-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6d6bd-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="6d6bd-p109">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="6d6bd-187">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-187">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="6d6bd-189">在 "**详细信息**" 列中，选择 " **DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-189">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="6d6bd-191">添加第一条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-191">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="6d6bd-192">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-192">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="6d6bd-193">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="6d6bd-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6d6bd-194">**类型**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-194">**Type**</span></span>|<span data-ttu-id="6d6bd-195">**主机**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-195">**Host**</span></span>|<span data-ttu-id="6d6bd-196">**应答**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-196">**Answer**</span></span>|<span data-ttu-id="6d6bd-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-197">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6d6bd-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="6d6bd-198">CNAME</span></span>  <br/> |<span data-ttu-id="6d6bd-199">自动发现</span><span class="sxs-lookup"><span data-stu-id="6d6bd-199">autodiscover</span></span>  <br/> |<span data-ttu-id="6d6bd-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6d6bd-200">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="6d6bd-201">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-201">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="6d6bd-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="6d6bd-202">CNAME</span></span>  <br/> |<span data-ttu-id="6d6bd-203">sip</span><span class="sxs-lookup"><span data-stu-id="6d6bd-203">sip</span></span>  <br/> |<span data-ttu-id="6d6bd-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6d6bd-204">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="6d6bd-205">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-205">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="6d6bd-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="6d6bd-206">CNAME</span></span>  <br/> |<span data-ttu-id="6d6bd-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6d6bd-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6d6bd-208">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6d6bd-208">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="6d6bd-209">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-209">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="6d6bd-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="6d6bd-210">CNAME</span></span>  <br/> |<span data-ttu-id="6d6bd-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6d6bd-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6d6bd-212">EnterpriseRegistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6d6bd-212">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="6d6bd-213">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-213">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="6d6bd-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="6d6bd-214">CNAME</span></span>  <br/> |<span data-ttu-id="6d6bd-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6d6bd-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6d6bd-216">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6d6bd-216">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="6d6bd-217">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-217">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="6d6bd-219">选择 "**添加记录**" 以添加第一条记录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-219">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="6d6bd-221">添加第二条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-221">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="6d6bd-222">使用上表中第二行的值，然后选择 "**添加记录**" 以添加第二条记录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-222">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="6d6bd-223">按同样的方法，使用表中第 3 到 6 行的值添加其余记录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-223">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6d6bd-224">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="6d6bd-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6d6bd-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6d6bd-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d6bd-226">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6d6bd-227">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6d6bd-228">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="6d6bd-229">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="6d6bd-p111">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="6d6bd-233">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-233">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="6d6bd-235">在 "**详细信息**" 列中，选择 " **DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-235">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="6d6bd-237">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-237">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="6d6bd-238">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="6d6bd-238">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6d6bd-239">**类型**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-239">**Type**</span></span>|<span data-ttu-id="6d6bd-240">**主机**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-240">**Host**</span></span>|<span data-ttu-id="6d6bd-241">**应答**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-241">**Answer**</span></span>|<span data-ttu-id="6d6bd-242">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-242">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6d6bd-243">TXT</span><span class="sxs-lookup"><span data-stu-id="6d6bd-243">TXT</span></span>  <br/> |<span data-ttu-id="6d6bd-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="6d6bd-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6d6bd-245">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6d6bd-245">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6d6bd-246">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-246">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="6d6bd-247">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="6d6bd-247">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="6d6bd-249">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-249">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="6d6bd-251">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="6d6bd-251">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="6d6bd-252"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6d6bd-252"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="6d6bd-p112">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="6d6bd-256">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-256">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="6d6bd-258">在 "**详细信息**" 列中，选择 " **DNS 记录 +**"。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-258">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="6d6bd-260">添加第一条 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="6d6bd-260">Add the first SRV record:</span></span>
    
    <span data-ttu-id="6d6bd-261">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-261">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="6d6bd-262">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="6d6bd-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6d6bd-263">**类型**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-263">**Type**</span></span>|<span data-ttu-id="6d6bd-264">**服务**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-264">**Service**</span></span>|<span data-ttu-id="6d6bd-265">**权重**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-265">**Weight**</span></span>|<span data-ttu-id="6d6bd-266">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-266">**TTL**</span></span>|<span data-ttu-id="6d6bd-267">**优先级**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-267">**Prio**</span></span>|<span data-ttu-id="6d6bd-268">**协议**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-268">**Protocol**</span></span>|<span data-ttu-id="6d6bd-269">**端口**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-269">**Port**</span></span>|<span data-ttu-id="6d6bd-270">**目标**</span><span class="sxs-lookup"><span data-stu-id="6d6bd-270">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6d6bd-271">SRV</span><span class="sxs-lookup"><span data-stu-id="6d6bd-271">SRV</span></span>|<span data-ttu-id="6d6bd-272">sip</span><span class="sxs-lookup"><span data-stu-id="6d6bd-272">sip</span></span>|<span data-ttu-id="6d6bd-273">1 </span><span class="sxs-lookup"><span data-stu-id="6d6bd-273">1</span></span>|<span data-ttu-id="6d6bd-274">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-274">Use the default value (300).</span></span>|<span data-ttu-id="6d6bd-275">100</span><span class="sxs-lookup"><span data-stu-id="6d6bd-275">100</span></span>|<span data-ttu-id="6d6bd-276">tls</span><span class="sxs-lookup"><span data-stu-id="6d6bd-276">tls</span></span>|<span data-ttu-id="6d6bd-277">443</span><span class="sxs-lookup"><span data-stu-id="6d6bd-277">443</span></span>|<span data-ttu-id="6d6bd-278">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6d6bd-278">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="6d6bd-279">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="6d6bd-280">SRV</span><span class="sxs-lookup"><span data-stu-id="6d6bd-280">SRV</span></span>|<span data-ttu-id="6d6bd-281">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="6d6bd-281">sipfederationtls</span></span>|<span data-ttu-id="6d6bd-282">1 </span><span class="sxs-lookup"><span data-stu-id="6d6bd-282">1</span></span>|<span data-ttu-id="6d6bd-283">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-283">Use the default value (300).</span></span>|<span data-ttu-id="6d6bd-284">100</span><span class="sxs-lookup"><span data-stu-id="6d6bd-284">100</span></span>|<span data-ttu-id="6d6bd-285">tcp</span><span class="sxs-lookup"><span data-stu-id="6d6bd-285">tcp</span></span>|<span data-ttu-id="6d6bd-286">5061</span><span class="sxs-lookup"><span data-stu-id="6d6bd-286">5061</span></span>|<span data-ttu-id="6d6bd-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6d6bd-287">sipfed.online.lync.com</span></span> <br><span data-ttu-id="6d6bd-288">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-288">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="6d6bd-290">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-290">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="6d6bd-292">添加第二条 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="6d6bd-292">Add the second SRV record:</span></span>

<span data-ttu-id="6d6bd-293">使用上表中下一行的值，然后选择 "**添加记录**" 以添加第二条记录。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-293">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="6d6bd-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="6d6bd-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
