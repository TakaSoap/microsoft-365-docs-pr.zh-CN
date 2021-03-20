---
title: 在 Cloudflare 为 Microsoft 创建 DNS 记录
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 了解如何在 Cloudflare for Microsoft 中验证域并设置电子邮件、Skype for Business Online 和其他服务的 DNS 记录。
ms.openlocfilehash: 0a80cf059a3a69dcb8aa48251875410f35684286
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910374"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="f29f6-103">在 Cloudflare 为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="f29f6-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="f29f6-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="f29f6-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f29f6-105">如果 Cloudflare 是你的 DNS 托管提供商，请按照本文中的步骤验证域并设置电子邮件、Skype for Business Online 等的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="f29f6-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f29f6-106">在 Cloudflare 添加这些记录后，你的域将设置为使用 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="f29f6-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="f29f6-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f29f6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f29f6-110">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="f29f6-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="f29f6-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="f29f6-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f29f6-112">必须在购买和注册域的域注册机构中执行此过程。</span><span class="sxs-lookup"><span data-stu-id="f29f6-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="f29f6-113">注册 Cloudflare 时，你使用 Cloudflare 安装过程添加了域。</span><span class="sxs-lookup"><span data-stu-id="f29f6-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="f29f6-114">你添加的域是从 Cloudflare 或单独的域注册机构购买的。</span><span class="sxs-lookup"><span data-stu-id="f29f6-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="f29f6-115">若要在 Microsoft 365 中验证和创建域的 DNS 记录，首先需要更改域注册机构中的名称服务器，以便它们使用 Cloudflare 的名称服务器。</span><span class="sxs-lookup"><span data-stu-id="f29f6-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="f29f6-116">若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="f29f6-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="f29f6-117">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="f29f6-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="f29f6-118">使用下表中的值创建两个名称机记录，或编辑现有名称机记录，以便它们与这些值匹配。</span><span class="sxs-lookup"><span data-stu-id="f29f6-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="f29f6-119">首选名称服务器</span><span class="sxs-lookup"><span data-stu-id="f29f6-119">First nameserver</span></span>  <br/> |<span data-ttu-id="f29f6-120">使用 Cloudflare 提供的名称器值。</span><span class="sxs-lookup"><span data-stu-id="f29f6-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="f29f6-121">次要名称服务器</span><span class="sxs-lookup"><span data-stu-id="f29f6-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="f29f6-122">使用 Cloudflare 提供的名称器值。</span><span class="sxs-lookup"><span data-stu-id="f29f6-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="f29f6-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="f29f6-123">You should use at least two name server records.</span></span> <span data-ttu-id="f29f6-124">如果列出了任何其他名称服务器，您应该将其删除。</span><span class="sxs-lookup"><span data-stu-id="f29f6-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="f29f6-125">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f29f6-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f29f6-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="f29f6-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="f29f6-127">然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="f29f6-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f29f6-128">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="f29f6-128">Add a TXT record for verification</span></span>
<span data-ttu-id="f29f6-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f29f6-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f29f6-p105">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="f29f6-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f29f6-p106">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="f29f6-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f29f6-134">To get started， go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="f29f6-134">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="f29f6-135">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="f29f6-135">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="f29f6-136">在 **主页** 上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="f29f6-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="f29f6-137">在域 **的"** 概述"页面上，选择 **"DNS"。**</span><span class="sxs-lookup"><span data-stu-id="f29f6-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="f29f6-138">在 **"DNS 管理"** 页上，单击" **添加** 记录"，然后从下表中选择值。</span><span class="sxs-lookup"><span data-stu-id="f29f6-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="f29f6-139">类型</span><span class="sxs-lookup"><span data-stu-id="f29f6-139">Type</span></span> | <span data-ttu-id="f29f6-140">名称</span><span class="sxs-lookup"><span data-stu-id="f29f6-140">Name</span></span> | <span data-ttu-id="f29f6-141">自动 TTL</span><span class="sxs-lookup"><span data-stu-id="f29f6-141">Automatic TTL</span></span> | <span data-ttu-id="f29f6-142">内容</span><span class="sxs-lookup"><span data-stu-id="f29f6-142">Content</span></span> |
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="f29f6-143">TXT</span><span class="sxs-lookup"><span data-stu-id="f29f6-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="f29f6-144">30 分钟</span><span class="sxs-lookup"><span data-stu-id="f29f6-144">30 minutes</span></span>  <br/> |<span data-ttu-id="f29f6-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f29f6-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f29f6-146">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="f29f6-146">**Note:** This is an example.</span></span> <span data-ttu-id="f29f6-147">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="f29f6-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="f29f6-148">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="f29f6-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="f29f6-149">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f29f6-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="f29f6-150">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="f29f6-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f29f6-151">现在，你已在你的域注册机构网站添加了记录，你将返回到 Microsoft 并搜索该记录。</span><span class="sxs-lookup"><span data-stu-id="f29f6-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="f29f6-152">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="f29f6-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f29f6-153">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f29f6-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f29f6-154">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="f29f6-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f29f6-155">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="f29f6-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f29f6-156">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="f29f6-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f29f6-p109">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f29f6-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="f29f6-160">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="f29f6-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="f29f6-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f29f6-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f29f6-162">To get started， go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="f29f6-162">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="f29f6-163">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="f29f6-163">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="f29f6-164">在 **主页** 上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="f29f6-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="f29f6-165">在域 **的"** 概述"页面上，选择 **"DNS"。**</span><span class="sxs-lookup"><span data-stu-id="f29f6-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="f29f6-166">在 **"DNS 管理"** 页上，单击" **添加** 记录"，然后从下表中选择值。</span><span class="sxs-lookup"><span data-stu-id="f29f6-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    | <span data-ttu-id="f29f6-167">类型</span><span class="sxs-lookup"><span data-stu-id="f29f6-167">Type</span></span> | <span data-ttu-id="f29f6-168">名称</span><span class="sxs-lookup"><span data-stu-id="f29f6-168">Name</span></span> | <span data-ttu-id="f29f6-169">邮件服务器</span><span class="sxs-lookup"><span data-stu-id="f29f6-169">Mail server</span></span> | <span data-ttu-id="f29f6-170">优先级</span><span class="sxs-lookup"><span data-stu-id="f29f6-170">Priority</span></span> | <span data-ttu-id="f29f6-171">TTL</span><span class="sxs-lookup"><span data-stu-id="f29f6-171">TTL</span></span> |
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f29f6-172">MX</span><span class="sxs-lookup"><span data-stu-id="f29f6-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="f29f6-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f29f6-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="f29f6-174">**注意：** 从  *\<domain-key\>*  Microsoft 365 帐户获取你的。</span><span class="sxs-lookup"><span data-stu-id="f29f6-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   <span data-ttu-id="f29f6-175">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="f29f6-175">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span> |<span data-ttu-id="f29f6-176">1</span><span class="sxs-lookup"><span data-stu-id="f29f6-176">1</span></span>  <br/> <span data-ttu-id="f29f6-177">有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="f29f6-177">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/>|<span data-ttu-id="f29f6-178">30 分钟</span><span class="sxs-lookup"><span data-stu-id="f29f6-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="f29f6-179">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f29f6-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="f29f6-180">如果 **"MX** 记录"部分列出了任何其他 MX 记录，则通过选择"删除 X 记录" (**删除)** 删除它们。</span><span class="sxs-lookup"><span data-stu-id="f29f6-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="f29f6-181">在确认对话框中，选择 **"删除** "以确认所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f29f6-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="f29f6-182">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="f29f6-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="f29f6-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f29f6-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f29f6-184">To get started， go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="f29f6-184">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="f29f6-185">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="f29f6-185">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="f29f6-186">在 **主页** 上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="f29f6-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="f29f6-187">在域 **的"** 概述"页面上，选择 **"DNS"。**</span><span class="sxs-lookup"><span data-stu-id="f29f6-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="f29f6-188">添加五条 CNAME 记录中的第一条。</span><span class="sxs-lookup"><span data-stu-id="f29f6-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="f29f6-189">在 **"DNS 管理"** 页上，单击" **添加** 记录"，然后从下表中选择值。</span><span class="sxs-lookup"><span data-stu-id="f29f6-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    | <span data-ttu-id="f29f6-190">类型</span><span class="sxs-lookup"><span data-stu-id="f29f6-190">Type</span></span> | <span data-ttu-id="f29f6-191">名称</span><span class="sxs-lookup"><span data-stu-id="f29f6-191">Name</span></span> | <span data-ttu-id="f29f6-192">Target</span><span class="sxs-lookup"><span data-stu-id="f29f6-192">Target</span></span> | <span data-ttu-id="f29f6-193">TTL</span><span class="sxs-lookup"><span data-stu-id="f29f6-193">TTL</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f29f6-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="f29f6-194">CNAME</span></span>  <br/> |<span data-ttu-id="f29f6-195">自动发现</span><span class="sxs-lookup"><span data-stu-id="f29f6-195">autodiscover</span></span>  <br/> |<span data-ttu-id="f29f6-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f29f6-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="f29f6-197">30 分钟</span><span class="sxs-lookup"><span data-stu-id="f29f6-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="f29f6-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="f29f6-198">CNAME</span></span>  <br/> |<span data-ttu-id="f29f6-199">sip</span><span class="sxs-lookup"><span data-stu-id="f29f6-199">sip</span></span>  <br/> |<span data-ttu-id="f29f6-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f29f6-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="f29f6-201">30 分钟</span><span class="sxs-lookup"><span data-stu-id="f29f6-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="f29f6-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="f29f6-202">CNAME</span></span>  <br/> |<span data-ttu-id="f29f6-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f29f6-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f29f6-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f29f6-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="f29f6-205">30 分钟</span><span class="sxs-lookup"><span data-stu-id="f29f6-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="f29f6-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="f29f6-206">CNAME</span></span>  <br/> |<span data-ttu-id="f29f6-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f29f6-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f29f6-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f29f6-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="f29f6-209">30 分钟</span><span class="sxs-lookup"><span data-stu-id="f29f6-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="f29f6-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="f29f6-210">CNAME</span></span>  <br/> |<span data-ttu-id="f29f6-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f29f6-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f29f6-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f29f6-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="f29f6-213">30 分钟</span><span class="sxs-lookup"><span data-stu-id="f29f6-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="f29f6-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="f29f6-214">CNAME</span></span>  <br/> |<span data-ttu-id="f29f6-215">msoid</span><span class="sxs-lookup"><span data-stu-id="f29f6-215">msoid</span></span>  <br/> |<span data-ttu-id="f29f6-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="f29f6-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="f29f6-217">30 分钟</span><span class="sxs-lookup"><span data-stu-id="f29f6-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="f29f6-218">选择 **"DNS 流量** "图标 (橙色云更改为灰色) 以绕过 Cloudflare 服务器。</span><span class="sxs-lookup"><span data-stu-id="f29f6-218">Select the **DNS Traffic** icon (change orange cloud to grey) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="f29f6-219">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f29f6-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="f29f6-220">逐一添加其他 5 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="f29f6-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f29f6-221">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="f29f6-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f29f6-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f29f6-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f29f6-223">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="f29f6-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f29f6-224">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="f29f6-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f29f6-225">如果你的域已有 SPF 记录，请不要为 Microsoft 365 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="f29f6-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="f29f6-226">可以将所需的 Microsoft 365 值添加到当前记录，这样就拥有包含两组值的 *单个* SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="f29f6-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="f29f6-227">To get started， go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="f29f6-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="f29f6-228">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="f29f6-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="f29f6-229">在 **主页** 上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="f29f6-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="f29f6-230">在域 **的"** 概述"页面上，选择 **"DNS"。**</span><span class="sxs-lookup"><span data-stu-id="f29f6-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="f29f6-231">在 **"DNS 管理"** 页上，单击" **添加** 记录"，然后从下表中选择值。</span><span class="sxs-lookup"><span data-stu-id="f29f6-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    | <span data-ttu-id="f29f6-232">类型</span><span class="sxs-lookup"><span data-stu-id="f29f6-232">Type</span></span> | <span data-ttu-id="f29f6-233">名称</span><span class="sxs-lookup"><span data-stu-id="f29f6-233">Name</span></span> | <span data-ttu-id="f29f6-234">TTL</span><span class="sxs-lookup"><span data-stu-id="f29f6-234">TTL</span></span> | <span data-ttu-id="f29f6-235">内容</span><span class="sxs-lookup"><span data-stu-id="f29f6-235">Content</span></span> |
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f29f6-236">TXT</span><span class="sxs-lookup"><span data-stu-id="f29f6-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="f29f6-237">30 分钟</span><span class="sxs-lookup"><span data-stu-id="f29f6-237">30 minutes</span></span>  <br/> |<span data-ttu-id="f29f6-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f29f6-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f29f6-239">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="f29f6-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="f29f6-240">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f29f6-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="f29f6-241">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="f29f6-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="f29f6-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f29f6-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f29f6-243">请记住，Cloudflare 负责提供此功能。</span><span class="sxs-lookup"><span data-stu-id="f29f6-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="f29f6-244">如果你看到以下步骤与图形用户界面中当前 Cloudflare GUI (差异) ，请利用 [Cloudflare 社区](https://community.cloudflare.com/)。</span><span class="sxs-lookup"><span data-stu-id="f29f6-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="f29f6-245">To get started， go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="f29f6-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="f29f6-246">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="f29f6-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="f29f6-247">在 **主页** 上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="f29f6-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="f29f6-248">在域 **的"** 概述"页面上，选择 **"DNS"。**</span><span class="sxs-lookup"><span data-stu-id="f29f6-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="f29f6-249">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="f29f6-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="f29f6-250">在 **"DNS 管理"** 页上 **，单击"** 添加记录"，然后从下表的第一行中选择值。</span><span class="sxs-lookup"><span data-stu-id="f29f6-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    | <span data-ttu-id="f29f6-251">类型</span><span class="sxs-lookup"><span data-stu-id="f29f6-251">Type</span></span> | <span data-ttu-id="f29f6-252">服务</span><span class="sxs-lookup"><span data-stu-id="f29f6-252">Service</span></span> | <span data-ttu-id="f29f6-253">协议</span><span class="sxs-lookup"><span data-stu-id="f29f6-253">Protocol</span></span> | <span data-ttu-id="f29f6-254">名称</span><span class="sxs-lookup"><span data-stu-id="f29f6-254">Name</span></span> | <span data-ttu-id="f29f6-255">TTL</span><span class="sxs-lookup"><span data-stu-id="f29f6-255">TTL</span></span> | <span data-ttu-id="f29f6-256">Priority</span><span class="sxs-lookup"><span data-stu-id="f29f6-256">Priority</span></span> | <span data-ttu-id="f29f6-257">粗细</span><span class="sxs-lookup"><span data-stu-id="f29f6-257">Weight</span></span> | <span data-ttu-id="f29f6-258">端口</span><span class="sxs-lookup"><span data-stu-id="f29f6-258">Port</span></span> | <span data-ttu-id="f29f6-259">Target</span><span class="sxs-lookup"><span data-stu-id="f29f6-259">Target</span></span> |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f29f6-260">SRV</span><span class="sxs-lookup"><span data-stu-id="f29f6-260">SRV</span></span>|<span data-ttu-id="f29f6-261">_sip</span><span class="sxs-lookup"><span data-stu-id="f29f6-261">_sip</span></span> |<span data-ttu-id="f29f6-262">TLS</span><span class="sxs-lookup"><span data-stu-id="f29f6-262">TLS</span></span> |<span data-ttu-id="f29f6-263">使用你的 *domain_name;* 例如，contoso.com</span><span class="sxs-lookup"><span data-stu-id="f29f6-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="f29f6-264">30 分钟</span><span class="sxs-lookup"><span data-stu-id="f29f6-264">30 minutes</span></span> | <span data-ttu-id="f29f6-265">100</span><span class="sxs-lookup"><span data-stu-id="f29f6-265">100</span></span>|<span data-ttu-id="f29f6-266">1</span><span class="sxs-lookup"><span data-stu-id="f29f6-266">1</span></span> |<span data-ttu-id="f29f6-267">443</span><span class="sxs-lookup"><span data-stu-id="f29f6-267">443</span></span> |<span data-ttu-id="f29f6-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f29f6-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="f29f6-269">SRV</span><span class="sxs-lookup"><span data-stu-id="f29f6-269">SRV</span></span>|<span data-ttu-id="f29f6-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f29f6-270">_sipfederationtls</span></span> | <span data-ttu-id="f29f6-271">TCP</span><span class="sxs-lookup"><span data-stu-id="f29f6-271">TCP</span></span>|<span data-ttu-id="f29f6-272">使用你的 *domain_name;* 例如，contoso.com</span><span class="sxs-lookup"><span data-stu-id="f29f6-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="f29f6-273">30 分钟</span><span class="sxs-lookup"><span data-stu-id="f29f6-273">30 minutes</span></span> |<span data-ttu-id="f29f6-274">100</span><span class="sxs-lookup"><span data-stu-id="f29f6-274">100</span></span> |<span data-ttu-id="f29f6-275">1</span><span class="sxs-lookup"><span data-stu-id="f29f6-275">1</span></span> |<span data-ttu-id="f29f6-276">5061</span><span class="sxs-lookup"><span data-stu-id="f29f6-276">5061</span></span> | <span data-ttu-id="f29f6-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f29f6-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="f29f6-278">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f29f6-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="f29f6-279">通过从表的第二行选择值添加其他 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="f29f6-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="f29f6-p117">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="f29f6-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
