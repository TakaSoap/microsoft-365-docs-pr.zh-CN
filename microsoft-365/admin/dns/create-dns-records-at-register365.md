---
title: 在 Register365 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: 了解如何验证您的域，并在 Register365 for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 056d4dbf923c49b0586ed556f1844cd3b29abe75
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048887"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a><span data-ttu-id="d444d-103">在 Register365 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="d444d-103">Create DNS records at Register365 for Microsoft</span></span>

 <span data-ttu-id="d444d-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="d444d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d444d-105">如果 Register365 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="d444d-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="d444d-106">下面是要添加的主要记录：</span><span class="sxs-lookup"><span data-stu-id="d444d-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="d444d-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="d444d-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="d444d-108">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d444d-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="d444d-109">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="d444d-109">Add the six CNAME records that are required for Microsoft</span></span>](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="d444d-110">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="d444d-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="d444d-111">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="d444d-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="d444d-112">在 Microsoft 中添加这些记录后，您的域将设置为使用 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="d444d-112">After you add these records at Microsoft, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="d444d-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d444d-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d444d-116">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="d444d-116">Add a TXT record for verification</span></span>
<span data-ttu-id="d444d-117"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d444d-117"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d444d-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="d444d-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d444d-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="d444d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d444d-p104">要开始，请使用[此链接](https://admin.register365.com/dns/)转到您在 Register365 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="d444d-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    !['控制面板'登录页面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="d444d-125">在" **仪表板**"页面上，找到要更新的域的名称，然后从下拉列表中选择" **DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="d444d-125">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d444d-126">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="d444d-126">(You may have to scroll down.)</span></span>
    
    ![选择列表中的 DNS 设置](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="d444d-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d444d-128">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d444d-129">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d444d-129">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="d444d-130">（如果需要添加行，请选择 "**添加/CNAME 记录（+）**"。</span><span class="sxs-lookup"><span data-stu-id="d444d-130">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="d444d-131">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="d444d-131">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d444d-132">**主机名**</span><span class="sxs-lookup"><span data-stu-id="d444d-132">**Host name**</span></span>|<span data-ttu-id="d444d-133">**类型**</span><span class="sxs-lookup"><span data-stu-id="d444d-133">**Type**</span></span>|<span data-ttu-id="d444d-134">**结果**</span><span class="sxs-lookup"><span data-stu-id="d444d-134">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d444d-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d444d-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d444d-136">TXT</span><span class="sxs-lookup"><span data-stu-id="d444d-136">TXT</span></span>  <br/> |<span data-ttu-id="d444d-137">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d444d-137">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d444d-138">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="d444d-138">**Note:** This is an example.</span></span> <span data-ttu-id="d444d-139">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="d444d-139">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="d444d-140">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="d444d-140">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![在 "添加/修改 DNS 区域" 页上输入值](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="d444d-142">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d444d-142">Select **Save**.</span></span>
    
    <span data-ttu-id="d444d-143">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d444d-143">(You may have to scroll down.)</span></span>
    
    ![选择 "保存"](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="d444d-145">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="d444d-145">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d444d-146">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="d444d-146">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d444d-147">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="d444d-147">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d444d-148">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="d444d-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d444d-149">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="d444d-149">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d444d-150">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="d444d-150">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d444d-151">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="d444d-151">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d444d-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d444d-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d444d-155">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d444d-155">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d444d-156"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d444d-156"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d444d-p107">要开始，请使用[此链接](https://admin.register365.com/dns/)转到您在 Register365 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="d444d-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    !['控制面板'登录页面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="d444d-160">在" **仪表板**"页面上，找到要更新的域的名称，然后从下拉列表中选择" **DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="d444d-160">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d444d-161">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="d444d-161">(You may have to scroll down.)</span></span>
    
    ![选择列表中的 DNS 设置](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="d444d-163">在 "**添加/修改 DNS 区域**" 页上的 "**邮件交换记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="d444d-163">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d444d-164">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="d444d-164">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d444d-165">**主机名**</span><span class="sxs-lookup"><span data-stu-id="d444d-165">**Host name**</span></span>|<span data-ttu-id="d444d-166">**优先级**</span><span class="sxs-lookup"><span data-stu-id="d444d-166">**Priority**</span></span>|<span data-ttu-id="d444d-167">**结果**</span><span class="sxs-lookup"><span data-stu-id="d444d-167">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d444d-168">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="d444d-168">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d444d-169">1</span><span class="sxs-lookup"><span data-stu-id="d444d-169">1</span></span>  <br/> <span data-ttu-id="d444d-170">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="d444d-170">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="d444d-171">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d444d-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d444d-172">**注意：** 从你的 Microsoft 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="d444d-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="d444d-173">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="d444d-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![在 "添加/修改 DNS 区域" 页上输入值](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="d444d-175">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d444d-175">Select **Save**.</span></span>
    
    <span data-ttu-id="d444d-176">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d444d-176">(You may have to scroll down.)</span></span>
    
    ![选择 "保存"](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="d444d-178">如果 "**邮件交换记录**" 部分中有任何其他 MX 记录，请选择该记录，然后按键盘上的**delete**键将其删除。</span><span class="sxs-lookup"><span data-stu-id="d444d-178">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![删除 "邮件交换记录" 部分中的记录](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="d444d-180">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d444d-180">Select **Save**.</span></span>
    
    <span data-ttu-id="d444d-181">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d444d-181">(You may have to scroll down.)</span></span>
    
    ![选择 "保存"](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d444d-183">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="d444d-183">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d444d-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d444d-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d444d-p109">要开始，请使用[此链接](https://admin.register365.com/dns/)转到您在 Register365 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="d444d-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    !['控制面板'登录页面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="d444d-188">在" **仪表板**"页面上，找到要更新的域的名称，然后从下拉列表中选择" **DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="d444d-188">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d444d-189">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="d444d-189">(You may have to scroll down.)</span></span>
    
    ![选择列表中的 DNS 设置](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="d444d-191">在 "**添加/修改 DNS 区域**" 页上的 " **A，CNAME，AAAA，TXT，NS 记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="d444d-191">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d444d-192">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d444d-192">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="d444d-193">（如果需要添加行，请选择 "**添加/CNAME 记录（+）**"。</span><span class="sxs-lookup"><span data-stu-id="d444d-193">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="d444d-194">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d444d-194">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d444d-195">主机名 \* \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="d444d-195">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="d444d-196">键入 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="d444d-196">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="d444d-197">结果 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="d444d-197">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d444d-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d444d-198">autodiscover</span></span>  <br/> |<span data-ttu-id="d444d-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="d444d-199">CNAME</span></span>  <br/> |<span data-ttu-id="d444d-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d444d-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d444d-201">sip</span><span class="sxs-lookup"><span data-stu-id="d444d-201">sip</span></span>  <br/> |<span data-ttu-id="d444d-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="d444d-202">CNAME</span></span>  <br/> |<span data-ttu-id="d444d-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d444d-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d444d-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d444d-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d444d-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="d444d-205">CNAME</span></span>  <br/> |<span data-ttu-id="d444d-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d444d-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d444d-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d444d-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d444d-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="d444d-208">CNAME</span></span>  <br/> |<span data-ttu-id="d444d-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d444d-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="d444d-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d444d-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d444d-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="d444d-211">CNAME</span></span>  <br/> |<span data-ttu-id="d444d-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d444d-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![在 "添加/修改 DNS 区域" 页上输入值](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="d444d-214">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d444d-214">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d444d-216">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="d444d-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d444d-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d444d-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d444d-218">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="d444d-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d444d-219">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="d444d-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d444d-220">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="d444d-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d444d-221">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="d444d-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="d444d-p111">要开始，请使用[此链接](https://admin.register365.com/dns/)转到您在 Register365 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="d444d-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    !['控制面板'登录页面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="d444d-225">在" **仪表板**"页面上，找到要更新的域的名称，然后从下拉列表中选择" **DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="d444d-225">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d444d-226">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="d444d-226">(You may have to scroll down.)</span></span>
    
    ![选择列表中的 DNS 设置](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="d444d-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d444d-228">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d444d-229">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="d444d-229">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="d444d-230">（如果需要添加行，请选择 "**添加/CNAME 记录（+）**"。</span><span class="sxs-lookup"><span data-stu-id="d444d-230">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="d444d-231">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="d444d-231">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d444d-232">**主机名**</span><span class="sxs-lookup"><span data-stu-id="d444d-232">**Host name**</span></span>|<span data-ttu-id="d444d-233">**类型**</span><span class="sxs-lookup"><span data-stu-id="d444d-233">**Type**</span></span>|<span data-ttu-id="d444d-234">**结果**</span><span class="sxs-lookup"><span data-stu-id="d444d-234">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d444d-235">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="d444d-235">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="d444d-236">TXT</span><span class="sxs-lookup"><span data-stu-id="d444d-236">TXT</span></span>  <br/> |<span data-ttu-id="d444d-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d444d-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="d444d-238">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="d444d-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![在 "添加/修改 DNS 区域" 页上输入值](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="d444d-240">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d444d-240">Select **Save**.</span></span>
    
    <span data-ttu-id="d444d-241">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d444d-241">(You may have to scroll down.)</span></span>
    
    ![选择 "保存"](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d444d-243">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="d444d-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d444d-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d444d-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d444d-p112">要开始，请使用[此链接](https://admin.register365.com/dns/)转到您在 Register365 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="d444d-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    !['控制面板'登录页面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="d444d-248">在" **仪表板**"页面上，找到要更新的域的名称，然后从下拉列表中选择" **DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="d444d-248">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="d444d-249">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="d444d-249">(You may have to scroll down.)</span></span>
    
    ![选择列表中的 DNS 设置](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="d444d-251">在 "**添加/修改 DNS 区域**" 页上的 "**服务记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="d444d-251">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="d444d-252">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d444d-252">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="d444d-253">**名称**</span><span class="sxs-lookup"><span data-stu-id="d444d-253">**Name**</span></span>|<span data-ttu-id="d444d-254">**优先级**</span><span class="sxs-lookup"><span data-stu-id="d444d-254">**Priority**</span></span>|<span data-ttu-id="d444d-255">**权重**</span><span class="sxs-lookup"><span data-stu-id="d444d-255">**Weight**</span></span>|<span data-ttu-id="d444d-256">**端口**</span><span class="sxs-lookup"><span data-stu-id="d444d-256">**Port**</span></span>|<span data-ttu-id="d444d-257">**结果**</span><span class="sxs-lookup"><span data-stu-id="d444d-257">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d444d-258">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="d444d-258">_sip._tls</span></span>  <br/> |<span data-ttu-id="d444d-259">100</span><span class="sxs-lookup"><span data-stu-id="d444d-259">100</span></span>  <br/> |<span data-ttu-id="d444d-260">1</span><span class="sxs-lookup"><span data-stu-id="d444d-260">1</span></span>  <br/> |<span data-ttu-id="d444d-261">443</span><span class="sxs-lookup"><span data-stu-id="d444d-261">443</span></span>  <br/> |<span data-ttu-id="d444d-262">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d444d-262">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d444d-263">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="d444d-263">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="d444d-264">100</span><span class="sxs-lookup"><span data-stu-id="d444d-264">100</span></span>  <br/> |<span data-ttu-id="d444d-265">1</span><span class="sxs-lookup"><span data-stu-id="d444d-265">1</span></span>  <br/> |<span data-ttu-id="d444d-266">5061</span><span class="sxs-lookup"><span data-stu-id="d444d-266">5061</span></span>  <br/> |<span data-ttu-id="d444d-267">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d444d-267">sipfed.online.lync.com</span></span>  <br/> |
   
    ![在 "服务记录" 部分中输入值](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="d444d-269">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d444d-269">Select **Save**.</span></span>
    
    <span data-ttu-id="d444d-270">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="d444d-270">(You may have to scroll down.)</span></span>
    
    ![选择 "保存"](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="d444d-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d444d-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
