---
title: 在 web.com 上为 Office 365 创建 DNS 记录
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: 了解如何在 web.com for Office 365 中验证您的域并为电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: eb231f85e568e81a5e229f0533d8176feb590f48
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249452"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a><span data-ttu-id="14ef8-103">在 web.com 上为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="14ef8-103">Create DNS records at web.com for Office 365</span></span>

 <span data-ttu-id="14ef8-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="14ef8-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="14ef8-105">如果 web.com 是您的 DNS 托管提供商，请按照本文中的步骤验证您的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="14ef8-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="14ef8-106">在 web.com 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="14ef8-106">After you add these records at web.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="14ef8-107">若要了解如何与 Office 365 结合使用网站的 Web 宿主和 DNS，请参阅[配合使用公共网站与 Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="14ef8-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="14ef8-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="14ef8-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="14ef8-111">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="14ef8-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="14ef8-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="14ef8-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="14ef8-113">必须在购买和注册域的域注册机构中执行此过程。</span><span class="sxs-lookup"><span data-stu-id="14ef8-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="14ef8-114">注册 web.com 时，使用 web.com**安装**过程添加了一个域。</span><span class="sxs-lookup"><span data-stu-id="14ef8-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="14ef8-115">若要在 Office 365 中验证和创建域的 DNS 记录，首先需要更改域注册机构中的名称服务器，以便它们使用 web .com 的名称服务器。</span><span class="sxs-lookup"><span data-stu-id="14ef8-115">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="14ef8-116">若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="14ef8-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="14ef8-117">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="14ef8-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="14ef8-118">通过使用下表中的值创建两个名称服务器记录，或编辑现有的名称服务器记录以使其与这些值匹配。</span><span class="sxs-lookup"><span data-stu-id="14ef8-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="14ef8-119">首选名称服务器</span><span class="sxs-lookup"><span data-stu-id="14ef8-119">First nameserver</span></span>  <br/> |<span data-ttu-id="14ef8-120">使用由 web.com 提供的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="14ef8-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="14ef8-121">次要名称服务器</span><span class="sxs-lookup"><span data-stu-id="14ef8-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="14ef8-122">使用由 web.com 提供的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="14ef8-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="14ef8-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="14ef8-123">You should use at least two name server records.</span></span> <span data-ttu-id="14ef8-124">如果列出了任何其他名称服务器，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="14ef8-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="14ef8-125">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="14ef8-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="14ef8-p103">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="14ef8-p103">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="14ef8-128">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="14ef8-128">Add a TXT record for verification</span></span>
<span data-ttu-id="14ef8-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="14ef8-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="14ef8-p104">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="14ef8-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14ef8-p105">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="14ef8-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="14ef8-134">若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="14ef8-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="14ef8-135">先登录。</span><span class="sxs-lookup"><span data-stu-id="14ef8-135">Log in first.</span></span>
  
2. <span data-ttu-id="14ef8-136">在 "**帐户管理器**" 页上，选择 **"我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="14ef8-137">在 "\* \* 管理 \* 我的域 \* \* \*" 下，选择 "**编辑高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="14ef8-138">在 "**域名**" 页上的 "**文本（TXT 记录）**" 下，单击 "**编辑 TXT 记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="14ef8-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="14ef8-139">**主机**</span><span class="sxs-lookup"><span data-stu-id="14ef8-139">**Host**</span></span>|<span data-ttu-id="14ef8-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14ef8-140">**TTL**</span></span>|<span data-ttu-id="14ef8-141">**文本**</span><span class="sxs-lookup"><span data-stu-id="14ef8-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="14ef8-142">3600</span><span class="sxs-lookup"><span data-stu-id="14ef8-142">3600</span></span>  <br/> |<span data-ttu-id="14ef8-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="14ef8-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="14ef8-144">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="14ef8-144">**Note:** This is an example.</span></span> <span data-ttu-id="14ef8-145">在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。</span><span class="sxs-lookup"><span data-stu-id="14ef8-145">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="14ef8-146">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="14ef8-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="14ef8-147">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="14ef8-148">请等待几分钟，然后再验证新的 TXT 记录，以便您刚刚创建的记录可以通过 Internet 进行更新。</span><span class="sxs-lookup"><span data-stu-id="14ef8-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="14ef8-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="14ef8-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="14ef8-150">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="14ef8-150">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="14ef8-151">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="14ef8-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="14ef8-152">在 "**域**" 页上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="14ef8-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="14ef8-153">在 "**设置**" 页上，选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="14ef8-154">在 "**验证域**" 页上，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="14ef8-p108">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="14ef8-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="14ef8-158">添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="14ef8-158">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="14ef8-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="14ef8-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="14ef8-160">若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="14ef8-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="14ef8-161">先登录。</span><span class="sxs-lookup"><span data-stu-id="14ef8-161">Log in first.</span></span>
  
