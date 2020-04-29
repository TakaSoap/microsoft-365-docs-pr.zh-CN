---
title: 在 Cloudflare 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 了解如何验证您的域，并在 Cloudflare for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: ccd629dfdec24e509144c205b748a883cb65d554
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919623"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="a7610-103">在 Cloudflare 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="a7610-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="a7610-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="a7610-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a7610-105">如果 Cloudflare 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="a7610-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a7610-106">在 Cloudflare 中添加这些记录后，您的域将设置为与 Microsoft 365 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="a7610-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
<span data-ttu-id="a7610-107">若要了解如何与 Microsoft 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a7610-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a7610-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a7610-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a7610-111">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="a7610-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="a7610-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="a7610-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7610-113">必须在购买和注册域的域注册机构中执行此过程。</span><span class="sxs-lookup"><span data-stu-id="a7610-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="a7610-114">注册 Cloudflare 时，使用 Cloudflare**安装**过程添加了一个域。</span><span class="sxs-lookup"><span data-stu-id="a7610-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="a7610-115">您添加的域是从 Cloudflare 或单独的域注册机构购买的。</span><span class="sxs-lookup"><span data-stu-id="a7610-115">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="a7610-116">若要在 Microsoft 365 中验证和创建域的 DNS 记录，首先需要在域注册机构中更改名称服务器，以便它们使用 Cloudflare 的名称服务器。</span><span class="sxs-lookup"><span data-stu-id="a7610-116">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="a7610-117">若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a7610-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="a7610-118">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="a7610-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="a7610-119">通过使用下表中的值创建两个名称服务器记录，或编辑现有的名称服务器记录以使其与这些值匹配。</span><span class="sxs-lookup"><span data-stu-id="a7610-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="a7610-120">首选名称服务器</span><span class="sxs-lookup"><span data-stu-id="a7610-120">First nameserver</span></span>  <br/> |<span data-ttu-id="a7610-121">使用由 Cloudflare 提供的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="a7610-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="a7610-122">次要名称服务器</span><span class="sxs-lookup"><span data-stu-id="a7610-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="a7610-123">使用由 Cloudflare 提供的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="a7610-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="a7610-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="a7610-124">You should use at least two name server records.</span></span> <span data-ttu-id="a7610-125">如果列出了任何其他名称服务器，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="a7610-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="a7610-126">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a7610-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a7610-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a7610-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a7610-128">然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。</span><span class="sxs-lookup"><span data-stu-id="a7610-128">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a7610-129">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="a7610-129">Add a TXT record for verification</span></span>
<span data-ttu-id="a7610-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a7610-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a7610-p105">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="a7610-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7610-p106">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="a7610-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a7610-135">若要开始，请使用[此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="a7610-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="a7610-136">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="a7610-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="a7610-137">在**主页**上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="a7610-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="a7610-138">在域的 "**概述**" 页上，选择 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="a7610-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="a7610-139">在 " **DNS 管理**" 页上，单击 "**添加记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a7610-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="a7610-140">**类型**</span><span class="sxs-lookup"><span data-stu-id="a7610-140">**Type**</span></span>|<span data-ttu-id="a7610-141">**名称**</span><span class="sxs-lookup"><span data-stu-id="a7610-141">**Name**</span></span>|<span data-ttu-id="a7610-142">**自动 TTL**</span><span class="sxs-lookup"><span data-stu-id="a7610-142">**Automatic TTL**</span></span>|<span data-ttu-id="a7610-143">**内容**</span><span class="sxs-lookup"><span data-stu-id="a7610-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="a7610-144">TXT</span><span class="sxs-lookup"><span data-stu-id="a7610-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="a7610-145">30 分钟</span><span class="sxs-lookup"><span data-stu-id="a7610-145">30 minutes</span></span>  <br/> |<span data-ttu-id="a7610-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a7610-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a7610-147">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="a7610-147">**Note:** This is an example.</span></span> <span data-ttu-id="a7610-148">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="a7610-148">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a7610-149">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="a7610-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="a7610-150">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7610-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="a7610-151">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="a7610-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a7610-152">现在您已在域注册机构的网站上添加了记录，您将返回到 Microsoft 并搜索该记录。</span><span class="sxs-lookup"><span data-stu-id="a7610-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="a7610-153">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="a7610-153">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a7610-154">在 Microsoft 管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="a7610-154">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a7610-155">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="a7610-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a7610-156">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="a7610-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a7610-157">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="a7610-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a7610-p109">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a7610-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a7610-161">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="a7610-161">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a7610-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a7610-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a7610-163">若要开始，请使用[此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="a7610-163">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="a7610-164">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="a7610-164">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="a7610-165">在**主页**上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="a7610-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="a7610-166">在域的 "**概述**" 页上，选择 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="a7610-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="a7610-167">在 " **DNS 管理**" 页上，单击 "**添加记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a7610-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="a7610-168">**类型**</span><span class="sxs-lookup"><span data-stu-id="a7610-168">**Type**</span></span>|<span data-ttu-id="a7610-169">**名称**</span><span class="sxs-lookup"><span data-stu-id="a7610-169">**Name**</span></span>|<span data-ttu-id="a7610-170">**邮件服务器**</span><span class="sxs-lookup"><span data-stu-id="a7610-170">**Mail server**</span></span>|<span data-ttu-id="a7610-171">**优先级**</span><span class="sxs-lookup"><span data-stu-id="a7610-171">**Priority**</span></span>|<span data-ttu-id="a7610-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7610-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7610-173">MX</span><span class="sxs-lookup"><span data-stu-id="a7610-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="a7610-174">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a7610-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a7610-175">**注意：** 从 Microsoft 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="a7610-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   <span data-ttu-id="a7610-176">如何查找此内容？[](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="a7610-176">[How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span> |<span data-ttu-id="a7610-177">1</span><span class="sxs-lookup"><span data-stu-id="a7610-177">1</span></span>  <br/> <span data-ttu-id="a7610-178">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7610-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="a7610-179">30 分钟</span><span class="sxs-lookup"><span data-stu-id="a7610-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="a7610-180">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7610-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="a7610-181">如果 " **Mx 记录**" 一节中列出了任何其他 MX 记录，请通过选择 "**删除（X）** " 图标将其删除。</span><span class="sxs-lookup"><span data-stu-id="a7610-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="a7610-182">在确认对话框中，选择 "**删除**" 以确认更改。</span><span class="sxs-lookup"><span data-stu-id="a7610-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a7610-183">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="a7610-183">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a7610-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a7610-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a7610-185">若要开始，请使用[此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="a7610-185">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="a7610-186">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="a7610-186">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="a7610-187">在**主页**上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="a7610-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="a7610-188">在域的 "**概述**" 页上，选择 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="a7610-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="a7610-189">添加五个 CNAME 记录中的第一个。</span><span class="sxs-lookup"><span data-stu-id="a7610-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="a7610-190">在 " **DNS 管理**" 页上，单击 "**添加记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a7610-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="a7610-191">**类型**</span><span class="sxs-lookup"><span data-stu-id="a7610-191">**Type**</span></span>|<span data-ttu-id="a7610-192">**名称**</span><span class="sxs-lookup"><span data-stu-id="a7610-192">**Name**</span></span>|<span data-ttu-id="a7610-193">**目标**</span><span class="sxs-lookup"><span data-stu-id="a7610-193">**Target**</span></span>|<span data-ttu-id="a7610-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7610-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7610-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7610-195">CNAME</span></span>  <br/> |<span data-ttu-id="a7610-196">自动发现</span><span class="sxs-lookup"><span data-stu-id="a7610-196">autodiscover</span></span>  <br/> |<span data-ttu-id="a7610-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a7610-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="a7610-198">30 分钟</span><span class="sxs-lookup"><span data-stu-id="a7610-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="a7610-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7610-199">CNAME</span></span>  <br/> |<span data-ttu-id="a7610-200">sip</span><span class="sxs-lookup"><span data-stu-id="a7610-200">sip</span></span>  <br/> |<span data-ttu-id="a7610-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7610-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a7610-202">30 分钟</span><span class="sxs-lookup"><span data-stu-id="a7610-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="a7610-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7610-203">CNAME</span></span>  <br/> |<span data-ttu-id="a7610-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a7610-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a7610-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7610-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="a7610-206">30 分钟</span><span class="sxs-lookup"><span data-stu-id="a7610-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="a7610-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7610-207">CNAME</span></span>  <br/> |<span data-ttu-id="a7610-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a7610-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a7610-209">EnterpriseRegistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a7610-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="a7610-210">30 分钟</span><span class="sxs-lookup"><span data-stu-id="a7610-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="a7610-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7610-211">CNAME</span></span>  <br/> |<span data-ttu-id="a7610-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a7610-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a7610-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a7610-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="a7610-214">30 分钟</span><span class="sxs-lookup"><span data-stu-id="a7610-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="a7610-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="a7610-215">CNAME</span></span>  <br/> |<span data-ttu-id="a7610-216">msoid</span><span class="sxs-lookup"><span data-stu-id="a7610-216">msoid</span></span>  <br/> |<span data-ttu-id="a7610-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="a7610-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="a7610-218">30 分钟</span><span class="sxs-lookup"><span data-stu-id="a7610-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="a7610-219">选择 " **DNS 流量**" 图标（橙色云）以绕过 Cloudflare 服务器。</span><span class="sxs-lookup"><span data-stu-id="a7610-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="a7610-220">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7610-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="a7610-221">逐一添加其他 5 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="a7610-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a7610-222">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="a7610-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a7610-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a7610-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7610-224">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="a7610-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a7610-225">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="a7610-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a7610-226">如果你的域已有 SPF 记录，请不要为 Microsoft 365 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="a7610-226">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="a7610-227">可以将所需的 Microsoft 365 值添加到当前记录，这样就拥有包含两组值的*单个* SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="a7610-227">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a7610-228">若要开始，请使用[此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="a7610-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="a7610-229">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="a7610-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="a7610-230">在**主页**上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="a7610-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="a7610-231">在域的 "**概述**" 页上，选择 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="a7610-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="a7610-232">在 " **DNS 管理**" 页上，单击 "**添加记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a7610-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="a7610-233">**类型**</span><span class="sxs-lookup"><span data-stu-id="a7610-233">**Type**</span></span>|<span data-ttu-id="a7610-234">**名称**</span><span class="sxs-lookup"><span data-stu-id="a7610-234">**Name**</span></span>|<span data-ttu-id="a7610-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7610-235">**TTL**</span></span>|<span data-ttu-id="a7610-236">**内容**</span><span class="sxs-lookup"><span data-stu-id="a7610-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7610-237">TXT</span><span class="sxs-lookup"><span data-stu-id="a7610-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="a7610-238">30 分钟</span><span class="sxs-lookup"><span data-stu-id="a7610-238">30 minutes</span></span>  <br/> |<span data-ttu-id="a7610-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a7610-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a7610-240">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="a7610-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="a7610-241">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7610-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a7610-242">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="a7610-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a7610-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a7610-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7610-244">请记住，Cloudflare 有责任使此功能可用。</span><span class="sxs-lookup"><span data-stu-id="a7610-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="a7610-245">如果您看到以下步骤与当前 Cloudflare GUI （图形用户界面）之间的差异，请利用[Cloudflare 社区](https://community.cloudflare.com/)。</span><span class="sxs-lookup"><span data-stu-id="a7610-245">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="a7610-246">若要开始，请使用[此链接](https://www.cloudflare.com/a/login)转到 Cloudflare 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="a7610-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="a7610-247">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="a7610-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="a7610-248">在**主页**上，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="a7610-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="a7610-249">在域的 "**概述**" 页上，选择 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="a7610-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="a7610-250">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="a7610-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="a7610-251">在 " **DNS 管理**" 页上，单击 "**添加记录**"，然后选择下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="a7610-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="a7610-252">**类型**</span><span class="sxs-lookup"><span data-stu-id="a7610-252">**Type**</span></span>|<span data-ttu-id="a7610-253">**服务**</span><span class="sxs-lookup"><span data-stu-id="a7610-253">**Service**</span></span>|<span data-ttu-id="a7610-254">**协议**</span><span class="sxs-lookup"><span data-stu-id="a7610-254">**Protocol**</span></span>|<span data-ttu-id="a7610-255">**名称**</span><span class="sxs-lookup"><span data-stu-id="a7610-255">**Name**</span></span>|<span data-ttu-id="a7610-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a7610-256">**TTL**</span></span>|<span data-ttu-id="a7610-257">**优先级**</span><span class="sxs-lookup"><span data-stu-id="a7610-257">**Priority**</span></span>|<span data-ttu-id="a7610-258">**权重**</span><span class="sxs-lookup"><span data-stu-id="a7610-258">**Weight**</span></span>|<span data-ttu-id="a7610-259">**端口**</span><span class="sxs-lookup"><span data-stu-id="a7610-259">**Port**</span></span>|<span data-ttu-id="a7610-260">**目标**</span><span class="sxs-lookup"><span data-stu-id="a7610-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a7610-261">SRV</span><span class="sxs-lookup"><span data-stu-id="a7610-261">SRV</span></span>|<span data-ttu-id="a7610-262">_sip</span><span class="sxs-lookup"><span data-stu-id="a7610-262">_sip</span></span> |<span data-ttu-id="a7610-263">TLS</span><span class="sxs-lookup"><span data-stu-id="a7610-263">TLS</span></span> |<span data-ttu-id="a7610-264">使用*domain_name*;例如，contoso.com</span><span class="sxs-lookup"><span data-stu-id="a7610-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="a7610-265">30 分钟</span><span class="sxs-lookup"><span data-stu-id="a7610-265">30 minutes</span></span> | <span data-ttu-id="a7610-266">100</span><span class="sxs-lookup"><span data-stu-id="a7610-266">100</span></span>|<span data-ttu-id="a7610-267">1</span><span class="sxs-lookup"><span data-stu-id="a7610-267">1</span></span> |<span data-ttu-id="a7610-268">443</span><span class="sxs-lookup"><span data-stu-id="a7610-268">443</span></span> |<span data-ttu-id="a7610-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7610-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="a7610-270">SRV</span><span class="sxs-lookup"><span data-stu-id="a7610-270">SRV</span></span>|<span data-ttu-id="a7610-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a7610-271">_sipfederationtls</span></span> | <span data-ttu-id="a7610-272">TCP</span><span class="sxs-lookup"><span data-stu-id="a7610-272">TCP</span></span>|<span data-ttu-id="a7610-273">使用*domain_name*;例如，contoso.com</span><span class="sxs-lookup"><span data-stu-id="a7610-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="a7610-274">30 分钟</span><span class="sxs-lookup"><span data-stu-id="a7610-274">30 minutes</span></span> |<span data-ttu-id="a7610-275">100</span><span class="sxs-lookup"><span data-stu-id="a7610-275">100</span></span> |<span data-ttu-id="a7610-276">1</span><span class="sxs-lookup"><span data-stu-id="a7610-276">1</span></span> |<span data-ttu-id="a7610-277">5061</span><span class="sxs-lookup"><span data-stu-id="a7610-277">5061</span></span> | <span data-ttu-id="a7610-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a7610-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="a7610-279">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a7610-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="a7610-280">通过从表的第二行中选择值来添加其他 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="a7610-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="a7610-p117">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a7610-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
