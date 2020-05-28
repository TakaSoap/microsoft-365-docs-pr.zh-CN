---
title: 在 web.com 处为 Microsoft 创建 DNS 记录
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 了解如何验证您的域，并在 web.com for Microsoft 中为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 2a9162c1ca6fc6a00e564e8f004768fac49bd3e3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400300"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="a1bc7-103">在 web.com 处为 Microsoft 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="a1bc7-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="a1bc7-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a1bc7-105">如果 web.com 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a1bc7-106">在 web.com 中添加这些记录后，您的域将设置为与 Microsoft 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="a1bc7-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a1bc7-110">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="a1bc7-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="a1bc7-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="a1bc7-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1bc7-112">必须在购买和注册域的域注册机构中执行此过程。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="a1bc7-113">注册 web.com 时，使用 web.com**安装**过程添加了一个域。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="a1bc7-114">若要在 Microsoft 中验证和创建域的 DNS 记录，首先需要更改域注册机构中的名称服务器，以便它们使用 .com 的名称服务器。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="a1bc7-115">若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="a1bc7-116">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="a1bc7-117">通过使用下表中的值创建两个名称服务器记录，或编辑现有的名称服务器记录以使其与这些值匹配。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="a1bc7-118">首选名称服务器</span><span class="sxs-lookup"><span data-stu-id="a1bc7-118">First nameserver</span></span>  <br/> |<span data-ttu-id="a1bc7-119">使用由 web.com 提供的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="a1bc7-120">次要名称服务器</span><span class="sxs-lookup"><span data-stu-id="a1bc7-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="a1bc7-121">使用由 web.com 提供的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="a1bc7-122">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="a1bc7-122">You should use at least two name server records.</span></span> <span data-ttu-id="a1bc7-123">如果列出了任何其他名称服务器，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="a1bc7-124">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a1bc7-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a1bc7-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a1bc7-126">然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a1bc7-127">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="a1bc7-127">Add a TXT record for verification</span></span>
<span data-ttu-id="a1bc7-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a1bc7-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a1bc7-p104">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a1bc7-p105">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a1bc7-133">若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a1bc7-134">先登录。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-134">Log in first.</span></span>
  
2. <span data-ttu-id="a1bc7-135">在 "**帐户管理器**" 页上，选择 **"我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a1bc7-136">在 "\* \* 管理 \* 我的域 \* \* \*" 下，选择 "**编辑高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="a1bc7-137">在 "**域名**" 页上的 "**文本（TXT 记录）**" 下，单击 "**编辑 TXT 记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="a1bc7-138">**主机**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-138">**Host**</span></span>|<span data-ttu-id="a1bc7-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-139">**TTL**</span></span>|<span data-ttu-id="a1bc7-140">**文本**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="a1bc7-141">3600</span><span class="sxs-lookup"><span data-stu-id="a1bc7-141">3600</span></span>  <br/> |<span data-ttu-id="a1bc7-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a1bc7-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a1bc7-143">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-143">**Note:** This is an example.</span></span> <span data-ttu-id="a1bc7-144">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a1bc7-145">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="a1bc7-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="a1bc7-146">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="a1bc7-147">请等待几分钟，然后再验证新的 TXT 记录，以便您刚刚创建的记录可以通过 Internet 进行更新。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a1bc7-148">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a1bc7-149">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a1bc7-150">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a1bc7-151">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a1bc7-152">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a1bc7-153">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a1bc7-p108">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a1bc7-157">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="a1bc7-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a1bc7-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a1bc7-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a1bc7-159">若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a1bc7-160">先登录。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-160">Log in first.</span></span>
  
