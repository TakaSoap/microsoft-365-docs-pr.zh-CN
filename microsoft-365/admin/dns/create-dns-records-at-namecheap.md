---
title: 在 Namecheap 上为 Office 365 创建 DNS 记录
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: 了解如何在 Namecheap for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: a913aa5f2d88be5bed246e813bebd590f401c07f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238435"
---
# <a name="create-dns-records-at-namecheap-for-office-365"></a><span data-ttu-id="da078-103">在 Namecheap 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="da078-103">Create DNS records at Namecheap for Office 365</span></span>

 <span data-ttu-id="da078-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="da078-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="da078-105">如果 Namecheap 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="da078-105">If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="da078-106">在 Namecheap 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="da078-106">After you add these records at Namecheap, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da078-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="da078-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="da078-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="da078-110">Add a TXT record for verification</span></span>
<span data-ttu-id="da078-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="da078-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="da078-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="da078-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da078-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="da078-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="da078-116">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="da078-116">Follow the steps below.</span></span>
  
1. <span data-ttu-id="da078-117">若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="da078-117">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="da078-118">系统将提示您登录并继续。</span><span class="sxs-lookup"><span data-stu-id="da078-118">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-配置-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="da078-120">在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。</span><span class="sxs-lookup"><span data-stu-id="da078-120">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-配置-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="da078-122">在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="da078-122">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-配置-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="da078-124">选择 "**高级 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="da078-124">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-配置-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="da078-126">在 "**主机记录**" 部分，选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="da078-126">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-配置-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="da078-128">在 "**类型**" 下拉中，选择 " **TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="da078-128">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="da078-129">当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。</span><span class="sxs-lookup"><span data-stu-id="da078-129">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-验证-1-1](../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="da078-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="da078-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="da078-132">（从下拉列表中选择 " **TTL** " 值。）</span><span class="sxs-lookup"><span data-stu-id="da078-132">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="da078-133">**类型**</span><span class="sxs-lookup"><span data-stu-id="da078-133">**Type**</span></span>|<span data-ttu-id="da078-134">**主机**</span><span class="sxs-lookup"><span data-stu-id="da078-134">**Host**</span></span>|<span data-ttu-id="da078-135">**值**</span><span class="sxs-lookup"><span data-stu-id="da078-135">**Value**</span></span>|<span data-ttu-id="da078-136">**TTL**</span><span class="sxs-lookup"><span data-stu-id="da078-136">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da078-137">TXT</span><span class="sxs-lookup"><span data-stu-id="da078-137">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="da078-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="da078-138">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="da078-139">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="da078-139">**Note:** This is an example.</span></span> <span data-ttu-id="da078-140">在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。</span><span class="sxs-lookup"><span data-stu-id="da078-140">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="da078-141">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="da078-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="da078-142">30分钟</span><span class="sxs-lookup"><span data-stu-id="da078-142">30 min</span></span>  <br/> |
       
    ![Namecheap-验证-1-2](../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="da078-144">选择 "**保存更改**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="da078-144">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-验证-1-3](../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="da078-146">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="da078-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="da078-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="da078-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="da078-148">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="da078-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="da078-149">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="da078-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="da078-150">在 "**域**" 页上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="da078-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="da078-151">在 "**设置**" 页上，选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="da078-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="da078-152">在 "**验证域**" 页上，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="da078-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="da078-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="da078-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="da078-156">添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="da078-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="da078-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="da078-157"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="da078-158">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="da078-158">Follow the steps below.</span></span>
  
1. <span data-ttu-id="da078-159">若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="da078-159">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="da078-160">系统将提示您登录并继续。</span><span class="sxs-lookup"><span data-stu-id="da078-160">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-配置-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="da078-162">在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。</span><span class="sxs-lookup"><span data-stu-id="da078-162">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-配置-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="da078-164">在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="da078-164">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-配置-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="da078-166">选择 "**高级 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="da078-166">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-配置-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="da078-168">在 "**邮件设置**" 部分，从 "**电子邮件转发**" 下拉列表中选择 "**自定义 MX** "。</span><span class="sxs-lookup"><span data-stu-id="da078-168">In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list.</span></span> 
    
    <span data-ttu-id="da078-169">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="da078-169">(You may have to scroll down.)</span></span>
    
    ![Namecheap-配置-2-1](../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. <span data-ttu-id="da078-171">选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="da078-171">Select **Add New Record**.</span></span>
    
    ![Namecheap-配置-2-2-1](../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. <span data-ttu-id="da078-173">在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="da078-173">In the boxes for the new record, type or copy and paste the values, from the following table.</span></span>
    
    <span data-ttu-id="da078-174">（"**优先级**" 框是 "**值**" 框右侧的未命名框。</span><span class="sxs-lookup"><span data-stu-id="da078-174">(The **Priority** box is the unnamed box to the right of the **Value** box.</span></span> <span data-ttu-id="da078-175">从下拉列表中选择 " **TTL** " 值。</span><span class="sxs-lookup"><span data-stu-id="da078-175">Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="da078-176">**类型**</span><span class="sxs-lookup"><span data-stu-id="da078-176">**Type**</span></span>|<span data-ttu-id="da078-177">**主机**</span><span class="sxs-lookup"><span data-stu-id="da078-177">**Host**</span></span>|<span data-ttu-id="da078-178">**值**</span><span class="sxs-lookup"><span data-stu-id="da078-178">**Value**</span></span>|<span data-ttu-id="da078-179">**优先级**</span><span class="sxs-lookup"><span data-stu-id="da078-179">**Priority**</span></span>|<span data-ttu-id="da078-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="da078-180">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da078-181">MX 记录</span><span class="sxs-lookup"><span data-stu-id="da078-181">MX Record</span></span>  <br/> |@  <br/> |<span data-ttu-id="da078-182">\<\*\*\>mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="da078-182">\<*domain-key*\>.mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="da078-183">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="da078-183">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="da078-184">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="da078-184">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  <span data-ttu-id="da078-185">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="da078-185">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="da078-186">0</span><span class="sxs-lookup"><span data-stu-id="da078-186">0</span></span>  <br/> <span data-ttu-id="da078-187">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="da078-187">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="da078-188">30分钟</span><span class="sxs-lookup"><span data-stu-id="da078-188">30 min</span></span>  <br/> |
       
    ![Namecheap-配置-2-2-2](../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. <span data-ttu-id="da078-190">选择 "**保存更改**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="da078-190">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-配置-2-3](../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. <span data-ttu-id="da078-192">如果有任何其他 MX 记录，请使用以下两步过程删除每个：</span><span class="sxs-lookup"><span data-stu-id="da078-192">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="da078-193">首先，选择要删除的记录的 "**删除" 图标**（垃圾桶）。</span><span class="sxs-lookup"><span data-stu-id="da078-193">First, select the **Delete icon** (trash can) for the record that you want to remove.</span></span> 
    
    ![Namecheap-配置-2-4](../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    <span data-ttu-id="da078-195">其次，选择 **"是"** 以确认删除。</span><span class="sxs-lookup"><span data-stu-id="da078-195">Second, select **Yes** to confirm the deletion.</span></span> 
    
    ![Namecheap-配置-2-5](../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    <span data-ttu-id="da078-197">删除在此过程前面添加的 MX 记录之外的所有 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="da078-197">Remove all MX records except for the one that you added earlier in this procedure.</span></span>

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="da078-198">添加 Office 365 所需的 6 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="da078-198">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="da078-199"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="da078-199"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="da078-200">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="da078-200">Follow the steps below.</span></span>
  
1. <span data-ttu-id="da078-201">若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="da078-201">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="da078-202">系统将提示您登录并继续。</span><span class="sxs-lookup"><span data-stu-id="da078-202">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-配置-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="da078-204">在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。</span><span class="sxs-lookup"><span data-stu-id="da078-204">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-配置-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="da078-206">在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="da078-206">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-配置-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="da078-208">选择 "**高级 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="da078-208">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-配置-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="da078-210">在 "**主机记录**" 部分，选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="da078-210">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-配置-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="da078-212">在 "**类型**" 下拉菜单中，选择 " **CNAME 记录**"。</span><span class="sxs-lookup"><span data-stu-id="da078-212">In the **Type** drop-down, select **CNAME Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="da078-213">当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。</span><span class="sxs-lookup"><span data-stu-id="da078-213">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-配置-3-1](../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. <span data-ttu-id="da078-215">在新记录的空框中，为**记录类型**选择 " **CNAME** "，然后键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="da078-215">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="da078-216">**类型**</span><span class="sxs-lookup"><span data-stu-id="da078-216">**Type**</span></span>|<span data-ttu-id="da078-217">**主机**</span><span class="sxs-lookup"><span data-stu-id="da078-217">**Host**</span></span>|<span data-ttu-id="da078-218">**值**</span><span class="sxs-lookup"><span data-stu-id="da078-218">**Value**</span></span>|<span data-ttu-id="da078-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="da078-219">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da078-220">CNAME</span><span class="sxs-lookup"><span data-stu-id="da078-220">CNAME</span></span>  <br/> |<span data-ttu-id="da078-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="da078-221">autodiscover</span></span>  <br/> |<span data-ttu-id="da078-222">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="da078-222">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="da078-223">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="da078-223">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="da078-224">3600</span><span class="sxs-lookup"><span data-stu-id="da078-224">3600</span></span>  <br/> |
    |<span data-ttu-id="da078-225">CNAME</span><span class="sxs-lookup"><span data-stu-id="da078-225">CNAME</span></span>  <br/> |<span data-ttu-id="da078-226">sip</span><span class="sxs-lookup"><span data-stu-id="da078-226">sip</span></span>  <br/> |<span data-ttu-id="da078-227">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="da078-227">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="da078-228">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="da078-228">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="da078-229">3600</span><span class="sxs-lookup"><span data-stu-id="da078-229">3600</span></span>  <br/> |
    |<span data-ttu-id="da078-230">CNAME</span><span class="sxs-lookup"><span data-stu-id="da078-230">CNAME</span></span>  <br/> |<span data-ttu-id="da078-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="da078-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="da078-232">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="da078-232">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="da078-233">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="da078-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="da078-234">3600</span><span class="sxs-lookup"><span data-stu-id="da078-234">3600</span></span>  <br/> |
    |<span data-ttu-id="da078-235">CNAME</span><span class="sxs-lookup"><span data-stu-id="da078-235">CNAME</span></span>  <br/> |<span data-ttu-id="da078-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="da078-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="da078-237">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="da078-237">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="da078-238">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="da078-238">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="da078-239">3600</span><span class="sxs-lookup"><span data-stu-id="da078-239">3600</span></span>  <br/> |
    |<span data-ttu-id="da078-240">CNAME</span><span class="sxs-lookup"><span data-stu-id="da078-240">CNAME</span></span>  <br/> |<span data-ttu-id="da078-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="da078-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="da078-242">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="da078-242">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="da078-243">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="da078-243">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="da078-244">3600</span><span class="sxs-lookup"><span data-stu-id="da078-244">3600</span></span>  <br/> |
       
    ![Namecheap-配置-3-2](../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. <span data-ttu-id="da078-246">选择 "**保存更改**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="da078-246">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-配置-3-3](../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. <span data-ttu-id="da078-248">使用前面的四个步骤和表中其他五行中的值，添加其他五个 CNAME 记录中的每个。</span><span class="sxs-lookup"><span data-stu-id="da078-248">Using the preceding four steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="da078-249">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="da078-249">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="da078-250"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="da078-250"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="da078-251">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="da078-251">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="da078-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="da078-252">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="da078-253">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="da078-253">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="da078-254">改为将所需的 Office 365 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="da078-254">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 

<span data-ttu-id="da078-255">按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="da078-255">Follow the steps below.</span></span>
  
1. <span data-ttu-id="da078-256">若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="da078-256">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="da078-257">系统将提示您登录并继续。</span><span class="sxs-lookup"><span data-stu-id="da078-257">You'll be prompted to Sign in and Continue.</span></span>
    
2. <span data-ttu-id="da078-258">在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。</span><span class="sxs-lookup"><span data-stu-id="da078-258">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-配置-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="da078-260">在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="da078-260">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-配置-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="da078-262">选择 "**高级 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="da078-262">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-配置-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="da078-264">在 "**主机记录**" 部分，选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="da078-264">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-配置-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="da078-266">在 "**类型**" 下拉中，选择 " **TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="da078-266">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="da078-267">当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。</span><span class="sxs-lookup"><span data-stu-id="da078-267">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-配置-4-1](../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. <span data-ttu-id="da078-269">在新记录的框中，键入或复制并粘贴下表中的以下值。</span><span class="sxs-lookup"><span data-stu-id="da078-269">In the boxes for the new record, type or copy and paste the following values from the following table.</span></span>
    
    <span data-ttu-id="da078-270">（从下拉列表中选择 " **TTL** " 值。）</span><span class="sxs-lookup"><span data-stu-id="da078-270">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="da078-271">**类型**</span><span class="sxs-lookup"><span data-stu-id="da078-271">**Type**</span></span>|<span data-ttu-id="da078-272">**主机**</span><span class="sxs-lookup"><span data-stu-id="da078-272">**Host**</span></span>|<span data-ttu-id="da078-273">**值**</span><span class="sxs-lookup"><span data-stu-id="da078-273">**Value**</span></span>|<span data-ttu-id="da078-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="da078-274">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da078-275">TXT</span><span class="sxs-lookup"><span data-stu-id="da078-275">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="da078-276">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="da078-276">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="da078-277">**注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。</span><span class="sxs-lookup"><span data-stu-id="da078-277">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="da078-278">30分钟</span><span class="sxs-lookup"><span data-stu-id="da078-278">30 min</span></span>  <br/> |
       
    ![Namecheap-配置-4-2](../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. <span data-ttu-id="da078-280">选择 "**保存更改**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="da078-280">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-配置-4-3](../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="da078-282">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="da078-282">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="da078-283"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="da078-283"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="da078-284">若要开始，请使用[此链接](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f)转到 Namecheap 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="da078-284">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="da078-285">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="da078-285">You'll be prompted to sign in.</span></span>
    
    ![Namecheap-配置-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="da078-287">在 "**登录**" 页面上的 "**帐户**" 下，从下拉列表中选择 "**域列表**"。</span><span class="sxs-lookup"><span data-stu-id="da078-287">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-配置-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="da078-289">在 "**域列表**" 页上，找到要编辑的域的名称，然后选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="da078-289">On the **Domain List** page, find the name of the domain that you want to edit and then select **Manage**.</span></span>
    
    ![Namecheap-配置-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="da078-291">选择 "**高级 DNS**"。</span><span class="sxs-lookup"><span data-stu-id="da078-291">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-配置-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="da078-293">在 "**主机记录**" 部分，选择 "**添加新记录**"。</span><span class="sxs-lookup"><span data-stu-id="da078-293">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-配置-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="da078-295">在 "**类型**" 下拉菜单中，选择 " **SRV 记录**"。</span><span class="sxs-lookup"><span data-stu-id="da078-295">In the **Type** drop-down, select **SRV Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="da078-296">当您选择 "**添加新记录**" 时，"类型" 下拉**类型**将自动显示。</span><span class="sxs-lookup"><span data-stu-id="da078-296">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span> 
  
    ![Namecheap-配置-5-1](../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. <span data-ttu-id="da078-298">在新记录的空框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="da078-298">In the empty boxes for the new records, type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="da078-299">**服务**</span><span class="sxs-lookup"><span data-stu-id="da078-299">**Service**</span></span>|<span data-ttu-id="da078-300">**协议**</span><span class="sxs-lookup"><span data-stu-id="da078-300">**Protocol**</span></span>|<span data-ttu-id="da078-301">**优先级**</span><span class="sxs-lookup"><span data-stu-id="da078-301">**Priority**</span></span>|<span data-ttu-id="da078-302">**权重**</span><span class="sxs-lookup"><span data-stu-id="da078-302">**Weight**</span></span>|<span data-ttu-id="da078-303">**端口**</span><span class="sxs-lookup"><span data-stu-id="da078-303">**Port**</span></span>|<span data-ttu-id="da078-304">**目标**</span><span class="sxs-lookup"><span data-stu-id="da078-304">**Target**</span></span>|<span data-ttu-id="da078-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="da078-305">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="da078-306">_sip</span><span class="sxs-lookup"><span data-stu-id="da078-306">_sip</span></span>  <br/> |<span data-ttu-id="da078-307">_tls</span><span class="sxs-lookup"><span data-stu-id="da078-307">_tls</span></span>  <br/> |<span data-ttu-id="da078-308">100</span><span class="sxs-lookup"><span data-stu-id="da078-308">100</span></span>  <br/> |<span data-ttu-id="da078-309">1</span><span class="sxs-lookup"><span data-stu-id="da078-309">1</span></span>  <br/> |<span data-ttu-id="da078-310">443</span><span class="sxs-lookup"><span data-stu-id="da078-310">443</span></span>  <br/> |<span data-ttu-id="da078-311">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="da078-311">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="da078-312">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="da078-312">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="da078-313">30分钟</span><span class="sxs-lookup"><span data-stu-id="da078-313">30 min</span></span>  <br/> |
    |<span data-ttu-id="da078-314">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="da078-314">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="da078-315">_tcp</span><span class="sxs-lookup"><span data-stu-id="da078-315">_tcp</span></span>  <br/> |<span data-ttu-id="da078-316">100</span><span class="sxs-lookup"><span data-stu-id="da078-316">100</span></span>  <br/> |<span data-ttu-id="da078-317">1</span><span class="sxs-lookup"><span data-stu-id="da078-317">1</span></span>  <br/> |<span data-ttu-id="da078-318">5061</span><span class="sxs-lookup"><span data-stu-id="da078-318">5061</span></span>  <br/> |<span data-ttu-id="da078-319">sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="da078-319">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="da078-320">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="da078-320">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="da078-321">30分钟</span><span class="sxs-lookup"><span data-stu-id="da078-321">30 min</span></span>  <br/> |
       
    ![Namecheap-配置-5-2](../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. <span data-ttu-id="da078-323">选择 "**保存更改**" （复选标记）控件。</span><span class="sxs-lookup"><span data-stu-id="da078-323">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-配置-5-3](../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. <span data-ttu-id="da078-325">使用前面的四个步骤和表中第二行的值，添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="da078-325">Using the preceding four steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="da078-p114">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="da078-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

  
