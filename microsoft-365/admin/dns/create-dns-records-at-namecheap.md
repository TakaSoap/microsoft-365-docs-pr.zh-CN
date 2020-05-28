---
title: 在 Namecheap 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: 了解如何验证您的域，并在 Namecheap for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 2aae667428aba5ea22ab210c47aa9c994a9acf14
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400384"
---
# <a name="create-dns-records-at-namecheap-for-microsoft"></a><span data-ttu-id="dba66-103">在 Namecheap 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="dba66-103">Create DNS records at Namecheap for Microsoft</span></span>

 <span data-ttu-id="dba66-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="dba66-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="dba66-105">如果 Namecheap 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="dba66-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="dba66-106">在 Namecheap 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="dba66-106">After you add these records at Namecheap, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dba66-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dba66-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="dba66-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="dba66-110">Add a TXT record for verification</span></span>
<span data-ttu-id="dba66-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="dba66-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="dba66-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="dba66-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dba66-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="dba66-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="dba66-116">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="dba66-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="dba66-117">若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="dba66-117">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="dba66-118">系统将提示您登录并继续。</span><span class="sxs-lookup"><span data-stu-id="dba66-118">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-配置-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="dba66-120">在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-配置-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="dba66-122">在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-配置-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="dba66-124">选择 "**高级 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-配置-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="dba66-126">在 "**主机记录**" 部分，选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-配置-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="dba66-128">在 "**类型**" 下拉中，选择 " **TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dba66-129">当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。</span><span class="sxs-lookup"><span data-stu-id="dba66-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-验证-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="dba66-131">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dba66-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="dba66-132">（从下拉列表中选择 " **TTL** " 值。）</span><span class="sxs-lookup"><span data-stu-id="dba66-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="dba66-133">**类型**</span><span class="sxs-lookup"><span data-stu-id="dba66-133">**Type**</span></span>|<span data-ttu-id="dba66-134">**主机**</span><span class="sxs-lookup"><span data-stu-id="dba66-134">**Host**</span></span>|<span data-ttu-id="dba66-135">**值**</span><span class="sxs-lookup"><span data-stu-id="dba66-135">**Value**</span></span>|<span data-ttu-id="dba66-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dba66-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dba66-137">TXT</span><span class="sxs-lookup"><span data-stu-id="dba66-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="dba66-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="dba66-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="dba66-139">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="dba66-139">**Note:** This is an example.</span></span> <span data-ttu-id="dba66-140">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="dba66-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="dba66-141">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="dba66-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="dba66-142">30分钟</span><span class="sxs-lookup"><span data-stu-id="dba66-142">30 min</span></span>  <br/> |
       
    ![Namecheap-验证-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="dba66-144">选择 "**保存更改**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="dba66-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-验证-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="dba66-146">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="dba66-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="dba66-147">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="dba66-147">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="dba66-148">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="dba66-148">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="dba66-149">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="dba66-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="dba66-150">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="dba66-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="dba66-151">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="dba66-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="dba66-152">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="dba66-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="dba66-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dba66-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="dba66-156">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="dba66-156">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="dba66-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="dba66-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="dba66-158">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="dba66-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="dba66-159">若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="dba66-159">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="dba66-160">系统将提示您登录并继续。</span><span class="sxs-lookup"><span data-stu-id="dba66-160">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-配置-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="dba66-162">在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-配置-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="dba66-164">在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-配置-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="dba66-166">选择 "**高级 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-配置-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="dba66-168">在 "**邮件设置**" 部分，从 "**电子邮件转发**" 下拉列表中选择 "**自定义 MX** "。</span><span class="sxs-lookup"><span data-stu-id="dba66-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="dba66-169">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="dba66-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-配置-2-1](../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="dba66-171">选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-配置-2-2-1](../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="dba66-173">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="dba66-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="dba66-174">（"**优先级**" 框是 "**值**" 框右侧的未命名框。</span><span class="sxs-lookup"><span data-stu-id="dba66-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="dba66-175">从下拉列表中选择 " **TTL** " 值。</span><span class="sxs-lookup"><span data-stu-id="dba66-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="dba66-176">**类型**</span><span class="sxs-lookup"><span data-stu-id="dba66-176">**Type**</span></span>|<span data-ttu-id="dba66-177">**主机**</span><span class="sxs-lookup"><span data-stu-id="dba66-177">**Host**</span></span>|<span data-ttu-id="dba66-178">**值**</span><span class="sxs-lookup"><span data-stu-id="dba66-178">**Value**</span></span>|<span data-ttu-id="dba66-179">**优先级**</span><span class="sxs-lookup"><span data-stu-id="dba66-179">**Priority**</span></span>|<span data-ttu-id="dba66-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dba66-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dba66-181">MX 记录</span><span class="sxs-lookup"><span data-stu-id="dba66-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="dba66-182">\<*domain-key*\>. mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="dba66-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="dba66-183">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="dba66-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="dba66-184">\**注意：\*\*\*\<domain-key\>* 从你的 Microsoft 帐户获取你的。</span><span class="sxs-lookup"><span data-stu-id="dba66-184">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  <span data-ttu-id="dba66-185">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="dba66-185">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="dba66-186">0</span><span class="sxs-lookup"><span data-stu-id="dba66-186">0</span></span>  <br/> <span data-ttu-id="dba66-187">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="dba66-187">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="dba66-188">30分钟</span><span class="sxs-lookup"><span data-stu-id="dba66-188">30 min</span></span>  <br/> |
       
    ![Namecheap-配置-2-2-2](../../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="dba66-190">选择 "**保存更改**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="dba66-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-配置-2-3](../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="dba66-192">如果有任何其他 MX 记录，请使用以下两步过程删除每个：</span><span class="sxs-lookup"><span data-stu-id="dba66-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="dba66-193">首先，选择要删除的记录的 "**删除" 图标**（垃圾桶）。</span><span class="sxs-lookup"><span data-stu-id="dba66-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-配置-2-4](../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="dba66-195">其次，选择 **"是"** 以确认删除。</span><span class="sxs-lookup"><span data-stu-id="dba66-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-配置-2-5](../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="dba66-197">删除在此过程前面添加的 MX 记录之外的所有 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="dba66-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="dba66-198">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="dba66-198">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="dba66-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="dba66-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="dba66-200">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="dba66-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="dba66-201">若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="dba66-201">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="dba66-202">系统将提示您登录并继续。</span><span class="sxs-lookup"><span data-stu-id="dba66-202">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-配置-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="dba66-204">在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-配置-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="dba66-206">在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-配置-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="dba66-208">选择 "**高级 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-配置-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="dba66-210">在 "**主机记录**" 部分，选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-配置-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="dba66-212">在 "**类型**" 下拉菜单中，选择 " **CNAME 记录**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dba66-213">当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。</span><span class="sxs-lookup"><span data-stu-id="dba66-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-配置-3-1](../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="dba66-215">在新记录的空框中，为**记录类型**选择 " **CNAME** "，然后键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="dba66-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="dba66-216">**类型**</span><span class="sxs-lookup"><span data-stu-id="dba66-216">**Type**</span></span>|<span data-ttu-id="dba66-217">**主机**</span><span class="sxs-lookup"><span data-stu-id="dba66-217">**Host**</span></span>|<span data-ttu-id="dba66-218">**值**</span><span class="sxs-lookup"><span data-stu-id="dba66-218">**Value**</span></span>|<span data-ttu-id="dba66-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dba66-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dba66-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="dba66-220">CNAME</span></span>  <br/> |<span data-ttu-id="dba66-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="dba66-221">autodiscover</span></span>  <br/> |<span data-ttu-id="dba66-222">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="dba66-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="dba66-223">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="dba66-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="dba66-224">3600</span><span class="sxs-lookup"><span data-stu-id="dba66-224">3600</span></span>  <br/> |
    |<span data-ttu-id="dba66-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="dba66-225">CNAME</span></span>  <br/> |<span data-ttu-id="dba66-226">sip</span><span class="sxs-lookup"><span data-stu-id="dba66-226">sip</span></span>  <br/> |<span data-ttu-id="dba66-227">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="dba66-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="dba66-228">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="dba66-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="dba66-229">3600</span><span class="sxs-lookup"><span data-stu-id="dba66-229">3600</span></span>  <br/> |
    |<span data-ttu-id="dba66-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="dba66-230">CNAME</span></span>  <br/> |<span data-ttu-id="dba66-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="dba66-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="dba66-232">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="dba66-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="dba66-233">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="dba66-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="dba66-234">3600</span><span class="sxs-lookup"><span data-stu-id="dba66-234">3600</span></span>  <br/> |
    |<span data-ttu-id="dba66-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="dba66-235">CNAME</span></span>  <br/> |<span data-ttu-id="dba66-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="dba66-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="dba66-237">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="dba66-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="dba66-238">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="dba66-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="dba66-239">3600</span><span class="sxs-lookup"><span data-stu-id="dba66-239">3600</span></span>  <br/> |
    |<span data-ttu-id="dba66-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="dba66-240">CNAME</span></span>  <br/> |<span data-ttu-id="dba66-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="dba66-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="dba66-242">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="dba66-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="dba66-243">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="dba66-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="dba66-244">3600</span><span class="sxs-lookup"><span data-stu-id="dba66-244">3600</span></span>  <br/> |
       
    ![Namecheap-配置-3-2](../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="dba66-246">选择 "**保存更改**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="dba66-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-配置-3-3](../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="dba66-248">使用前面的四个步骤和表中其他五行中的值，添加其他五个 CNAME 记录中的每个。</span><span class="sxs-lookup"><span data-stu-id="dba66-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="dba66-249">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="dba66-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="dba66-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="dba66-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="dba66-251">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="dba66-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="dba66-252">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="dba66-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="dba66-253">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="dba66-253">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="dba66-254">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="dba66-254">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="dba66-255">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="dba66-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="dba66-256">若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="dba66-256">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="dba66-257">系统将提示您登录并继续。</span><span class="sxs-lookup"><span data-stu-id="dba66-257">You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="dba66-258">在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-配置-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="dba66-260">在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-配置-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="dba66-262">选择 "**高级 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-配置-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="dba66-264">在 "**主机记录**" 部分，选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-配置-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="dba66-266">在 "**类型**" 下拉中，选择 " **TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dba66-267">当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。</span><span class="sxs-lookup"><span data-stu-id="dba66-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-配置-4-1](../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="dba66-269">在新记录的框中，键入或复制并粘贴下表中的以下值。</span><span class="sxs-lookup"><span data-stu-id="dba66-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="dba66-270">（从下拉列表中选择 " **TTL** " 值。）</span><span class="sxs-lookup"><span data-stu-id="dba66-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="dba66-271">**类型**</span><span class="sxs-lookup"><span data-stu-id="dba66-271">**Type**</span></span>|<span data-ttu-id="dba66-272">**主机**</span><span class="sxs-lookup"><span data-stu-id="dba66-272">**Host**</span></span>|<span data-ttu-id="dba66-273">**值**</span><span class="sxs-lookup"><span data-stu-id="dba66-273">**Value**</span></span>|<span data-ttu-id="dba66-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dba66-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dba66-275">TXT</span><span class="sxs-lookup"><span data-stu-id="dba66-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="dba66-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="dba66-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="dba66-277">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="dba66-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="dba66-278">30分钟</span><span class="sxs-lookup"><span data-stu-id="dba66-278">30 min</span></span>  <br/> |
       
    ![Namecheap-配置-4-2](../../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="dba66-280">选择 "**保存更改**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="dba66-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-配置-4-3](../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="dba66-282">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="dba66-282">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="dba66-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="dba66-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="dba66-284">若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="dba66-284">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="dba66-285">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="dba66-285">You'll be prompted to sign in.</span></span>
    
    ![Namecheap-配置-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="dba66-287">在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-配置-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="dba66-289">在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-配置-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="dba66-291">选择 "**高级 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-配置-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="dba66-293">在 "**主机记录**" 部分，选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-配置-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="dba66-295">在 "**类型**" 下拉菜单中，选择 " **SRV 记录**"。</span><span class="sxs-lookup"><span data-stu-id="dba66-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dba66-296">当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。</span><span class="sxs-lookup"><span data-stu-id="dba66-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-配置-5-1](../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="dba66-298">在新记录的空框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="dba66-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="dba66-299">**服务**</span><span class="sxs-lookup"><span data-stu-id="dba66-299">**Service**</span></span>|<span data-ttu-id="dba66-300">**协议**</span><span class="sxs-lookup"><span data-stu-id="dba66-300">**Protocol**</span></span>|<span data-ttu-id="dba66-301">**优先级**</span><span class="sxs-lookup"><span data-stu-id="dba66-301">**Priority**</span></span>|<span data-ttu-id="dba66-302">**权重**</span><span class="sxs-lookup"><span data-stu-id="dba66-302">**Weight**</span></span>|<span data-ttu-id="dba66-303">**端口**</span><span class="sxs-lookup"><span data-stu-id="dba66-303">**Port**</span></span>|<span data-ttu-id="dba66-304">**目标**</span><span class="sxs-lookup"><span data-stu-id="dba66-304">**Target**</span></span>|<span data-ttu-id="dba66-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dba66-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dba66-306">_sip</span><span class="sxs-lookup"><span data-stu-id="dba66-306">_sip</span></span>  <br/> |<span data-ttu-id="dba66-307">_tls</span><span class="sxs-lookup"><span data-stu-id="dba66-307">_tls</span></span>  <br/> |<span data-ttu-id="dba66-308">100</span><span class="sxs-lookup"><span data-stu-id="dba66-308">100</span></span>  <br/> |<span data-ttu-id="dba66-309">1 </span><span class="sxs-lookup"><span data-stu-id="dba66-309">1</span></span>  <br/> |<span data-ttu-id="dba66-310">443</span><span class="sxs-lookup"><span data-stu-id="dba66-310">443</span></span>  <br/> |<span data-ttu-id="dba66-311">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="dba66-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="dba66-312">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="dba66-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="dba66-313">30分钟</span><span class="sxs-lookup"><span data-stu-id="dba66-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="dba66-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="dba66-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="dba66-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="dba66-315">_tcp</span></span>  <br/> |<span data-ttu-id="dba66-316">100</span><span class="sxs-lookup"><span data-stu-id="dba66-316">100</span></span>  <br/> |<span data-ttu-id="dba66-317">1 </span><span class="sxs-lookup"><span data-stu-id="dba66-317">1</span></span>  <br/> |<span data-ttu-id="dba66-318">5061</span><span class="sxs-lookup"><span data-stu-id="dba66-318">5061</span></span>  <br/> |<span data-ttu-id="dba66-319">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="dba66-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="dba66-320">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="dba66-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="dba66-321">30分钟</span><span class="sxs-lookup"><span data-stu-id="dba66-321">30 min</span></span>  <br/> |
       
    ![Namecheap-配置-5-2](../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="dba66-323">选择 "**保存更改**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="dba66-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-配置-5-3](../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="dba66-325">使用前面的四个步骤和表中第二行的值，添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="dba66-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dba66-p114">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="dba66-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