2. <span data-ttu-id="14ef8-162">在 "**帐户管理器**" 页上，选择 **"我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="14ef8-163">在 "\* \* 管理 \* 我的域 \* \* \*" 下，选择 "**编辑高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="14ef8-164">在 "**邮件服务器（MX 记录）**" 下，单击 "**编辑 MX 记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="14ef8-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="14ef8-165">**优先级**</span><span class="sxs-lookup"><span data-stu-id="14ef8-165">**Priority**</span></span>|<span data-ttu-id="14ef8-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14ef8-166">**TTL**</span></span>|<span data-ttu-id="14ef8-167">**邮件服务器**</span><span class="sxs-lookup"><span data-stu-id="14ef8-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="14ef8-168">1</span><span class="sxs-lookup"><span data-stu-id="14ef8-168">1</span></span>  <br/> <span data-ttu-id="14ef8-169">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="14ef8-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="14ef8-170">3600</span><span class="sxs-lookup"><span data-stu-id="14ef8-170">3600</span></span>  <br/> |<span data-ttu-id="14ef8-171">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="14ef8-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="14ef8-172">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="14ef8-172">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="14ef8-173">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="14ef8-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="14ef8-174">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="14ef8-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="14ef8-175">如果 " **Mx 记录**" 部分中列出了任何其他 MX 记录，请选中 "**删除**" 下的记录旁边的复选框，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="14ef8-176">在确认屏幕上，选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="14ef8-177">添加 Office 365 所需的6条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="14ef8-177">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="14ef8-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="14ef8-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="14ef8-179">若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="14ef8-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="14ef8-180">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="14ef8-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="14ef8-181">在 "**帐户管理器**" 页上，选择 **"我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="14ef8-182">在 "\* \* 管理 \* 我的域 \* \* \*" 下，选择 "**编辑高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="14ef8-183">添加第一条 CNAME 记录（共 6 条）。</span><span class="sxs-lookup"><span data-stu-id="14ef8-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="14ef8-184">在 "**主机别名（CNAME 记录）**" 下，单击 "**编辑 CNAME 记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="14ef8-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="14ef8-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="14ef8-185">**Alias**</span></span>|<span data-ttu-id="14ef8-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14ef8-186">**TTL**</span></span>|<span data-ttu-id="14ef8-187">**引用主机名**</span><span class="sxs-lookup"><span data-stu-id="14ef8-187">**Refers to Host Name**</span></span>|<span data-ttu-id="14ef8-188">**其他主机**</span><span class="sxs-lookup"><span data-stu-id="14ef8-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14ef8-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="14ef8-189">autodiscover</span></span>  <br/> |<span data-ttu-id="14ef8-190">3600</span><span class="sxs-lookup"><span data-stu-id="14ef8-190">3600</span></span>  <br/> |<span data-ttu-id="14ef8-191">@ （无）</span><span class="sxs-lookup"><span data-stu-id="14ef8-191">@ (none)</span></span>  <br/> |<span data-ttu-id="14ef8-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="14ef8-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="14ef8-193">sip</span><span class="sxs-lookup"><span data-stu-id="14ef8-193">sip</span></span>  <br/> |<span data-ttu-id="14ef8-194">3600</span><span class="sxs-lookup"><span data-stu-id="14ef8-194">3600</span></span>  <br/> |<span data-ttu-id="14ef8-195">@ （无）</span><span class="sxs-lookup"><span data-stu-id="14ef8-195">@ (none)</span></span>  <br/> |<span data-ttu-id="14ef8-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="14ef8-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="14ef8-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="14ef8-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="14ef8-198">3600</span><span class="sxs-lookup"><span data-stu-id="14ef8-198">3600</span></span>  <br/> |<span data-ttu-id="14ef8-199">@ （无）</span><span class="sxs-lookup"><span data-stu-id="14ef8-199">@ (none)</span></span>  <br/> | <span data-ttu-id="14ef8-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="14ef8-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="14ef8-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="14ef8-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="14ef8-202">3600</span><span class="sxs-lookup"><span data-stu-id="14ef8-202">3600</span></span>  <br/> |<span data-ttu-id="14ef8-203">@ （无）</span><span class="sxs-lookup"><span data-stu-id="14ef8-203">@ (none)</span></span>  <br/> |<span data-ttu-id="14ef8-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="14ef8-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="14ef8-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="14ef8-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="14ef8-206">3600</span><span class="sxs-lookup"><span data-stu-id="14ef8-206">3600</span></span>  <br/> |<span data-ttu-id="14ef8-207">@ （无）</span><span class="sxs-lookup"><span data-stu-id="14ef8-207">@ (none)</span></span>  <br/> |<span data-ttu-id="14ef8-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="14ef8-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="14ef8-209">msoid</span><span class="sxs-lookup"><span data-stu-id="14ef8-209">msoid</span></span>  <br/> |<span data-ttu-id="14ef8-210">3600</span><span class="sxs-lookup"><span data-stu-id="14ef8-210">3600</span></span>  <br/> |<span data-ttu-id="14ef8-211">@ （无）</span><span class="sxs-lookup"><span data-stu-id="14ef8-211">@ (none)</span></span>  <br/> |<span data-ttu-id="14ef8-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="14ef8-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="14ef8-213">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="14ef8-214">逐一添加其他 5 条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="14ef8-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="14ef8-215">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="14ef8-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="14ef8-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="14ef8-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="14ef8-217">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="14ef8-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="14ef8-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="14ef8-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="14ef8-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="14ef8-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="14ef8-220">改为将所需的 Office 365 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="14ef8-220">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="14ef8-221">若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="14ef8-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="14ef8-222">先登录。</span><span class="sxs-lookup"><span data-stu-id="14ef8-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="14ef8-223">在 "**帐户管理器**" 页上，选择 **"我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="14ef8-224">在 "\* \* 管理 \* 我的域 \* \* \*" 下，选择 "**编辑高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="14ef8-225">在 "**域名**" 页上的 "**文本（TXT 记录）**" 下，单击 "**编辑 TXT 记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="14ef8-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="14ef8-226">**主机**</span><span class="sxs-lookup"><span data-stu-id="14ef8-226">**Host**</span></span>|<span data-ttu-id="14ef8-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14ef8-227">**TTL**</span></span>|<span data-ttu-id="14ef8-228">**文本**</span><span class="sxs-lookup"><span data-stu-id="14ef8-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="14ef8-229">3600</span><span class="sxs-lookup"><span data-stu-id="14ef8-229">3600</span></span>  <br/> |<span data-ttu-id="14ef8-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="14ef8-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="14ef8-231">**注意：** 我们建议您复制并粘贴此条目，以确保所有的间距保持正确。</span><span class="sxs-lookup"><span data-stu-id="14ef8-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="14ef8-232">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-232">Select **Continue**.</span></span>

