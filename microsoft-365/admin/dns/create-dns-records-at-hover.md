---
title: 在 Microsoft 悬停时创建 DNS 记录
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: 了解如何验证你的域并为 Microsoft 的悬停时设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 328020dffe5d6549f7a0418a01d99b18ef9c5035
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629511"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="43455-103">在 Microsoft 悬停时创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="43455-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="43455-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="43455-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="43455-105">如果悬停是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="43455-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="43455-106">在悬停时添加这些记录后，您的域将设置为与 Microsoft 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="43455-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="43455-107">若要了解 Microsoft 相关网站的托管和 DNS，请参阅[将公共网站与 microsoft 结合使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)。</span><span class="sxs-lookup"><span data-stu-id="43455-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="43455-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="43455-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="43455-111">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="43455-111">Add a TXT record for verification</span></span>
<span data-ttu-id="43455-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="43455-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="43455-113">在将你的域用于 Microsoft 之前，我们必须确保你拥有此域。</span><span class="sxs-lookup"><span data-stu-id="43455-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="43455-114">你能够在域注册机构登录到你的帐户，并创建向 Microsoft 证明你拥有该域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="43455-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="43455-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="43455-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="43455-117">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="43455-117">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="43455-p104">若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="43455-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="43455-121">在 "**管理您的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="43455-121">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="43455-123">选择 " **DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="43455-123">Select the **DNS** tab.</span></span> 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="43455-125">选择 "**添加新**"。</span><span class="sxs-lookup"><span data-stu-id="43455-125">Select **Add New**.</span></span>
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="43455-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="43455-127">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="43455-128">主机名</span><span class="sxs-lookup"><span data-stu-id="43455-128">Hostname</span></span>  <br/> |<span data-ttu-id="43455-129">记录类型</span><span class="sxs-lookup"><span data-stu-id="43455-129">Record Type</span></span>  <br/> |<span data-ttu-id="43455-130">值</span><span class="sxs-lookup"><span data-stu-id="43455-130">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="43455-131">TXT</span><span class="sxs-lookup"><span data-stu-id="43455-131">TXT</span></span>  <br/> |<span data-ttu-id="43455-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="43455-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="43455-133">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="43455-133">**Note:** This is an example.</span></span> <span data-ttu-id="43455-134">从表中使用您的特定**目标或指向 "地址**" 值。</span><span class="sxs-lookup"><span data-stu-id="43455-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="43455-135">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="43455-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![键入或复制并粘贴 DNS 值](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="43455-137">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="43455-137">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="43455-139">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="43455-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="43455-140">现在您已在域注册机构的网站上添加了记录，您将返回到 Microsoft 365 并请求 Microsoft 365 查找该记录。</span><span class="sxs-lookup"><span data-stu-id="43455-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="43455-141">当 Microsoft 找到正确的 TXT 记录时，您的域将会得到验证。</span><span class="sxs-lookup"><span data-stu-id="43455-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="43455-142">在 Microsoft 管理中心，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="43455-142">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="43455-143">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="43455-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="43455-144">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="43455-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="43455-145">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="43455-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="43455-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="43455-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="43455-149">添加 MX 记录，以便你的域的电子邮件将发送给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="43455-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="43455-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="43455-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="43455-151">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="43455-151">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="43455-p107">若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="43455-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="43455-155">在 "**管理您的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="43455-155">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="43455-157">选择 " **DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="43455-157">Select the **DNS** tab.</span></span> 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="43455-159">选择 "**添加新**"。</span><span class="sxs-lookup"><span data-stu-id="43455-159">Select **Add New**.</span></span>
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="43455-161">在新记录的框中，选择**记录类型**的 " **MX** "，然后键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="43455-161">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="43455-162">**主机名**</span><span class="sxs-lookup"><span data-stu-id="43455-162">**Hostname**</span></span>|<span data-ttu-id="43455-163">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="43455-163">**Record Type**</span></span>|<span data-ttu-id="43455-164">**优先级**</span><span class="sxs-lookup"><span data-stu-id="43455-164">**Priority**</span></span>|<span data-ttu-id="43455-165">**主机名**</span><span class="sxs-lookup"><span data-stu-id="43455-165">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="43455-166">MX</span><span class="sxs-lookup"><span data-stu-id="43455-166">MX</span></span>  <br/> |<span data-ttu-id="43455-167">0</span><span class="sxs-lookup"><span data-stu-id="43455-167">0</span></span>  <br/> <span data-ttu-id="43455-168">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="43455-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="43455-169">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="43455-169">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="43455-170">**注意：** 从你的 Microsoft 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="43455-170">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="43455-171">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="43455-171">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![键入或复制并粘贴 DNS 值](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="43455-173">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="43455-173">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="43455-175">如果有任何其他 MX 记录，请使用以下两步过程删除每个：</span><span class="sxs-lookup"><span data-stu-id="43455-175">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="43455-176">首先，鼠标移要删除的记录，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="43455-176">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![鼠标悬停并选择 "删除"](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="43455-178">其次，选择 **"是"** 以确认每次删除。</span><span class="sxs-lookup"><span data-stu-id="43455-178">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![选择 "是" 以确认删除](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="43455-180">重复此过程，直到删除了之前在此过程中添加的 MX 记录之外的所有 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="43455-180">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="43455-181">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="43455-181">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="43455-182"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="43455-182"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="43455-183">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="43455-183">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="43455-p109">若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="43455-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="43455-187">在 "**管理您的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="43455-187">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="43455-189">选择 " **DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="43455-189">Select the **DNS** tab.</span></span> 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="43455-191">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="43455-191">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="43455-192">选择 "**添加新**"。</span><span class="sxs-lookup"><span data-stu-id="43455-192">Select **Add New**.</span></span>
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="43455-194">在新记录的空框中，为**记录类型**选择 " **CNAME** "，然后键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="43455-194">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="43455-195">**主机名**</span><span class="sxs-lookup"><span data-stu-id="43455-195">**Hostname**</span></span>|<span data-ttu-id="43455-196">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="43455-196">**Record Type**</span></span>|<span data-ttu-id="43455-197">**目标主机**</span><span class="sxs-lookup"><span data-stu-id="43455-197">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="43455-198">autodiscover</span><span class="sxs-lookup"><span data-stu-id="43455-198">autodiscover</span></span>  <br/> |<span data-ttu-id="43455-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="43455-199">CNAME</span></span>  <br/> |<span data-ttu-id="43455-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="43455-200">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="43455-201">sip</span><span class="sxs-lookup"><span data-stu-id="43455-201">sip</span></span>  <br/> |<span data-ttu-id="43455-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="43455-202">CNAME</span></span>  <br/> |<span data-ttu-id="43455-203">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="43455-203">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="43455-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="43455-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="43455-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="43455-205">CNAME</span></span>  <br/> |<span data-ttu-id="43455-206">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="43455-206">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="43455-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="43455-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="43455-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="43455-208">CNAME</span></span>  <br/> |<span data-ttu-id="43455-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="43455-209">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="43455-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="43455-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="43455-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="43455-211">CNAME</span></span>  <br/> |<span data-ttu-id="43455-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="43455-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![键入或复制并粘贴 DNS 值](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="43455-214">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="43455-214">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="43455-216">使用前面的三个步骤和表中其他五行中的值，添加其他五个 CNAME 记录中的每个。</span><span class="sxs-lookup"><span data-stu-id="43455-216">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="43455-217">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="43455-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="43455-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="43455-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="43455-219">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="43455-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="43455-220">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="43455-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="43455-221">如果你已有域的 SPF 记录，请不要为 Microsoft 创建一个新的。</span><span class="sxs-lookup"><span data-stu-id="43455-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="43455-222">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="43455-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="43455-223">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="43455-223">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="43455-p111">若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="43455-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="43455-227">在 "**管理您的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="43455-227">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="43455-229">选择 " **DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="43455-229">Select the **DNS** tab.</span></span> 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="43455-231">选择 "**添加新**"。</span><span class="sxs-lookup"><span data-stu-id="43455-231">Select **Add New**.</span></span>
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="43455-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="43455-233">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="43455-234">**主机名**</span><span class="sxs-lookup"><span data-stu-id="43455-234">**Hostname**</span></span>|<span data-ttu-id="43455-235">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="43455-235">**Record Type**</span></span>|<span data-ttu-id="43455-236">**值**</span><span class="sxs-lookup"><span data-stu-id="43455-236">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="43455-237">TXT</span><span class="sxs-lookup"><span data-stu-id="43455-237">TXT</span></span>  <br/> |<span data-ttu-id="43455-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="43455-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="43455-239">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="43455-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![键入或复制并粘贴 DNS 值](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="43455-241">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="43455-241">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="43455-243">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="43455-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="43455-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="43455-244"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="43455-245">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="43455-245">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="43455-p112">若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="43455-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="43455-249">在 "**管理您的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="43455-249">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="43455-251">选择 " **DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="43455-251">Select the **DNS** tab.</span></span> 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="43455-253">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="43455-253">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="43455-254">选择 "**添加新**"。</span><span class="sxs-lookup"><span data-stu-id="43455-254">Select **Add New**.</span></span>
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="43455-256">在新记录的空框中，为**记录类型**选择 " **SRV** "，然后键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="43455-256">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="43455-257">**主机名**</span><span class="sxs-lookup"><span data-stu-id="43455-257">**Hostname**</span></span>|<span data-ttu-id="43455-258">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="43455-258">**Record Type**</span></span>|<span data-ttu-id="43455-259">**优先级**</span><span class="sxs-lookup"><span data-stu-id="43455-259">**Priority**</span></span>|<span data-ttu-id="43455-260">**权重**</span><span class="sxs-lookup"><span data-stu-id="43455-260">**Weight**</span></span>|<span data-ttu-id="43455-261">**端口**</span><span class="sxs-lookup"><span data-stu-id="43455-261">**Port**</span></span>|<span data-ttu-id="43455-262">**目标**</span><span class="sxs-lookup"><span data-stu-id="43455-262">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="43455-263">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="43455-263">_sip._tls</span></span>  <br/> |<span data-ttu-id="43455-264">SRV</span><span class="sxs-lookup"><span data-stu-id="43455-264">SRV</span></span>  <br/> |<span data-ttu-id="43455-265">100</span><span class="sxs-lookup"><span data-stu-id="43455-265">100</span></span>  <br/> |<span data-ttu-id="43455-266">1</span><span class="sxs-lookup"><span data-stu-id="43455-266">1</span></span>  <br/> |<span data-ttu-id="43455-267">443</span><span class="sxs-lookup"><span data-stu-id="43455-267">443</span></span>  <br/> |<span data-ttu-id="43455-268">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="43455-268">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="43455-269">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="43455-269">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="43455-270">SRV</span><span class="sxs-lookup"><span data-stu-id="43455-270">SRV</span></span>  <br/> |<span data-ttu-id="43455-271">100</span><span class="sxs-lookup"><span data-stu-id="43455-271">100</span></span>  <br/> |<span data-ttu-id="43455-272">1</span><span class="sxs-lookup"><span data-stu-id="43455-272">1</span></span>  <br/> |<span data-ttu-id="43455-273">5061</span><span class="sxs-lookup"><span data-stu-id="43455-273">5061</span></span>  <br/> |<span data-ttu-id="43455-274">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="43455-274">sipfed.online.lync.com</span></span>  <br/> |
   
    ![键入或复制并粘贴 DNS 值](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="43455-276">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="43455-276">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="43455-278">使用前面的三个步骤和表中第二行的值，添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="43455-278">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="43455-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="43455-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
