---
title: 在 Register365 上为 Office 365 创建 DNS 记录
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: 了解如何在 Register365 for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 7f9398e14ea5280948829b263d4cd66d61fab682
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362847"
---
# <a name="create-dns-records-at-register365-for-office-365"></a><span data-ttu-id="571f2-103">在 Register365 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="571f2-103">Create DNS records at Register365 for Office 365</span></span>

 <span data-ttu-id="571f2-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="571f2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="571f2-105">如果 Register365 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="571f2-105">If Register365 is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="571f2-106">下面是要添加的主要记录：</span><span class="sxs-lookup"><span data-stu-id="571f2-106">These are the main records to add.</span></span>  
  
- [<span data-ttu-id="571f2-107">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="571f2-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="571f2-108">添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="571f2-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="571f2-109">添加 Office 365 所需的 6 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="571f2-109">Add the six CNAME records that are required for Office 365</span></span>](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="571f2-110">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="571f2-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="571f2-111">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="571f2-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="571f2-112">在 Office 365 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="571f2-112">After you add these records at Office 365, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="571f2-113">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="571f2-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="571f2-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="571f2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="571f2-117">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="571f2-117">Add a TXT record for verification</span></span>
<span data-ttu-id="571f2-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="571f2-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="571f2-p102">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="571f2-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="571f2-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="571f2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="571f2-p104">要开始，请使用[此链接](https://admin.register365.com/dns/)转到您在 Register365 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="571f2-p104">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    !['控制面板'登录页面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="571f2-126">在" **仪表板**"页面上，找到要更新的域的名称，然后从下拉列表中选择" **DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="571f2-126">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="571f2-127">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="571f2-127">(You may have to scroll down.)</span></span>
    
    ![选择列表中的 DNS 设置](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="571f2-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="571f2-129">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="571f2-130">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="571f2-130">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="571f2-131">（如果需要添加行，请选择 "**添加/CNAME 记录（+）**"。</span><span class="sxs-lookup"><span data-stu-id="571f2-131">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="571f2-132">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="571f2-132">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="571f2-133">**主机名**</span><span class="sxs-lookup"><span data-stu-id="571f2-133">**Host name**</span></span>|<span data-ttu-id="571f2-134">**类型**</span><span class="sxs-lookup"><span data-stu-id="571f2-134">**Type**</span></span>|<span data-ttu-id="571f2-135">**结果**</span><span class="sxs-lookup"><span data-stu-id="571f2-135">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="571f2-136">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="571f2-136">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="571f2-137">TXT</span><span class="sxs-lookup"><span data-stu-id="571f2-137">TXT</span></span>  <br/> |<span data-ttu-id="571f2-138">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="571f2-138">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="571f2-139">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="571f2-139">**Note:** This is an example.</span></span> <span data-ttu-id="571f2-140">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="571f2-140">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="571f2-141">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="571f2-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![在 "添加/修改 DNS 区域" 页上输入值](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. <span data-ttu-id="571f2-143">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="571f2-143">Select **Save**.</span></span>
    
    <span data-ttu-id="571f2-144">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="571f2-144">(You may have to scroll down.)</span></span>
    
    ![选择 "保存"](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. <span data-ttu-id="571f2-146">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="571f2-146">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="571f2-147">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="571f2-147">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="571f2-148">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="571f2-148">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="571f2-149">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="571f2-149">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="571f2-150">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="571f2-150">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="571f2-151">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="571f2-151">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="571f2-152">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="571f2-152">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="571f2-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="571f2-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="571f2-156">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="571f2-156">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="571f2-157"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="571f2-157"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="571f2-p107">要开始，请使用[此链接](https://admin.register365.com/dns/)转到您在 Register365 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="571f2-p107">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    !['控制面板'登录页面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="571f2-161">在" **仪表板**"页面上，找到要更新的域的名称，然后从下拉列表中选择" **DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="571f2-161">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="571f2-162">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="571f2-162">(You may have to scroll down.)</span></span>
    
    ![选择列表中的 DNS 设置](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="571f2-164">在 "**添加/修改 DNS 区域**" 页上的 "**邮件交换记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="571f2-164">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="571f2-165">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="571f2-165">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="571f2-166">**主机名**</span><span class="sxs-lookup"><span data-stu-id="571f2-166">**Host name**</span></span>|<span data-ttu-id="571f2-167">**优先级**</span><span class="sxs-lookup"><span data-stu-id="571f2-167">**Priority**</span></span>|<span data-ttu-id="571f2-168">**结果**</span><span class="sxs-lookup"><span data-stu-id="571f2-168">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="571f2-169">（将此字段留空。）</span><span class="sxs-lookup"><span data-stu-id="571f2-169">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="571f2-170">1</span><span class="sxs-lookup"><span data-stu-id="571f2-170">1</span></span>  <br/> <span data-ttu-id="571f2-171">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="571f2-171">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="571f2-172">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="571f2-172">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="571f2-173">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="571f2-173">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="571f2-174">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="571f2-174">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![在 "添加/修改 DNS 区域" 页上输入值](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. <span data-ttu-id="571f2-176">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="571f2-176">Select **Save**.</span></span>
    
    <span data-ttu-id="571f2-177">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="571f2-177">(You may have to scroll down.)</span></span>
    
    ![选择 "保存"](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. <span data-ttu-id="571f2-179">如果 "**邮件交换记录**" 部分中有任何其他 MX 记录，请选择该记录，然后按键盘上的**delete**键将其删除。</span><span class="sxs-lookup"><span data-stu-id="571f2-179">If there are any other MX records in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![删除 "邮件交换记录" 部分中的记录](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. <span data-ttu-id="571f2-181">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="571f2-181">Select **Save**.</span></span>
    
    <span data-ttu-id="571f2-182">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="571f2-182">(You may have to scroll down.)</span></span>
    
    ![选择 "保存"](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="571f2-184">添加 Office 365 所需的 6 条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="571f2-184">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="571f2-185"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="571f2-185"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="571f2-p109">要开始，请使用[此链接](https://admin.register365.com/dns/)转到您在 Register365 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="571f2-p109">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    !['控制面板'登录页面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="571f2-189">在" **仪表板**"页面上，找到要更新的域的名称，然后从下拉列表中选择" **DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="571f2-189">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="571f2-190">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="571f2-190">(You may have to scroll down.)</span></span>
    
    ![选择列表中的 DNS 设置](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="571f2-192">在 "**添加/修改 DNS 区域**" 页上的 " **A，CNAME，AAAA，TXT，NS 记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="571f2-192">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="571f2-193">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="571f2-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="571f2-194">（如果需要添加行，请选择 "**添加/CNAME 记录（+）**"。</span><span class="sxs-lookup"><span data-stu-id="571f2-194">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="571f2-195">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="571f2-195">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="571f2-196">主机名 \* \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="571f2-196">\*\*\*\*Host name\*\*\*\*</span></span>|<span data-ttu-id="571f2-197">键入 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="571f2-197">\*\*\*\*Type\*\*\*\*</span></span>|<span data-ttu-id="571f2-198">结果 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="571f2-198">\*\*\*\*Result\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="571f2-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="571f2-199">autodiscover</span></span>  <br/> |<span data-ttu-id="571f2-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="571f2-200">CNAME</span></span>  <br/> |<span data-ttu-id="571f2-201">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="571f2-201">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="571f2-202">sip</span><span class="sxs-lookup"><span data-stu-id="571f2-202">sip</span></span>  <br/> |<span data-ttu-id="571f2-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="571f2-203">CNAME</span></span>  <br/> |<span data-ttu-id="571f2-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="571f2-204">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="571f2-205">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="571f2-205">lyncdiscover</span></span>  <br/> |<span data-ttu-id="571f2-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="571f2-206">CNAME</span></span>  <br/> |<span data-ttu-id="571f2-207">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="571f2-207">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="571f2-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="571f2-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="571f2-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="571f2-209">CNAME</span></span>  <br/> |<span data-ttu-id="571f2-210">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="571f2-210">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="571f2-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="571f2-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="571f2-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="571f2-212">CNAME</span></span>  <br/> |<span data-ttu-id="571f2-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="571f2-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![在 "添加/修改 DNS 区域" 页上输入值](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. <span data-ttu-id="571f2-215">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="571f2-215">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="571f2-217">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="571f2-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="571f2-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="571f2-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="571f2-219">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="571f2-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="571f2-220">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="571f2-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="571f2-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="571f2-221">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="571f2-222">可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="571f2-222">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="571f2-p111">要开始，请使用[此链接](https://admin.register365.com/dns/)转到您在 Register365 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="571f2-p111">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    !['控制面板'登录页面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="571f2-226">在" **仪表板**"页面上，找到要更新的域的名称，然后从下拉列表中选择" **DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="571f2-226">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="571f2-227">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="571f2-227">(You may have to scroll down.)</span></span>
    
    ![选择列表中的 DNS 设置](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="571f2-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="571f2-229">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="571f2-230">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="571f2-230">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="571f2-231">（如果需要添加行，请选择 "**添加/CNAME 记录（+）**"。</span><span class="sxs-lookup"><span data-stu-id="571f2-231">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="571f2-232">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="571f2-232">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="571f2-233">**主机名**</span><span class="sxs-lookup"><span data-stu-id="571f2-233">**Host name**</span></span>|<span data-ttu-id="571f2-234">**类型**</span><span class="sxs-lookup"><span data-stu-id="571f2-234">**Type**</span></span>|<span data-ttu-id="571f2-235">**结果**</span><span class="sxs-lookup"><span data-stu-id="571f2-235">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="571f2-236">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="571f2-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="571f2-237">TXT</span><span class="sxs-lookup"><span data-stu-id="571f2-237">TXT</span></span>  <br/> |<span data-ttu-id="571f2-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="571f2-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="571f2-239">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="571f2-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![在 "添加/修改 DNS 区域" 页上输入值](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. <span data-ttu-id="571f2-241">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="571f2-241">Select **Save**.</span></span>
    
    <span data-ttu-id="571f2-242">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="571f2-242">(You may have to scroll down.)</span></span>
    
    ![选择 "保存"](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="571f2-244">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="571f2-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="571f2-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="571f2-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="571f2-p112">要开始，请使用[此链接](https://admin.register365.com/dns/)转到您在 Register365 上的域页面。 系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="571f2-p112">To get started, go to your domains page at Register365 by using [this link](https://admin.register365.com/dns/). You'll be prompted to log in first.</span></span>
    
    !['控制面板'登录页面](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. <span data-ttu-id="571f2-249">在" **仪表板**"页面上，找到要更新的域的名称，然后从下拉列表中选择" **DNS 设置**"。</span><span class="sxs-lookup"><span data-stu-id="571f2-249">On the **Dashboard** page, find the name of the domain that you're updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="571f2-250">（可能需要向下滚动。）</span><span class="sxs-lookup"><span data-stu-id="571f2-250">(You may have to scroll down.)</span></span>
    
    ![选择列表中的 DNS 设置](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. <span data-ttu-id="571f2-252">在 "**添加/修改 DNS 区域**" 页上的 "**服务记录**" 部分中，在新记录的框中，键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="571f2-252">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new records, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="571f2-253">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="571f2-253">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="571f2-254">**名称**</span><span class="sxs-lookup"><span data-stu-id="571f2-254">**Name**</span></span>|<span data-ttu-id="571f2-255">**优先级**</span><span class="sxs-lookup"><span data-stu-id="571f2-255">**Priority**</span></span>|<span data-ttu-id="571f2-256">**权重**</span><span class="sxs-lookup"><span data-stu-id="571f2-256">**Weight**</span></span>|<span data-ttu-id="571f2-257">**端口**</span><span class="sxs-lookup"><span data-stu-id="571f2-257">**Port**</span></span>|<span data-ttu-id="571f2-258">**结果**</span><span class="sxs-lookup"><span data-stu-id="571f2-258">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="571f2-259">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="571f2-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="571f2-260">100</span><span class="sxs-lookup"><span data-stu-id="571f2-260">100</span></span>  <br/> |<span data-ttu-id="571f2-261">1</span><span class="sxs-lookup"><span data-stu-id="571f2-261">1</span></span>  <br/> |<span data-ttu-id="571f2-262">443</span><span class="sxs-lookup"><span data-stu-id="571f2-262">443</span></span>  <br/> |<span data-ttu-id="571f2-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="571f2-263">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="571f2-264">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="571f2-264">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="571f2-265">100</span><span class="sxs-lookup"><span data-stu-id="571f2-265">100</span></span>  <br/> |<span data-ttu-id="571f2-266">1</span><span class="sxs-lookup"><span data-stu-id="571f2-266">1</span></span>  <br/> |<span data-ttu-id="571f2-267">5061</span><span class="sxs-lookup"><span data-stu-id="571f2-267">5061</span></span>  <br/> |<span data-ttu-id="571f2-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="571f2-268">sipfed.online.lync.com</span></span>  <br/> |
   
    ![在 "服务记录" 部分中输入值](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. <span data-ttu-id="571f2-270">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="571f2-270">Select **Save**.</span></span>
    
    <span data-ttu-id="571f2-271">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="571f2-271">(You may have to scroll down.)</span></span>
    
    ![选择 "保存"](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  <span data-ttu-id="571f2-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="571f2-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
