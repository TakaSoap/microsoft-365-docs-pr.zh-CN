---
title: 在 Microsoft Dyn.com 创建 DNS 记录
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: 了解如何验证你的域，并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录，Dyn.com Microsoft。
ms.openlocfilehash: 432dc630d49cc3494d17b3f007f813d66dc6b1c3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910326"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="1f8be-103">在 Microsoft Dyn.com 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="1f8be-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="1f8be-104">**如果找不到要查找的内容，请 [查看域常见问题解答](../setup/domains-faq.yml)** 。</span><span class="sxs-lookup"><span data-stu-id="1f8be-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1f8be-105">如果 DNS 托管提供者是 Dyn.com，请按本文中的步骤验证域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 

  
> [!NOTE]
>  <span data-ttu-id="1f8be-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1f8be-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1f8be-109">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="1f8be-109">Add a TXT record for verification</span></span>
<span data-ttu-id="1f8be-110"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1f8be-110"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="1f8be-p102">若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。系统会提示你先进行登录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="1f8be-114">在" **区域级别服务** "页上，为要编辑的域选择 **"Dyn** 标准 DNS 服务"。</span><span class="sxs-lookup"><span data-stu-id="1f8be-114">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1f8be-115">在域 **的"DNS"** 页面上，选择 **"首选项"。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-115">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="1f8be-116">选择 **启用专家接口**。</span><span class="sxs-lookup"><span data-stu-id="1f8be-116">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="1f8be-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1f8be-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1f8be-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1f8be-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1f8be-119">**主机**</span><span class="sxs-lookup"><span data-stu-id="1f8be-119">**Host**</span></span>|<span data-ttu-id="1f8be-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1f8be-120">**TTL**</span></span>|<span data-ttu-id="1f8be-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="1f8be-121">**Type**</span></span>|<span data-ttu-id="1f8be-122">**数据**</span><span class="sxs-lookup"><span data-stu-id="1f8be-122">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1f8be-123">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1f8be-123">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1f8be-124">600</span><span class="sxs-lookup"><span data-stu-id="1f8be-124">600</span></span>  <br/> |<span data-ttu-id="1f8be-125">TXT</span><span class="sxs-lookup"><span data-stu-id="1f8be-125">TXT</span></span>  <br/> |<span data-ttu-id="1f8be-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1f8be-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1f8be-127">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="1f8be-127">**Note:** This is an example.</span></span> <span data-ttu-id="1f8be-128">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="1f8be-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="1f8be-129">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="1f8be-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="1f8be-131">选择 **"创建记录"。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-131">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="1f8be-133">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="1f8be-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1f8be-134">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="1f8be-135">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="1f8be-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1f8be-136">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="1f8be-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1f8be-137">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="1f8be-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1f8be-138">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="1f8be-138">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1f8be-139">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="1f8be-139">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1f8be-p104">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1f8be-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1f8be-143">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="1f8be-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1f8be-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1f8be-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="1f8be-p105">若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。系统会提示你先进行登录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="1f8be-148">在" **区域级别服务** "页上，为要编辑的域选择 **"Dyn** 标准 DNS 服务"。</span><span class="sxs-lookup"><span data-stu-id="1f8be-148">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1f8be-149">在域的"DNS"页面上，选择 **"首选项"。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-149">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="1f8be-150">选择 **启用专家接口**。</span><span class="sxs-lookup"><span data-stu-id="1f8be-150">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="1f8be-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1f8be-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1f8be-152">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1f8be-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1f8be-153">**主机**</span><span class="sxs-lookup"><span data-stu-id="1f8be-153">**Host**</span></span>|<span data-ttu-id="1f8be-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1f8be-154">**TTL**</span></span>|<span data-ttu-id="1f8be-155">**类型**</span><span class="sxs-lookup"><span data-stu-id="1f8be-155">**Type**</span></span>|<span data-ttu-id="1f8be-156">**数据**</span><span class="sxs-lookup"><span data-stu-id="1f8be-156">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1f8be-157">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1f8be-157">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1f8be-158">600</span><span class="sxs-lookup"><span data-stu-id="1f8be-158">600</span></span>  <br/> |<span data-ttu-id="1f8be-159">MX</span><span class="sxs-lookup"><span data-stu-id="1f8be-159">MX</span></span>  <br/> |<span data-ttu-id="1f8be-160">10  *\<domain-key\>*  .mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="1f8be-160">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="1f8be-161">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-161">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="1f8be-p106">**10** 是 MX 优先级值。将其添加到 MX 值的开头，使用一个空格将其与其余部分隔开。  </span><span class="sxs-lookup"><span data-stu-id="1f8be-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="1f8be-164">**注意：** 从  *\<domain-key\>*  Microsoft 帐户获取你的信息。</span><span class="sxs-lookup"><span data-stu-id="1f8be-164">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="1f8be-165">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="1f8be-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="1f8be-166">有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="1f8be-166">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
    ![Dyn-BP-Configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="1f8be-168">选择 **"创建记录"。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-168">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="1f8be-170">如果存在任何其他 MX 记录，通过选中" **删除**"列中这些记录的复选框将其删除。</span><span class="sxs-lookup"><span data-stu-id="1f8be-170">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![Dyn-BP-Configure-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="1f8be-172">选择 **"应用更改"。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-172">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1f8be-174">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="1f8be-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1f8be-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1f8be-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="1f8be-p108">若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。系统会提示你先进行登录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="1f8be-179">在" **区域级别服务** "页上，为要编辑的域选择 **"Dyn** 标准 DNS 服务"。</span><span class="sxs-lookup"><span data-stu-id="1f8be-179">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1f8be-180">在域 **的"DNS"** 页面上，选择 **"首选项"。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-180">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="1f8be-181">选择 **启用专家接口**。</span><span class="sxs-lookup"><span data-stu-id="1f8be-181">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="1f8be-182">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="1f8be-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="1f8be-183">在" **添加 DNS 记录**"部分中新记录的框内，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="1f8be-183">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="1f8be-184">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="1f8be-184">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1f8be-185">**主机**</span><span class="sxs-lookup"><span data-stu-id="1f8be-185">**Host**</span></span>|<span data-ttu-id="1f8be-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1f8be-186">**TTL**</span></span>|<span data-ttu-id="1f8be-187">**类型**</span><span class="sxs-lookup"><span data-stu-id="1f8be-187">**Type**</span></span>|<span data-ttu-id="1f8be-188">**数据**</span><span class="sxs-lookup"><span data-stu-id="1f8be-188">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1f8be-189">自动发现</span><span class="sxs-lookup"><span data-stu-id="1f8be-189">autodiscover</span></span>  <br/> |<span data-ttu-id="1f8be-190">600</span><span class="sxs-lookup"><span data-stu-id="1f8be-190">600</span></span>  <br/> |<span data-ttu-id="1f8be-191">CNAME</span><span class="sxs-lookup"><span data-stu-id="1f8be-191">CNAME</span></span>  <br/> |<span data-ttu-id="1f8be-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1f8be-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="1f8be-193">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-193">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1f8be-194">sip</span><span class="sxs-lookup"><span data-stu-id="1f8be-194">sip</span></span>  <br/> |<span data-ttu-id="1f8be-195">600</span><span class="sxs-lookup"><span data-stu-id="1f8be-195">600</span></span>  <br/> |<span data-ttu-id="1f8be-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="1f8be-196">CNAME</span></span>  <br/> |<span data-ttu-id="1f8be-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1f8be-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1f8be-198">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-198">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1f8be-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1f8be-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1f8be-200">600</span><span class="sxs-lookup"><span data-stu-id="1f8be-200">600</span></span>  <br/> |<span data-ttu-id="1f8be-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="1f8be-201">CNAME</span></span>  <br/> |<span data-ttu-id="1f8be-202">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1f8be-202">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1f8be-203">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-203">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1f8be-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1f8be-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1f8be-205">600</span><span class="sxs-lookup"><span data-stu-id="1f8be-205">600</span></span>  <br/> |<span data-ttu-id="1f8be-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="1f8be-206">CNAME</span></span>  <br/> |<span data-ttu-id="1f8be-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="1f8be-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="1f8be-208">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="1f8be-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1f8be-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1f8be-210">600</span><span class="sxs-lookup"><span data-stu-id="1f8be-210">600</span></span>  <br/> |<span data-ttu-id="1f8be-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="1f8be-211">CNAME</span></span>  <br/> |<span data-ttu-id="1f8be-212">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1f8be-212">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="1f8be-213">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-213">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-Configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="1f8be-215">选择 **"创建记录"。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-215">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="1f8be-217">添加其他五条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-217">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="1f8be-218">在" **添加 DNS 记录** "部分，使用表中下一行的值创建记录，然后再次选择" **创建记录** "以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-218">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="1f8be-219">重复该过程，直到创建完全部 6 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1f8be-220">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="1f8be-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1f8be-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1f8be-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f8be-222">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="1f8be-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1f8be-223">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="1f8be-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1f8be-224">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1f8be-225">相反，将所需的 Microsoft 值添加到当前记录，以便你有一个  *包含这*  两组值的 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="1f8be-p110">若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。系统会提示你先进行登录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="1f8be-229">在" **区域级别服务** "页上，为要编辑的域选择 **"Dyn** 标准 DNS 服务"。</span><span class="sxs-lookup"><span data-stu-id="1f8be-229">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1f8be-230">在域 **的"DNS"** 页面上，选择 **"首选项"。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-230">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="1f8be-231">选择 **启用专家接口**。</span><span class="sxs-lookup"><span data-stu-id="1f8be-231">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="1f8be-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="1f8be-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="1f8be-233">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="1f8be-233">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1f8be-234">**主机**</span><span class="sxs-lookup"><span data-stu-id="1f8be-234">**Host**</span></span>|<span data-ttu-id="1f8be-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1f8be-235">**TTL**</span></span>|<span data-ttu-id="1f8be-236">**类型**</span><span class="sxs-lookup"><span data-stu-id="1f8be-236">**Type**</span></span>|<span data-ttu-id="1f8be-237">**数据**</span><span class="sxs-lookup"><span data-stu-id="1f8be-237">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1f8be-238">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="1f8be-238">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="1f8be-239">600</span><span class="sxs-lookup"><span data-stu-id="1f8be-239">600</span></span>  <br/> |<span data-ttu-id="1f8be-240">TXT</span><span class="sxs-lookup"><span data-stu-id="1f8be-240">TXT</span></span>  <br/> |<span data-ttu-id="1f8be-241">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1f8be-241">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1f8be-242">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="1f8be-242">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="1f8be-244">选择 **"创建记录"。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-244">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1f8be-246">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="1f8be-246">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1f8be-247"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1f8be-247"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="1f8be-248">若要开始，请使用[此链接](https://account.dyn.com/dns/)转到你在 Dyn.com 上的域页面。</span><span class="sxs-lookup"><span data-stu-id="1f8be-248">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="1f8be-249">系统将提示你先登录</span><span class="sxs-lookup"><span data-stu-id="1f8be-249">You'll be prompted to login first</span></span> 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="1f8be-251">在" **区域级别服务** "页上，为要编辑的域选择 **"Dyn** 标准 DNS 服务"。</span><span class="sxs-lookup"><span data-stu-id="1f8be-251">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="1f8be-252">在域 **的"DNS"** 页面上，选择 **"首选项"。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-252">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="1f8be-253">选择 **启用专家接口**。</span><span class="sxs-lookup"><span data-stu-id="1f8be-253">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="1f8be-254">添加两条 SRV 记录中的第一条。</span><span class="sxs-lookup"><span data-stu-id="1f8be-254">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="1f8be-255">在" **添加 DNS 记录**"部分中新记录的框内，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="1f8be-255">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="1f8be-256">（从下拉列表中选择" **类型**"值。）</span><span class="sxs-lookup"><span data-stu-id="1f8be-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="1f8be-257">**主机**</span><span class="sxs-lookup"><span data-stu-id="1f8be-257">**Host**</span></span>|<span data-ttu-id="1f8be-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1f8be-258">**TTL**</span></span>|<span data-ttu-id="1f8be-259">**类型**</span><span class="sxs-lookup"><span data-stu-id="1f8be-259">**Type**</span></span>|<span data-ttu-id="1f8be-260">**数据**</span><span class="sxs-lookup"><span data-stu-id="1f8be-260">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1f8be-261">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="1f8be-261">_sip._tls</span></span>|<span data-ttu-id="1f8be-262">600</span><span class="sxs-lookup"><span data-stu-id="1f8be-262">600</span></span>|<span data-ttu-id="1f8be-263">SRV</span><span class="sxs-lookup"><span data-stu-id="1f8be-263">SRV</span></span>|<span data-ttu-id="1f8be-264">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1f8be-264">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="1f8be-265">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-265">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="1f8be-266">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="1f8be-266">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="1f8be-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="1f8be-267">_sipfederationtls._tcp</span></span>|<span data-ttu-id="1f8be-268">600</span><span class="sxs-lookup"><span data-stu-id="1f8be-268">600</span></span>|<span data-ttu-id="1f8be-269">SRV</span><span class="sxs-lookup"><span data-stu-id="1f8be-269">SRV</span></span>|<span data-ttu-id="1f8be-270">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1f8be-270">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="1f8be-271">**此值必须以句点 (.) 结尾。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-271">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="1f8be-272">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="1f8be-272">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="1f8be-274">选择 **"创建记录"。**</span><span class="sxs-lookup"><span data-stu-id="1f8be-274">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="1f8be-276">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="1f8be-277">在" **添加 DNS 记录** "部分，使用表中第二行的值创建记录，然后再次选择"创建 **记录** "以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="1f8be-277">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="1f8be-p114">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1f8be-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
