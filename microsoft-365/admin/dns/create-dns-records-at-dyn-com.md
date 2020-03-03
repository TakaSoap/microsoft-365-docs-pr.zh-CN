---
title: 在 Dyn.com 处为 Office 365 创建 DNS 记录
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: 了解如何在 Dyn.com for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: a09ba409b1788432c5cd5c060252bb76b6903342
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349343"
---
# <a name="create-dns-records-at-dyncom-for-office-365"></a><span data-ttu-id="604ed-103">在 Dyn.com 处为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="604ed-103">Create DNS records at Dyn.com for Office 365</span></span>

 <span data-ttu-id="604ed-104">**如果找不到要查找的内容，请[查看域常见问题解答](../setup/domains-faq.md)** 。</span><span class="sxs-lookup"><span data-stu-id="604ed-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="604ed-105">如果 DNS 托管提供者是 Dyn.com，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="604ed-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="604ed-106">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="604ed-106">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="604ed-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="604ed-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="604ed-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="604ed-110">Add a TXT record for verification</span></span>
<span data-ttu-id="604ed-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="604ed-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="604ed-p102">若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。系统会提示你先进行登录。</span><span class="sxs-lookup"><span data-stu-id="604ed-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="604ed-115">在 "**区域级别服务**" 页上，为要编辑的域选择 " **Dyn Standard DNS 服务**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="604ed-116">在您的域的 " **DNS** " 页面上，选择 "**首选项**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="604ed-117">选择 "**启用专家界面**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="604ed-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="604ed-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="604ed-119">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="604ed-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="604ed-120">**主机**</span><span class="sxs-lookup"><span data-stu-id="604ed-120">**Host**</span></span>|<span data-ttu-id="604ed-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="604ed-121">**TTL**</span></span>|<span data-ttu-id="604ed-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="604ed-122">**Type**</span></span>|<span data-ttu-id="604ed-123">**数据**</span><span class="sxs-lookup"><span data-stu-id="604ed-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="604ed-124">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="604ed-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="604ed-125">600</span><span class="sxs-lookup"><span data-stu-id="604ed-125">600</span></span>  <br/> |<span data-ttu-id="604ed-126">TXT</span><span class="sxs-lookup"><span data-stu-id="604ed-126">TXT</span></span>  <br/> |<span data-ttu-id="604ed-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="604ed-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="604ed-128">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="604ed-128">**Note:** This is an example.</span></span> <span data-ttu-id="604ed-129">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="604ed-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="604ed-130">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="604ed-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-验证-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="604ed-132">选择 "**创建记录**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="604ed-134">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="604ed-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="604ed-135">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="604ed-135">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="604ed-136">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="604ed-136">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="604ed-137">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="604ed-137">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="604ed-138">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="604ed-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="604ed-139">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="604ed-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="604ed-140">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="604ed-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="604ed-p104">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="604ed-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="604ed-144">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="604ed-144">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="604ed-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="604ed-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="604ed-p105">若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。系统会提示你先进行登录。</span><span class="sxs-lookup"><span data-stu-id="604ed-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="604ed-149">在 "**区域级别服务**" 页上，为要编辑的域选择 " **Dyn Standard DNS 服务**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="604ed-150">在您的域的 "DNS" 页面上，选择 "**首选项**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="604ed-151">选择 "**启用专家界面**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="604ed-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="604ed-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="604ed-153">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="604ed-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="604ed-154">**主机**</span><span class="sxs-lookup"><span data-stu-id="604ed-154">**Host**</span></span>|<span data-ttu-id="604ed-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="604ed-155">**TTL**</span></span>|<span data-ttu-id="604ed-156">**类型**</span><span class="sxs-lookup"><span data-stu-id="604ed-156">**Type**</span></span>|<span data-ttu-id="604ed-157">**数据**</span><span class="sxs-lookup"><span data-stu-id="604ed-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="604ed-158">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="604ed-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="604ed-159">600</span><span class="sxs-lookup"><span data-stu-id="604ed-159">600</span></span>  <br/> |<span data-ttu-id="604ed-160">MX</span><span class="sxs-lookup"><span data-stu-id="604ed-160">MX</span></span>  <br/> |<span data-ttu-id="604ed-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="604ed-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="604ed-162">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="604ed-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="604ed-p106">**10** 是 MX 优先级值。将其添加到 MX 值的开头，使用一个空格将其与其余部分隔开。  </span><span class="sxs-lookup"><span data-stu-id="604ed-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="604ed-165">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="604ed-165">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           <span data-ttu-id="604ed-166">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="604ed-166">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>      <br>    <span data-ttu-id="604ed-167">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="604ed-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Dyn-配置-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="604ed-169">选择 "**创建记录**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="604ed-171">如果存在任何其他 MX 记录，通过选中" **删除**"列中这些记录的复选框将其删除。</span><span class="sxs-lookup"><span data-stu-id="604ed-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="604ed-173">选择 "**应用更改**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="604ed-175">添加 Office 365 所需的 6 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="604ed-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="604ed-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="604ed-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="604ed-p108">若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。系统会提示你先进行登录。</span><span class="sxs-lookup"><span data-stu-id="604ed-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="604ed-180">在 "**区域级别服务**" 页上，为要编辑的域选择 " **Dyn Standard DNS 服务**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="604ed-181">在您的域的 " **DNS** " 页面上，选择 "**首选项**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="604ed-182">选择 "**启用专家界面**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="604ed-183">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="604ed-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="604ed-184">在" **添加 DNS 记录**"部分中新记录的框内，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="604ed-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="604ed-185">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="604ed-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="604ed-186">**主机**</span><span class="sxs-lookup"><span data-stu-id="604ed-186">**Host**</span></span>|<span data-ttu-id="604ed-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="604ed-187">**TTL**</span></span>|<span data-ttu-id="604ed-188">**类型**</span><span class="sxs-lookup"><span data-stu-id="604ed-188">**Type**</span></span>|<span data-ttu-id="604ed-189">**数据**</span><span class="sxs-lookup"><span data-stu-id="604ed-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="604ed-190">autodiscover</span><span class="sxs-lookup"><span data-stu-id="604ed-190">autodiscover</span></span>  <br/> |<span data-ttu-id="604ed-191">600</span><span class="sxs-lookup"><span data-stu-id="604ed-191">600</span></span>  <br/> |<span data-ttu-id="604ed-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="604ed-192">CNAME</span></span>  <br/> |<span data-ttu-id="604ed-193">autodiscover.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="604ed-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="604ed-194">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="604ed-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="604ed-195">sip</span><span class="sxs-lookup"><span data-stu-id="604ed-195">sip</span></span>  <br/> |<span data-ttu-id="604ed-196">600</span><span class="sxs-lookup"><span data-stu-id="604ed-196">600</span></span>  <br/> |<span data-ttu-id="604ed-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="604ed-197">CNAME</span></span>  <br/> |<span data-ttu-id="604ed-198">sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="604ed-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="604ed-199">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="604ed-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="604ed-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="604ed-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="604ed-201">600</span><span class="sxs-lookup"><span data-stu-id="604ed-201">600</span></span>  <br/> |<span data-ttu-id="604ed-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="604ed-202">CNAME</span></span>  <br/> |<span data-ttu-id="604ed-203">webdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="604ed-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="604ed-204">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="604ed-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="604ed-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="604ed-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="604ed-206">600</span><span class="sxs-lookup"><span data-stu-id="604ed-206">600</span></span>  <br/> |<span data-ttu-id="604ed-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="604ed-207">CNAME</span></span>  <br/> |<span data-ttu-id="604ed-208">enterpriseregistration.windows.net。</span><span class="sxs-lookup"><span data-stu-id="604ed-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="604ed-209">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="604ed-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="604ed-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="604ed-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="604ed-211">600</span><span class="sxs-lookup"><span data-stu-id="604ed-211">600</span></span>  <br/> |<span data-ttu-id="604ed-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="604ed-212">CNAME</span></span>  <br/> |<span data-ttu-id="604ed-213">enterpriseenrollment-s.manage.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="604ed-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="604ed-214">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="604ed-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-配置-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="604ed-216">选择 "**创建记录**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="604ed-218">添加其他五条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="604ed-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="604ed-219">在 "**添加 DNS 记录**" 部分，使用表中下一行的值创建记录，然后再次选择 "**创建记录**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="604ed-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="604ed-220">重复该过程，直到创建完全部 6 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="604ed-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="604ed-221">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="604ed-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="604ed-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="604ed-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="604ed-223">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="604ed-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="604ed-224">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="604ed-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="604ed-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="604ed-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="604ed-226">可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="604ed-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="604ed-p110">若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。系统会提示你先进行登录。</span><span class="sxs-lookup"><span data-stu-id="604ed-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="604ed-230">在 "**区域级别服务**" 页上，为要编辑的域选择 " **Dyn Standard DNS 服务**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="604ed-231">在您的域的 " **DNS** " 页面上，选择 "**首选项**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="604ed-232">选择 "**启用专家界面**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="604ed-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="604ed-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="604ed-234">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="604ed-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="604ed-235">**主机**</span><span class="sxs-lookup"><span data-stu-id="604ed-235">**Host**</span></span>|<span data-ttu-id="604ed-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="604ed-236">**TTL**</span></span>|<span data-ttu-id="604ed-237">**类型**</span><span class="sxs-lookup"><span data-stu-id="604ed-237">**Type**</span></span>|<span data-ttu-id="604ed-238">**数据**</span><span class="sxs-lookup"><span data-stu-id="604ed-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="604ed-239">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="604ed-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="604ed-240">600</span><span class="sxs-lookup"><span data-stu-id="604ed-240">600</span></span>  <br/> |<span data-ttu-id="604ed-241">TXT</span><span class="sxs-lookup"><span data-stu-id="604ed-241">TXT</span></span>  <br/> |<span data-ttu-id="604ed-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="604ed-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="604ed-243">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="604ed-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-配置-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="604ed-245">选择 "**创建记录**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-245">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="604ed-247">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="604ed-247">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="604ed-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="604ed-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="604ed-249">若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="604ed-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="604ed-250">系统将提示您先登录</span><span class="sxs-lookup"><span data-stu-id="604ed-250">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="604ed-252">在 "**区域级别服务**" 页上，为要编辑的域选择 " **Dyn Standard DNS 服务**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="604ed-253">在您的域的 " **DNS** " 页面上，选择 "**首选项**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="604ed-254">选择 "**启用专家界面**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="604ed-255">添加两条 SRV 记录中的第一条。</span><span class="sxs-lookup"><span data-stu-id="604ed-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="604ed-256">在" **添加 DNS 记录**"部分中新记录的框内，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="604ed-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="604ed-257">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="604ed-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="604ed-258">**主机**</span><span class="sxs-lookup"><span data-stu-id="604ed-258">**Host**</span></span>|<span data-ttu-id="604ed-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="604ed-259">**TTL**</span></span>|<span data-ttu-id="604ed-260">**类型**</span><span class="sxs-lookup"><span data-stu-id="604ed-260">**Type**</span></span>|<span data-ttu-id="604ed-261">**数据**</span><span class="sxs-lookup"><span data-stu-id="604ed-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="604ed-262">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="604ed-262">_sip._tls</span></span>|<span data-ttu-id="604ed-263">600</span><span class="sxs-lookup"><span data-stu-id="604ed-263">600</span></span>|<span data-ttu-id="604ed-264">SRV</span><span class="sxs-lookup"><span data-stu-id="604ed-264">SRV</span></span>|<span data-ttu-id="604ed-265">100 1 443 sipdir.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="604ed-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="604ed-266">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="604ed-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="604ed-267">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="604ed-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="604ed-268">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="604ed-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="604ed-269">600</span><span class="sxs-lookup"><span data-stu-id="604ed-269">600</span></span>|<span data-ttu-id="604ed-270">SRV</span><span class="sxs-lookup"><span data-stu-id="604ed-270">SRV</span></span>|<span data-ttu-id="604ed-271">100 1 5061 sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="604ed-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="604ed-272">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="604ed-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="604ed-273">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="604ed-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-配置-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="604ed-275">选择 "**创建记录**"。</span><span class="sxs-lookup"><span data-stu-id="604ed-275">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="604ed-277">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="604ed-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="604ed-278">在 "**添加 DNS 记录**" 部分，使用表中第二行的值创建记录，然后再次选择 "**创建记录**" 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="604ed-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="604ed-p114">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="604ed-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