6. <span data-ttu-id="14ef8-233">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="14ef8-234">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="14ef8-234">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="14ef8-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="14ef8-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="14ef8-236">请记住，web.com 有责任使此功能可用。</span><span class="sxs-lookup"><span data-stu-id="14ef8-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="14ef8-237">如果您看到以下步骤与当前 web.com GUI （图形用户界面）之间的差异，请利用[Web.com 社区](https://community.web.com.com/)。</span><span class="sxs-lookup"><span data-stu-id="14ef8-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="14ef8-238">若要开始，请使用[此链接](https://checkout.web.com/manage-it/index.jsp)转到 web.com 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="14ef8-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="14ef8-239">先登录。</span><span class="sxs-lookup"><span data-stu-id="14ef8-239">Log in first.</span></span>
      
2. <span data-ttu-id="14ef8-240">在 "**帐户管理器**" 页上，选择 **"我的域名**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="14ef8-241">在 "\* \* 管理 \* 我的域 \* \* \*" 下，选择 "**编辑高级 DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="14ef8-242">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="14ef8-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="14ef8-243">在 "**服务（SRV 记录）**" 下，单击 "**编辑 SRV 记录**"，然后选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="14ef8-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="14ef8-244">**服务**</span><span class="sxs-lookup"><span data-stu-id="14ef8-244">**Service**</span></span>|<span data-ttu-id="14ef8-245">**协议**</span><span class="sxs-lookup"><span data-stu-id="14ef8-245">**Protocol**</span></span>|<span data-ttu-id="14ef8-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="14ef8-246">**TTL**</span></span>|<span data-ttu-id="14ef8-247">**优先级**</span><span class="sxs-lookup"><span data-stu-id="14ef8-247">**Priority**</span></span>|<span data-ttu-id="14ef8-248">**权重**</span><span class="sxs-lookup"><span data-stu-id="14ef8-248">**Weight**</span></span>|<span data-ttu-id="14ef8-249">**端口**</span><span class="sxs-lookup"><span data-stu-id="14ef8-249">**Port**</span></span>|<span data-ttu-id="14ef8-250">**目标**</span><span class="sxs-lookup"><span data-stu-id="14ef8-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="14ef8-251">_sip</span><span class="sxs-lookup"><span data-stu-id="14ef8-251">_sip</span></span> |<span data-ttu-id="14ef8-252">_tls</span><span class="sxs-lookup"><span data-stu-id="14ef8-252">_tls</span></span> |<span data-ttu-id="14ef8-253">3600</span><span class="sxs-lookup"><span data-stu-id="14ef8-253">3600</span></span> | <span data-ttu-id="14ef8-254">100</span><span class="sxs-lookup"><span data-stu-id="14ef8-254">100</span></span>|<span data-ttu-id="14ef8-255">1</span><span class="sxs-lookup"><span data-stu-id="14ef8-255">1</span></span> |<span data-ttu-id="14ef8-256">443</span><span class="sxs-lookup"><span data-stu-id="14ef8-256">443</span></span> |<span data-ttu-id="14ef8-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="14ef8-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="14ef8-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="14ef8-258">_sipfederationtls</span></span> |<span data-ttu-id="14ef8-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="14ef8-259">_tcp</span></span> |<span data-ttu-id="14ef8-260">3600</span><span class="sxs-lookup"><span data-stu-id="14ef8-260">3600</span></span> |<span data-ttu-id="14ef8-261">100</span><span class="sxs-lookup"><span data-stu-id="14ef8-261">100</span></span> |<span data-ttu-id="14ef8-262">1</span><span class="sxs-lookup"><span data-stu-id="14ef8-262">1</span></span> |<span data-ttu-id="14ef8-263">5061</span><span class="sxs-lookup"><span data-stu-id="14ef8-263">5061</span></span> | <span data-ttu-id="14ef8-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="14ef8-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="14ef8-265">通过从表的第二行中选择值来添加其他 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="14ef8-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="14ef8-266">选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-266">Select **Continue**.</span></span>

7. <span data-ttu-id="14ef8-267">选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="14ef8-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="14ef8-p116">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="14ef8-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