2. <span data-ttu-id="a1bc7-161">在 "**帐户管理器**" 页上，选择 **"我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a1bc7-162">在 "\* \* 管理 \* 我的域 \* \* \*" 下，选择 "**编辑高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="a1bc7-163">在 "**邮件服务器（MX 记录）**" 下，单击 "**编辑 MX 记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="a1bc7-164">**优先级**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-164">**Priority**</span></span>|<span data-ttu-id="a1bc7-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-165">**TTL**</span></span>|<span data-ttu-id="a1bc7-166">**邮件服务器**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a1bc7-167">1 </span><span class="sxs-lookup"><span data-stu-id="a1bc7-167">1</span></span>  <br/> <span data-ttu-id="a1bc7-168">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="a1bc7-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="a1bc7-169">3600</span><span class="sxs-lookup"><span data-stu-id="a1bc7-169">3600</span></span>  <br/> |<span data-ttu-id="a1bc7-170">*\<domain-key\>*。 mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a1bc7-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a1bc7-171">\**注意：\*\*\*\<domain-key\>* 从你的 Microsoft 帐户获取你的。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="a1bc7-172">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="a1bc7-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="a1bc7-173">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="a1bc7-174">如果 " **Mx 记录**" 部分中列出了任何其他 MX 记录，请选中 "**删除**" 下的记录旁边的复选框，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="a1bc7-175">在确认屏幕上，选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a1bc7-176">添加 Microsoft 所需的六条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="a1bc7-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a1bc7-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a1bc7-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a1bc7-178">若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a1bc7-179">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="a1bc7-180">在 "**帐户管理器**" 页上，选择 **"我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a1bc7-181">在 "\* \* 管理 \* 我的域 \* \* \*" 下，选择 "**编辑高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="a1bc7-182">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="a1bc7-183">在 "**主机别名（CNAME 记录）**" 下，单击 "**编辑 CNAME 记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="a1bc7-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-184">**Alias**</span></span>|<span data-ttu-id="a1bc7-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-185">**TTL**</span></span>|<span data-ttu-id="a1bc7-186">**引用主机名**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-186">**Refers to Host Name**</span></span>|<span data-ttu-id="a1bc7-187">**其他主机**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a1bc7-188">自动发现</span><span class="sxs-lookup"><span data-stu-id="a1bc7-188">autodiscover</span></span>  <br/> |<span data-ttu-id="a1bc7-189">3600</span><span class="sxs-lookup"><span data-stu-id="a1bc7-189">3600</span></span>  <br/> |<span data-ttu-id="a1bc7-190">@ （无）</span><span class="sxs-lookup"><span data-stu-id="a1bc7-190">@ (none)</span></span>  <br/> |<span data-ttu-id="a1bc7-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a1bc7-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a1bc7-192">sip</span><span class="sxs-lookup"><span data-stu-id="a1bc7-192">sip</span></span>  <br/> |<span data-ttu-id="a1bc7-193">3600</span><span class="sxs-lookup"><span data-stu-id="a1bc7-193">3600</span></span>  <br/> |<span data-ttu-id="a1bc7-194">@ （无）</span><span class="sxs-lookup"><span data-stu-id="a1bc7-194">@ (none)</span></span>  <br/> |<span data-ttu-id="a1bc7-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a1bc7-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a1bc7-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a1bc7-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a1bc7-197">3600</span><span class="sxs-lookup"><span data-stu-id="a1bc7-197">3600</span></span>  <br/> |<span data-ttu-id="a1bc7-198">@ （无）</span><span class="sxs-lookup"><span data-stu-id="a1bc7-198">@ (none)</span></span>  <br/> | <span data-ttu-id="a1bc7-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a1bc7-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a1bc7-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a1bc7-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a1bc7-201">3600</span><span class="sxs-lookup"><span data-stu-id="a1bc7-201">3600</span></span>  <br/> |<span data-ttu-id="a1bc7-202">@ （无）</span><span class="sxs-lookup"><span data-stu-id="a1bc7-202">@ (none)</span></span>  <br/> |<span data-ttu-id="a1bc7-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a1bc7-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="a1bc7-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a1bc7-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a1bc7-205">3600</span><span class="sxs-lookup"><span data-stu-id="a1bc7-205">3600</span></span>  <br/> |<span data-ttu-id="a1bc7-206">@ （无）</span><span class="sxs-lookup"><span data-stu-id="a1bc7-206">@ (none)</span></span>  <br/> |<span data-ttu-id="a1bc7-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a1bc7-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="a1bc7-208">msoid</span><span class="sxs-lookup"><span data-stu-id="a1bc7-208">msoid</span></span>  <br/> |<span data-ttu-id="a1bc7-209">3600</span><span class="sxs-lookup"><span data-stu-id="a1bc7-209">3600</span></span>  <br/> |<span data-ttu-id="a1bc7-210">@ （无）</span><span class="sxs-lookup"><span data-stu-id="a1bc7-210">@ (none)</span></span>  <br/> |<span data-ttu-id="a1bc7-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="a1bc7-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="a1bc7-212">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="a1bc7-213">逐一添加其他 5 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a1bc7-214">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="a1bc7-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a1bc7-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a1bc7-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1bc7-216">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a1bc7-217">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a1bc7-218">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a1bc7-219">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a1bc7-220">若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a1bc7-221">先登录。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="a1bc7-222">在 "**帐户管理器**" 页上，选择 **"我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a1bc7-223">在 "\* \* 管理 \* 我的域 \* \* \*" 下，选择 "**编辑高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="a1bc7-224">在 "**域名**" 页上的 "**文本（TXT 记录）**" 下，单击 "**编辑 TXT 记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="a1bc7-225">**主机**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-225">**Host**</span></span>|<span data-ttu-id="a1bc7-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-226">**TTL**</span></span>|<span data-ttu-id="a1bc7-227">**文本**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a1bc7-228">3600</span><span class="sxs-lookup"><span data-stu-id="a1bc7-228">3600</span></span>  <br/> |<span data-ttu-id="a1bc7-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a1bc7-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a1bc7-230">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="a1bc7-231">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-231">Select **Continue**.</span></span>

