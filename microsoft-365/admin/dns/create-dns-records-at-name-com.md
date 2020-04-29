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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: 了解如何验证您的域，并在 name.com for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 9183d27641ee22d9e49be2ca04832ab68bc20ace
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919732"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="61aee-103">在 name.com 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="61aee-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="61aee-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="61aee-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="61aee-105">如果 DNS 托管提供者是 name.com，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="61aee-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="61aee-106">在 name.com 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="61aee-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="61aee-107">若要了解如何与 Microsoft 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="61aee-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="61aee-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="61aee-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="61aee-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="61aee-111">Add a TXT record for verification</span></span>
<span data-ttu-id="61aee-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="61aee-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="61aee-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="61aee-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61aee-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="61aee-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="61aee-p104">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="61aee-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="61aee-120">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="61aee-120">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="61aee-122">在 "**详细信息**" 列中，选择 " **DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="61aee-122">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="61aee-124">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="61aee-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="61aee-125">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="61aee-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="61aee-126">**类型**</span><span class="sxs-lookup"><span data-stu-id="61aee-126">**Type**</span></span> <br/> |<span data-ttu-id="61aee-127">**主机**</span><span class="sxs-lookup"><span data-stu-id="61aee-127">**Host**</span></span> <br/> |<span data-ttu-id="61aee-128">**应答**</span><span class="sxs-lookup"><span data-stu-id="61aee-128">**Answer**</span></span> <br/> |<span data-ttu-id="61aee-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="61aee-129">**TTL**</span></span> <br/> |
    |<span data-ttu-id="61aee-130">TXT</span><span class="sxs-lookup"><span data-stu-id="61aee-130">TXT</span></span>  <br/> |<span data-ttu-id="61aee-131">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="61aee-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="61aee-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="61aee-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="61aee-133">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="61aee-133">**Note:** This is an example.</span></span> <span data-ttu-id="61aee-134">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="61aee-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="61aee-135">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="61aee-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="61aee-136">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="61aee-136">Use the default value (300).</span></span>  <br/> |
   
    ![Name-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="61aee-138">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="61aee-138">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="61aee-140">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="61aee-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="61aee-141">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="61aee-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="61aee-142">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="61aee-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="61aee-143">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="61aee-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="61aee-144">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="61aee-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="61aee-145">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="61aee-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="61aee-146">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="61aee-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="61aee-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="61aee-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="61aee-150">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="61aee-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="61aee-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="61aee-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="61aee-p107">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="61aee-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="61aee-155">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="61aee-155">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="61aee-157">在 "**详细信息**" 列中，选择 " **DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="61aee-157">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="61aee-159">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="61aee-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="61aee-160">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="61aee-160">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="61aee-161">**类型**</span><span class="sxs-lookup"><span data-stu-id="61aee-161">**Type**</span></span>|<span data-ttu-id="61aee-162">**主机**</span><span class="sxs-lookup"><span data-stu-id="61aee-162">**Host**</span></span>|<span data-ttu-id="61aee-163">**应答**</span><span class="sxs-lookup"><span data-stu-id="61aee-163">**Answer**</span></span>|<span data-ttu-id="61aee-164">**TTL**</span><span class="sxs-lookup"><span data-stu-id="61aee-164">**TTL**</span></span>|<span data-ttu-id="61aee-165">**优先级**</span><span class="sxs-lookup"><span data-stu-id="61aee-165">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="61aee-166">MX</span><span class="sxs-lookup"><span data-stu-id="61aee-166">MX</span></span>  <br/> |<span data-ttu-id="61aee-167">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="61aee-167">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="61aee-168">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="61aee-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="61aee-169">**注意：** 从你的 Microsoft 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="61aee-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="61aee-170">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="61aee-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="61aee-171">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="61aee-171">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="61aee-172">0</span><span class="sxs-lookup"><span data-stu-id="61aee-172">0</span></span>  <br/> <span data-ttu-id="61aee-173">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="61aee-173">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
   ![Name-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="61aee-175">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="61aee-175">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="61aee-177">如果存在任何其他 MX 记录，请使用以下两步操作删除这些记录：</span><span class="sxs-lookup"><span data-stu-id="61aee-177">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="61aee-178">对于每个其他 MX 记录，请在 "**操作**" 列中选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="61aee-178">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="61aee-180">若要确认每个删除，请再次选择 "**操作**" 列中的 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="61aee-180">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="61aee-182">重复此两步操作，直到删除所有其他 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="61aee-182">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="61aee-183">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="61aee-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="61aee-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="61aee-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="61aee-p109">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="61aee-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="61aee-188">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="61aee-188">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="61aee-190">在 "**详细信息**" 列中，选择 " **DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="61aee-190">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="61aee-192">添加第一条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="61aee-192">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="61aee-193">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="61aee-193">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="61aee-194">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="61aee-194">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="61aee-195">**类型**</span><span class="sxs-lookup"><span data-stu-id="61aee-195">**Type**</span></span>|<span data-ttu-id="61aee-196">**主机**</span><span class="sxs-lookup"><span data-stu-id="61aee-196">**Host**</span></span>|<span data-ttu-id="61aee-197">**应答**</span><span class="sxs-lookup"><span data-stu-id="61aee-197">**Answer**</span></span>|<span data-ttu-id="61aee-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="61aee-198">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="61aee-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="61aee-199">CNAME</span></span>  <br/> |<span data-ttu-id="61aee-200">自动发现</span><span class="sxs-lookup"><span data-stu-id="61aee-200">autodiscover</span></span>  <br/> |<span data-ttu-id="61aee-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="61aee-201">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="61aee-202">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="61aee-202">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="61aee-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="61aee-203">CNAME</span></span>  <br/> |<span data-ttu-id="61aee-204">sip</span><span class="sxs-lookup"><span data-stu-id="61aee-204">sip</span></span>  <br/> |<span data-ttu-id="61aee-205">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="61aee-205">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="61aee-206">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="61aee-206">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="61aee-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="61aee-207">CNAME</span></span>  <br/> |<span data-ttu-id="61aee-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="61aee-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="61aee-209">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="61aee-209">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="61aee-210">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="61aee-210">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="61aee-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="61aee-211">CNAME</span></span>  <br/> |<span data-ttu-id="61aee-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="61aee-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="61aee-213">EnterpriseRegistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="61aee-213">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="61aee-214">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="61aee-214">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="61aee-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="61aee-215">CNAME</span></span>  <br/> |<span data-ttu-id="61aee-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="61aee-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="61aee-217">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="61aee-217">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="61aee-218">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="61aee-218">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="61aee-220">选择 "**添加记录**" 以添加第一条记录。</span><span class="sxs-lookup"><span data-stu-id="61aee-220">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="61aee-222">添加第二条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="61aee-222">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="61aee-223">使用上表中第二行的值，然后选择 "**添加记录**" 以添加第二条记录。</span><span class="sxs-lookup"><span data-stu-id="61aee-223">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="61aee-224">按同样的方法，使用表中第 3 到 6 行的值添加其余记录。</span><span class="sxs-lookup"><span data-stu-id="61aee-224">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="61aee-225">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="61aee-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="61aee-226"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="61aee-226"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="61aee-227">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="61aee-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="61aee-228">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="61aee-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="61aee-229">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="61aee-229">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="61aee-230">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="61aee-230">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="61aee-p111">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="61aee-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="61aee-234">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="61aee-234">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="61aee-236">在 "**详细信息**" 列中，选择 " **DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="61aee-236">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="61aee-238">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="61aee-238">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="61aee-239">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="61aee-239">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="61aee-240">**类型**</span><span class="sxs-lookup"><span data-stu-id="61aee-240">**Type**</span></span>|<span data-ttu-id="61aee-241">**主机**</span><span class="sxs-lookup"><span data-stu-id="61aee-241">**Host**</span></span>|<span data-ttu-id="61aee-242">**应答**</span><span class="sxs-lookup"><span data-stu-id="61aee-242">**Answer**</span></span>|<span data-ttu-id="61aee-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="61aee-243">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="61aee-244">TXT</span><span class="sxs-lookup"><span data-stu-id="61aee-244">TXT</span></span>  <br/> |<span data-ttu-id="61aee-245">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="61aee-245">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="61aee-246">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="61aee-246">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="61aee-247">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="61aee-247">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="61aee-248">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="61aee-248">Use the default value (300).</span></span>  <br/> |
   
   ![Name-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="61aee-250">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="61aee-250">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="61aee-252">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="61aee-252">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="61aee-253"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="61aee-253"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="61aee-p112">若要开始，请使用[此链接](https://www.name.com/account/domain)转到 name.com 上你的域页面。系统将会提示你首先登录。</span><span class="sxs-lookup"><span data-stu-id="61aee-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="61aee-257">在 **"我的域**" 下，选择要修改的域的名称。</span><span class="sxs-lookup"><span data-stu-id="61aee-257">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="61aee-259">在 "**详细信息**" 列中，选择 " **DNS 记录 +**"。</span><span class="sxs-lookup"><span data-stu-id="61aee-259">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="61aee-261">添加第一条 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="61aee-261">Add the first SRV record:</span></span>
    
    <span data-ttu-id="61aee-262">在新记录的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="61aee-262">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="61aee-263">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="61aee-263">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="61aee-264">**类型**</span><span class="sxs-lookup"><span data-stu-id="61aee-264">**Type**</span></span>|<span data-ttu-id="61aee-265">**服务**</span><span class="sxs-lookup"><span data-stu-id="61aee-265">**Service**</span></span>|<span data-ttu-id="61aee-266">**权重**</span><span class="sxs-lookup"><span data-stu-id="61aee-266">**Weight**</span></span>|<span data-ttu-id="61aee-267">**TTL**</span><span class="sxs-lookup"><span data-stu-id="61aee-267">**TTL**</span></span>|<span data-ttu-id="61aee-268">**优先级**</span><span class="sxs-lookup"><span data-stu-id="61aee-268">**Prio**</span></span>|<span data-ttu-id="61aee-269">**协议**</span><span class="sxs-lookup"><span data-stu-id="61aee-269">**Protocol**</span></span>|<span data-ttu-id="61aee-270">**端口**</span><span class="sxs-lookup"><span data-stu-id="61aee-270">**Port**</span></span>|<span data-ttu-id="61aee-271">**目标**</span><span class="sxs-lookup"><span data-stu-id="61aee-271">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="61aee-272">SRV</span><span class="sxs-lookup"><span data-stu-id="61aee-272">SRV</span></span>|<span data-ttu-id="61aee-273">sip</span><span class="sxs-lookup"><span data-stu-id="61aee-273">sip</span></span>|<span data-ttu-id="61aee-274">1</span><span class="sxs-lookup"><span data-stu-id="61aee-274">1</span></span>|<span data-ttu-id="61aee-275">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="61aee-275">Use the default value (300).</span></span>|<span data-ttu-id="61aee-276">100</span><span class="sxs-lookup"><span data-stu-id="61aee-276">100</span></span>|<span data-ttu-id="61aee-277">tls</span><span class="sxs-lookup"><span data-stu-id="61aee-277">tls</span></span>|<span data-ttu-id="61aee-278">443</span><span class="sxs-lookup"><span data-stu-id="61aee-278">443</span></span>|<span data-ttu-id="61aee-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="61aee-279">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="61aee-280">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="61aee-280">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="61aee-281">SRV</span><span class="sxs-lookup"><span data-stu-id="61aee-281">SRV</span></span>|<span data-ttu-id="61aee-282">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="61aee-282">sipfederationtls</span></span>|<span data-ttu-id="61aee-283">1</span><span class="sxs-lookup"><span data-stu-id="61aee-283">1</span></span>|<span data-ttu-id="61aee-284">使用默认值 (300)。</span><span class="sxs-lookup"><span data-stu-id="61aee-284">Use the default value (300).</span></span>|<span data-ttu-id="61aee-285">100</span><span class="sxs-lookup"><span data-stu-id="61aee-285">100</span></span>|<span data-ttu-id="61aee-286">tcp</span><span class="sxs-lookup"><span data-stu-id="61aee-286">tcp</span></span>|<span data-ttu-id="61aee-287">5061</span><span class="sxs-lookup"><span data-stu-id="61aee-287">5061</span></span>|<span data-ttu-id="61aee-288">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="61aee-288">sipfed.online.lync.com</span></span> <br><span data-ttu-id="61aee-289">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="61aee-289">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Name-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="61aee-291">选择 "**添加记录**"。</span><span class="sxs-lookup"><span data-stu-id="61aee-291">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="61aee-293">添加第二条 SRV 记录：</span><span class="sxs-lookup"><span data-stu-id="61aee-293">Add the second SRV record:</span></span>

<span data-ttu-id="61aee-294">使用上表中下一行的值，然后选择 "**添加记录**" 以添加第二条记录。</span><span class="sxs-lookup"><span data-stu-id="61aee-294">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="61aee-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="61aee-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
