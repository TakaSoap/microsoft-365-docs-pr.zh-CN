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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: 了解如何验证你的域并为 Microsoft 的悬停时设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 74662f37c3f72f02767f2434d9b251e3bd37ff1b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400421"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="d3066-103">在 Microsoft 悬停时创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="d3066-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="d3066-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="d3066-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d3066-105">如果悬停是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="d3066-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="d3066-106">在悬停时添加这些记录后，您的域将设置为与 Microsoft 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="d3066-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="d3066-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d3066-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d3066-110">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="d3066-110">Add a TXT record for verification</span></span>
<span data-ttu-id="d3066-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d3066-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d3066-p102">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="d3066-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3066-p103">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="d3066-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="d3066-116">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d3066-116">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d3066-p104">若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="d3066-p104">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="d3066-120">在 "**管理您的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="d3066-120">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="d3066-122">选择 " **DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d3066-122">Select the **DNS** tab.</span></span> 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="d3066-124">选择 "**添加新**"。</span><span class="sxs-lookup"><span data-stu-id="d3066-124">Select **Add New**.</span></span>
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="d3066-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d3066-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="d3066-127">主机名</span><span class="sxs-lookup"><span data-stu-id="d3066-127">Hostname</span></span>  <br/> |<span data-ttu-id="d3066-128">记录类型</span><span class="sxs-lookup"><span data-stu-id="d3066-128">Record Type</span></span>  <br/> |<span data-ttu-id="d3066-129">值</span><span class="sxs-lookup"><span data-stu-id="d3066-129">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="d3066-130">TXT</span><span class="sxs-lookup"><span data-stu-id="d3066-130">TXT</span></span>  <br/> |<span data-ttu-id="d3066-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d3066-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d3066-132">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="d3066-132">**Note:** This is an example.</span></span> <span data-ttu-id="d3066-133">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="d3066-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="d3066-134">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="d3066-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![键入或复制并粘贴 DNS 值](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="d3066-136">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d3066-136">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="d3066-138">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="d3066-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d3066-139">在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="d3066-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="d3066-140">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="d3066-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d3066-141">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="d3066-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d3066-142">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="d3066-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d3066-143">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="d3066-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d3066-144">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="d3066-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d3066-p106">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d3066-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d3066-148">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d3066-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d3066-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d3066-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="d3066-150">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d3066-150">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d3066-p107">若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="d3066-p107">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="d3066-154">在 "**管理您的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="d3066-154">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="d3066-156">选择 " **DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d3066-156">Select the **DNS** tab.</span></span> 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="d3066-158">选择 "**添加新**"。</span><span class="sxs-lookup"><span data-stu-id="d3066-158">Select **Add New**.</span></span>
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="d3066-160">在新记录的框中，选择**记录类型**的 " **MX** "，然后键入或复制并粘贴下表中的值。</span><span class="sxs-lookup"><span data-stu-id="d3066-160">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="d3066-161">**主机名**</span><span class="sxs-lookup"><span data-stu-id="d3066-161">**Hostname**</span></span>|<span data-ttu-id="d3066-162">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="d3066-162">**Record Type**</span></span>|<span data-ttu-id="d3066-163">**Priority**</span><span class="sxs-lookup"><span data-stu-id="d3066-163">**Priority**</span></span>|<span data-ttu-id="d3066-164">**主机名**</span><span class="sxs-lookup"><span data-stu-id="d3066-164">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d3066-165">MX</span><span class="sxs-lookup"><span data-stu-id="d3066-165">MX</span></span>  <br/> |<span data-ttu-id="d3066-166">0</span><span class="sxs-lookup"><span data-stu-id="d3066-166">0</span></span>  <br/> <span data-ttu-id="d3066-167">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="d3066-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="d3066-168">*\<domain-key\>*。 mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d3066-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d3066-169">\**注意：\*\*\*\<domain-key\>* 从你的 Microsoft 帐户获取你的。</span><span class="sxs-lookup"><span data-stu-id="d3066-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="d3066-170">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="d3066-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![键入或复制并粘贴 DNS 值](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="d3066-172">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d3066-172">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="d3066-174">如果有任何其他 MX 记录，请使用以下两步过程删除每个：</span><span class="sxs-lookup"><span data-stu-id="d3066-174">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="d3066-175">首先，鼠标移要删除的记录，选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="d3066-175">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![鼠标悬停并选择 "删除"](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="d3066-177">其次，选择 **"是"** 以确认每次删除。</span><span class="sxs-lookup"><span data-stu-id="d3066-177">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![选择 "是" 以确认删除](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="d3066-179">重复此过程，直到删除了之前在此过程中添加的 MX 记录之外的所有 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="d3066-179">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d3066-180">添加 Microsoft 所需的 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="d3066-180">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d3066-181"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d3066-181"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="d3066-182">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d3066-182">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d3066-p109">若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="d3066-p109">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="d3066-186">在 "**管理您的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="d3066-186">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="d3066-188">选择 " **DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d3066-188">Select the **DNS** tab.</span></span> 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="d3066-190">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="d3066-190">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="d3066-191">选择 "**添加新**"。</span><span class="sxs-lookup"><span data-stu-id="d3066-191">Select **Add New**.</span></span>
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="d3066-193">在新记录的空框中，为**记录类型**选择 " **CNAME** "，然后键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="d3066-193">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="d3066-194">**主机名**</span><span class="sxs-lookup"><span data-stu-id="d3066-194">**Hostname**</span></span>|<span data-ttu-id="d3066-195">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="d3066-195">**Record Type**</span></span>|<span data-ttu-id="d3066-196">**目标主机**</span><span class="sxs-lookup"><span data-stu-id="d3066-196">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d3066-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d3066-197">autodiscover</span></span>  <br/> |<span data-ttu-id="d3066-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="d3066-198">CNAME</span></span>  <br/> |<span data-ttu-id="d3066-199">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d3066-199">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d3066-200">sip</span><span class="sxs-lookup"><span data-stu-id="d3066-200">sip</span></span>  <br/> |<span data-ttu-id="d3066-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="d3066-201">CNAME</span></span>  <br/> |<span data-ttu-id="d3066-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d3066-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d3066-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d3066-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d3066-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="d3066-204">CNAME</span></span>  <br/> |<span data-ttu-id="d3066-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d3066-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d3066-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d3066-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d3066-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="d3066-207">CNAME</span></span>  <br/> |<span data-ttu-id="d3066-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d3066-208">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="d3066-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d3066-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d3066-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="d3066-210">CNAME</span></span>  <br/> |<span data-ttu-id="d3066-211">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d3066-211">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![键入或复制并粘贴 DNS 值](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="d3066-213">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d3066-213">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="d3066-215">使用前面的三个步骤和表中其他五行中的值，添加其他五个 CNAME 记录中的每个。</span><span class="sxs-lookup"><span data-stu-id="d3066-215">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d3066-216">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="d3066-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d3066-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d3066-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3066-218">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="d3066-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d3066-219">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="d3066-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d3066-220">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="d3066-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d3066-221">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="d3066-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="d3066-222">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d3066-222">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d3066-p111">若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="d3066-p111">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="d3066-226">在 "**管理您的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="d3066-226">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="d3066-228">选择 " **DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d3066-228">Select the **DNS** tab.</span></span> 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="d3066-230">选择 "**添加新**"。</span><span class="sxs-lookup"><span data-stu-id="d3066-230">Select **Add New**.</span></span>
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="d3066-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="d3066-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="d3066-233">**主机名**</span><span class="sxs-lookup"><span data-stu-id="d3066-233">**Hostname**</span></span>|<span data-ttu-id="d3066-234">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="d3066-234">**Record Type**</span></span>|<span data-ttu-id="d3066-235">**值**</span><span class="sxs-lookup"><span data-stu-id="d3066-235">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d3066-236">TXT</span><span class="sxs-lookup"><span data-stu-id="d3066-236">TXT</span></span>  <br/> |<span data-ttu-id="d3066-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d3066-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="d3066-238">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="d3066-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![键入或复制并粘贴 DNS 值](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="d3066-240">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d3066-240">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d3066-242">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="d3066-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d3066-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d3066-243"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="d3066-244">请按下列步骤操作或[观看视频](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d3066-244">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d3066-p112">若要开始，请使用[此链接](https://www.hover.com/domains)转到 Hover 上您的域页面。系统将会提示您首先登录。</span><span class="sxs-lookup"><span data-stu-id="d3066-p112">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.</span></span>
    
    ![登录](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="d3066-248">在 "**管理您的域**" 下，选择要编辑的域的名称。</span><span class="sxs-lookup"><span data-stu-id="d3066-248">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![选择域](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="d3066-250">选择 " **DNS** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d3066-250">Select the **DNS** tab.</span></span> 
    
    ![选择 "DNS" 选项卡](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="d3066-252">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="d3066-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="d3066-253">选择 "**添加新**"。</span><span class="sxs-lookup"><span data-stu-id="d3066-253">Select **Add New**.</span></span>
    
    ![选择 "添加新](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="d3066-255">在新记录的空框中，为**记录类型**选择 " **SRV** "，然后键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="d3066-255">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="d3066-256">**主机名**</span><span class="sxs-lookup"><span data-stu-id="d3066-256">**Hostname**</span></span>|<span data-ttu-id="d3066-257">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="d3066-257">**Record Type**</span></span>|<span data-ttu-id="d3066-258">**优先级**</span><span class="sxs-lookup"><span data-stu-id="d3066-258">**Priority**</span></span>|<span data-ttu-id="d3066-259">**权重**</span><span class="sxs-lookup"><span data-stu-id="d3066-259">**Weight**</span></span>|<span data-ttu-id="d3066-260">**端口**</span><span class="sxs-lookup"><span data-stu-id="d3066-260">**Port**</span></span>|<span data-ttu-id="d3066-261">**目标**</span><span class="sxs-lookup"><span data-stu-id="d3066-261">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d3066-262">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="d3066-262">_sip._tls</span></span>  <br/> |<span data-ttu-id="d3066-263">SRV</span><span class="sxs-lookup"><span data-stu-id="d3066-263">SRV</span></span>  <br/> |<span data-ttu-id="d3066-264">100</span><span class="sxs-lookup"><span data-stu-id="d3066-264">100</span></span>  <br/> |<span data-ttu-id="d3066-265">1 </span><span class="sxs-lookup"><span data-stu-id="d3066-265">1</span></span>  <br/> |<span data-ttu-id="d3066-266">443</span><span class="sxs-lookup"><span data-stu-id="d3066-266">443</span></span>  <br/> |<span data-ttu-id="d3066-267">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d3066-267">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d3066-268">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="d3066-268">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="d3066-269">SRV</span><span class="sxs-lookup"><span data-stu-id="d3066-269">SRV</span></span>  <br/> |<span data-ttu-id="d3066-270">100</span><span class="sxs-lookup"><span data-stu-id="d3066-270">100</span></span>  <br/> |<span data-ttu-id="d3066-271">1 </span><span class="sxs-lookup"><span data-stu-id="d3066-271">1</span></span>  <br/> |<span data-ttu-id="d3066-272">5061</span><span class="sxs-lookup"><span data-stu-id="d3066-272">5061</span></span>  <br/> |<span data-ttu-id="d3066-273">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d3066-273">sipfed.online.lync.com</span></span>  <br/> |
   
    ![键入或复制并粘贴 DNS 值](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="d3066-275">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d3066-275">Select **Save**.</span></span>
    
    ![选择 "保存"](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="d3066-277">使用前面的三个步骤和表中第二行的值，添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="d3066-277">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d3066-p113">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d3066-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