6. <span data-ttu-id="a1bc7-232">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a1bc7-233">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="a1bc7-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a1bc7-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a1bc7-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1bc7-235">请记住，web.com 有责任使此功能可用。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="a1bc7-236">如果您看到以下步骤与当前 web.com GUI （图形用户界面）之间的差异，请利用[Web.com 社区](https://community.web.com.com/)。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="a1bc7-237">若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a1bc7-238">先登录。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-238">Log in first.</span></span>
      
2. <span data-ttu-id="a1bc7-239">在 "**帐户管理器**" 页上，选择 **"我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a1bc7-240">在 "\* \* 管理 \* 我的域 \* \* \*" 下，选择 "**编辑高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="a1bc7-241">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="a1bc7-242">在 "**服务（SRV 记录）**" 下，单击 "**编辑 SRV 记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="a1bc7-243">**服务**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-243">**Service**</span></span>|<span data-ttu-id="a1bc7-244">**协议**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-244">**Protocol**</span></span>|<span data-ttu-id="a1bc7-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-245">**TTL**</span></span>|<span data-ttu-id="a1bc7-246">**优先级**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-246">**Priority**</span></span>|<span data-ttu-id="a1bc7-247">**权重**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-247">**Weight**</span></span>|<span data-ttu-id="a1bc7-248">**端口**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-248">**Port**</span></span>|<span data-ttu-id="a1bc7-249">**目标**</span><span class="sxs-lookup"><span data-stu-id="a1bc7-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a1bc7-250">_sip</span><span class="sxs-lookup"><span data-stu-id="a1bc7-250">_sip</span></span> |<span data-ttu-id="a1bc7-251">_tls</span><span class="sxs-lookup"><span data-stu-id="a1bc7-251">_tls</span></span> |<span data-ttu-id="a1bc7-252">3600</span><span class="sxs-lookup"><span data-stu-id="a1bc7-252">3600</span></span> | <span data-ttu-id="a1bc7-253">100</span><span class="sxs-lookup"><span data-stu-id="a1bc7-253">100</span></span>|<span data-ttu-id="a1bc7-254">1 </span><span class="sxs-lookup"><span data-stu-id="a1bc7-254">1</span></span> |<span data-ttu-id="a1bc7-255">443</span><span class="sxs-lookup"><span data-stu-id="a1bc7-255">443</span></span> |<span data-ttu-id="a1bc7-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a1bc7-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="a1bc7-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a1bc7-257">_sipfederationtls</span></span> |<span data-ttu-id="a1bc7-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="a1bc7-258">_tcp</span></span> |<span data-ttu-id="a1bc7-259">3600</span><span class="sxs-lookup"><span data-stu-id="a1bc7-259">3600</span></span> |<span data-ttu-id="a1bc7-260">100</span><span class="sxs-lookup"><span data-stu-id="a1bc7-260">100</span></span> |<span data-ttu-id="a1bc7-261">1 </span><span class="sxs-lookup"><span data-stu-id="a1bc7-261">1</span></span> |<span data-ttu-id="a1bc7-262">5061</span><span class="sxs-lookup"><span data-stu-id="a1bc7-262">5061</span></span> | <span data-ttu-id="a1bc7-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a1bc7-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="a1bc7-264">通过从表的第二行中选择值来添加其他 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="a1bc7-265">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-265">Select **Continue**.</span></span>

7. <span data-ttu-id="a1bc7-266">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="a1bc7-p116">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="a1bc7-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
