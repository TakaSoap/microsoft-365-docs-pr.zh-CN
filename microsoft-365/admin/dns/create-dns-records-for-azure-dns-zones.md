---
title: 为 Azure DNS 区域创建 DNS 记录
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: 了解如何验证域，并设置电子邮件、Skype for Business Online 和 Microsoft 的 Azure DNS 区域的其他服务的 DNS 记录。
ms.openlocfilehash: be4baa80d0f96e92dc9dd9004054f29f12f6415b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916138"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="d6cef-103">为 Azure DNS 区域创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="d6cef-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="d6cef-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="d6cef-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d6cef-105">如果 Azure 是 DNS 托管提供商，请按照本文中的步骤验证域，并设置电子邮件、Skype for Business Online 等的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="d6cef-106">下面是要添加的主要记录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="d6cef-107">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="d6cef-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="d6cef-108">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="d6cef-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="d6cef-109">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6cef-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="d6cef-110">添加 Microsoft 所需的四条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="d6cef-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="d6cef-111">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="d6cef-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="d6cef-112">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="d6cef-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="d6cef-113">在 Azure 中添加这些记录后，你的域将设置为使用 Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="d6cef-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6cef-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d6cef-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="d6cef-117">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="d6cef-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="d6cef-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="d6cef-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6cef-119">必须在购买和注册域的域注册机构中执行此过程。</span><span class="sxs-lookup"><span data-stu-id="d6cef-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="d6cef-120">注册 Azure 后，你在 DNS 区域中创建了一个资源组，然后将你的域名分配给该资源组。</span><span class="sxs-lookup"><span data-stu-id="d6cef-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="d6cef-121">该域名注册到外部域注册机构;Azure 不提供域注册服务。</span><span class="sxs-lookup"><span data-stu-id="d6cef-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="d6cef-122">若要在 Microsoft 中验证和创建域的 DNS 记录，首先需要更改域注册机构中的名称服务器，以便它们使用分配给你的资源组的 Azure 名称服务器。</span><span class="sxs-lookup"><span data-stu-id="d6cef-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="d6cef-123">若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="d6cef-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="d6cef-124">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="d6cef-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="d6cef-125">使用下表中的值创建两个名称机记录，或编辑现有名称机记录，以便它们与这些值匹配。</span><span class="sxs-lookup"><span data-stu-id="d6cef-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="d6cef-126">下面显示了 Azure 分配的名称服务器的示例。</span><span class="sxs-lookup"><span data-stu-id="d6cef-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="d6cef-127">**First nameserver：** 使用 Azure 分配的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="d6cef-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="d6cef-128">**第二个名称机：** 使用 Azure 分配的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="d6cef-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="d6cef-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="d6cef-130">You should use at least two name server records.</span></span> <span data-ttu-id="d6cef-131">如果域注册机构的网站中列出了任何其他名称服务器，您应该将其删除。</span><span class="sxs-lookup"><span data-stu-id="d6cef-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="d6cef-132">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d6cef-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d6cef-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="d6cef-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="d6cef-134">然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="d6cef-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d6cef-135">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="d6cef-135">Add a TXT record for verification</span></span>
<span data-ttu-id="d6cef-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d6cef-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d6cef-p106">在将域用于 Microsoft 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="d6cef-p106">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6cef-p107">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="d6cef-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="d6cef-141">To get started， go to your domains page at Azure by using [this link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="d6cef-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="d6cef-142">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="d6cef-144">使用 **仪表板页面上** 的搜索 **栏** ，键入 DNS **区域**。</span><span class="sxs-lookup"><span data-stu-id="d6cef-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="d6cef-145">在结果显示中，选择 **"服务"部分下的"DNS** **区域** "。</span><span class="sxs-lookup"><span data-stu-id="d6cef-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="d6cef-146">重定向后，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="d6cef-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="d6cef-148">On the **Settings** page for your domain， in the **DNS zone** area， select + **Record set**.</span><span class="sxs-lookup"><span data-stu-id="d6cef-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="d6cef-150">在 **"添加记录集** "区域中新记录集的框内，从下表中选择值。</span><span class="sxs-lookup"><span data-stu-id="d6cef-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="d6cef-151"> (从下拉列表 **中选择 Type** 和 **TTL** 单位值。) </span><span class="sxs-lookup"><span data-stu-id="d6cef-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d6cef-152">**名称**</span><span class="sxs-lookup"><span data-stu-id="d6cef-152">**Name**</span></span>|<span data-ttu-id="d6cef-153">**类型**</span><span class="sxs-lookup"><span data-stu-id="d6cef-153">**Type**</span></span>|<span data-ttu-id="d6cef-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d6cef-154">**TTL**</span></span>|<span data-ttu-id="d6cef-155">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="d6cef-155">**TTL unit**</span></span>|<span data-ttu-id="d6cef-156">**值**</span><span class="sxs-lookup"><span data-stu-id="d6cef-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d6cef-157">TXT</span><span class="sxs-lookup"><span data-stu-id="d6cef-157">TXT</span></span>  <br/> |<span data-ttu-id="d6cef-158">1</span><span class="sxs-lookup"><span data-stu-id="d6cef-158">1</span></span>  <br/> |<span data-ttu-id="d6cef-159">工作时间</span><span class="sxs-lookup"><span data-stu-id="d6cef-159">Hours</span></span>  <br/> |<span data-ttu-id="d6cef-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d6cef-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d6cef-161">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="d6cef-161">**Note:** This is an example.</span></span> <span data-ttu-id="d6cef-162">在这里使用表中的特定“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="d6cef-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="d6cef-163">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="d6cef-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="d6cef-165">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="d6cef-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="d6cef-166">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="d6cef-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d6cef-167">在在域注册机构网站添加了记录后，你将返回到 Microsoft 并请求记录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d6cef-168">Microsof 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="d6cef-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="d6cef-169">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="d6cef-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d6cef-170">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="d6cef-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d6cef-171">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="d6cef-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d6cef-172">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="d6cef-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d6cef-p111">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d6cef-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d6cef-176">添加一条 MX 记录，确保发往你的域的电子邮件将会发送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6cef-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d6cef-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d6cef-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="d6cef-178">To get started， go to your domains page at Azure by using [this link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="d6cef-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="d6cef-179">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="d6cef-181">在 **"仪表板** "页上的" **所有** 资源"区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="d6cef-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="d6cef-183">On the **Settings** page for your domain， in the **DNS zone** area， select + **Record set**.</span><span class="sxs-lookup"><span data-stu-id="d6cef-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="d6cef-185">在 **"添加记录集** "区域中新记录集的框内，从下表中选择值。</span><span class="sxs-lookup"><span data-stu-id="d6cef-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="d6cef-186"> (从下拉列表 **中选择 Type** 和 **TTL** 单位值。) </span><span class="sxs-lookup"><span data-stu-id="d6cef-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d6cef-187">**名称**</span><span class="sxs-lookup"><span data-stu-id="d6cef-187">**Name**</span></span>|<span data-ttu-id="d6cef-188">**类型**</span><span class="sxs-lookup"><span data-stu-id="d6cef-188">**Type**</span></span>|<span data-ttu-id="d6cef-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d6cef-189">**TTL**</span></span>|<span data-ttu-id="d6cef-190">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="d6cef-190">**TTL unit**</span></span>|<span data-ttu-id="d6cef-191">**首选项**</span><span class="sxs-lookup"><span data-stu-id="d6cef-191">**Preference**</span></span>|<span data-ttu-id="d6cef-192">**邮件交换**</span><span class="sxs-lookup"><span data-stu-id="d6cef-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d6cef-193">MX</span><span class="sxs-lookup"><span data-stu-id="d6cef-193">MX</span></span>  <br/> |<span data-ttu-id="d6cef-194">1</span><span class="sxs-lookup"><span data-stu-id="d6cef-194">1</span></span>  <br/> |<span data-ttu-id="d6cef-195">工作时间</span><span class="sxs-lookup"><span data-stu-id="d6cef-195">Hours</span></span>  <br/> |<span data-ttu-id="d6cef-196">10  </span><span class="sxs-lookup"><span data-stu-id="d6cef-196">10</span></span>  <br/> <span data-ttu-id="d6cef-197">有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="d6cef-197">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="d6cef-198">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d6cef-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="d6cef-199">**注意：** 从  *\<domain-key\>*  Microsoft 帐户获取你的信息。</span><span class="sxs-lookup"><span data-stu-id="d6cef-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="d6cef-200">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="d6cef-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="d6cef-202">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="d6cef-202">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="d6cef-204">如果"MX 记录"部分列出了任何其他 **MX** 记录，则必须删除它们。</span><span class="sxs-lookup"><span data-stu-id="d6cef-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="d6cef-205">首先，在 **DNS 区域** 区域中，选择 **"MX 记录集"。**</span><span class="sxs-lookup"><span data-stu-id="d6cef-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-Configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="d6cef-207">接下来，选择要删除的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-Configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="d6cef-209">Select the **Context menu (...)**， and then choose **Remove**.</span><span class="sxs-lookup"><span data-stu-id="d6cef-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-Configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="d6cef-211">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d6cef-211">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d6cef-213">添加 Microsoft 所需的四条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="d6cef-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d6cef-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d6cef-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="d6cef-215">To get started， go to your domains page at Azure by using [this link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="d6cef-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="d6cef-216">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="d6cef-218">在 **"仪表板** "页上的" **所有** 资源"区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="d6cef-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="d6cef-220">On the **Settings** page for your domain， in the **DNS zone** area， select + **Record set**.</span><span class="sxs-lookup"><span data-stu-id="d6cef-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="d6cef-222">添加四条 CNAME 记录中的第一条。</span><span class="sxs-lookup"><span data-stu-id="d6cef-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="d6cef-223">在 **"添加记录集** "区域中新记录集的框内，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="d6cef-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="d6cef-224"> (从下拉列表 **中选择 Type** 和 **TTL** 单位值。) </span><span class="sxs-lookup"><span data-stu-id="d6cef-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d6cef-225">**名称**</span><span class="sxs-lookup"><span data-stu-id="d6cef-225">**Name**</span></span>|<span data-ttu-id="d6cef-226">**类型**</span><span class="sxs-lookup"><span data-stu-id="d6cef-226">**Type**</span></span>|<span data-ttu-id="d6cef-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d6cef-227">**TTL**</span></span>|<span data-ttu-id="d6cef-228">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="d6cef-228">**TTL unit**</span></span>|<span data-ttu-id="d6cef-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d6cef-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d6cef-230">自动发现</span><span class="sxs-lookup"><span data-stu-id="d6cef-230">autodiscover</span></span>  <br/> |<span data-ttu-id="d6cef-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="d6cef-231">CNAME</span></span>  <br/> |<span data-ttu-id="d6cef-232">1</span><span class="sxs-lookup"><span data-stu-id="d6cef-232">1</span></span>  <br/> |<span data-ttu-id="d6cef-233">工作时间</span><span class="sxs-lookup"><span data-stu-id="d6cef-233">Hours</span></span>  <br/> |<span data-ttu-id="d6cef-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d6cef-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="d6cef-235">sip</span><span class="sxs-lookup"><span data-stu-id="d6cef-235">sip</span></span>  <br/> |<span data-ttu-id="d6cef-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="d6cef-236">CNAME</span></span>  <br/> |<span data-ttu-id="d6cef-237">1</span><span class="sxs-lookup"><span data-stu-id="d6cef-237">1</span></span>  <br/> |<span data-ttu-id="d6cef-238">工作时间</span><span class="sxs-lookup"><span data-stu-id="d6cef-238">Hours</span></span>  <br/> |<span data-ttu-id="d6cef-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d6cef-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d6cef-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d6cef-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d6cef-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="d6cef-241">CNAME</span></span>  <br/> |<span data-ttu-id="d6cef-242">1</span><span class="sxs-lookup"><span data-stu-id="d6cef-242">1</span></span>  <br/> |<span data-ttu-id="d6cef-243">工作时间</span><span class="sxs-lookup"><span data-stu-id="d6cef-243">Hours</span></span>  <br/> |<span data-ttu-id="d6cef-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d6cef-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-Configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="d6cef-246">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="d6cef-246">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="d6cef-248">添加其他三条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="d6cef-249">在 **DNS 区域区域中，** 选择 **+ 记录集**。</span><span class="sxs-lookup"><span data-stu-id="d6cef-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="d6cef-250">然后，在空记录集内，使用表中下一行的值创建记录，然后再次选择"确定"以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="d6cef-251">重复此过程，直到创建所有四条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="d6cef-252"> (MDM) 添加 2 条 CNAME 记录。可选。</span><span class="sxs-lookup"><span data-stu-id="d6cef-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6cef-253">如果你有适用于 Microsoft 的移动设备 (MDM) ，则必须创建另外两条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="d6cef-254">创建流程与你用于其他四个 CNAME 记录的流程一样，但需提供下表中的值。</span><span class="sxs-lookup"><span data-stu-id="d6cef-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="d6cef-255"> (如果没有 MDM，可以跳过此步骤。) </span><span class="sxs-lookup"><span data-stu-id="d6cef-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="d6cef-256">**名称**</span><span class="sxs-lookup"><span data-stu-id="d6cef-256">**Name**</span></span>|<span data-ttu-id="d6cef-257">**类型**</span><span class="sxs-lookup"><span data-stu-id="d6cef-257">**Type**</span></span>|<span data-ttu-id="d6cef-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d6cef-258">**TTL**</span></span>|<span data-ttu-id="d6cef-259">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="d6cef-259">**TTL unit**</span></span>|<span data-ttu-id="d6cef-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d6cef-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d6cef-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d6cef-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d6cef-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="d6cef-262">CNAME</span></span>  <br/> |<span data-ttu-id="d6cef-263">1</span><span class="sxs-lookup"><span data-stu-id="d6cef-263">1</span></span>  <br/> |<span data-ttu-id="d6cef-264">工作时间</span><span class="sxs-lookup"><span data-stu-id="d6cef-264">Hours</span></span>  <br/> |<span data-ttu-id="d6cef-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d6cef-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="d6cef-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d6cef-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d6cef-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="d6cef-267">CNAME</span></span>  <br/> |<span data-ttu-id="d6cef-268">1</span><span class="sxs-lookup"><span data-stu-id="d6cef-268">1</span></span>  <br/> |<span data-ttu-id="d6cef-269">工作时间</span><span class="sxs-lookup"><span data-stu-id="d6cef-269">Hours</span></span>  <br/> |<span data-ttu-id="d6cef-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d6cef-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d6cef-271">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="d6cef-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d6cef-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d6cef-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6cef-273">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="d6cef-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d6cef-274">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="d6cef-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d6cef-275">如果你的域已有 SPF 记录，请不要为 Microsoft 创建新记录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d6cef-276">相反，将所需的 Microsoft 值添加到当前记录，以便你有一个  *包含这*  两组值的 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="d6cef-277">To get started， go to your domains page at Azure by using [this link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="d6cef-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="d6cef-278">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="d6cef-280">在 **"仪表板** "页上的" **所有** 资源"区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="d6cef-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="d6cef-282">在 **DNS 区域区域中** ，选择 **TXT 记录集**。</span><span class="sxs-lookup"><span data-stu-id="d6cef-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-Configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="d6cef-284">在" **记录集属性** "区域中新记录集的框内，从下表中选择值。</span><span class="sxs-lookup"><span data-stu-id="d6cef-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="d6cef-285"> (从下拉列表 **中选择 Type** 和 **TTL** 单位值。) </span><span class="sxs-lookup"><span data-stu-id="d6cef-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d6cef-286">**名称**</span><span class="sxs-lookup"><span data-stu-id="d6cef-286">**Name**</span></span>|<span data-ttu-id="d6cef-287">**类型**</span><span class="sxs-lookup"><span data-stu-id="d6cef-287">**Type**</span></span>|<span data-ttu-id="d6cef-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d6cef-288">**TTL**</span></span>|<span data-ttu-id="d6cef-289">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="d6cef-289">**TTL unit**</span></span>|<span data-ttu-id="d6cef-290">**值**</span><span class="sxs-lookup"><span data-stu-id="d6cef-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="d6cef-291">TXT</span><span class="sxs-lookup"><span data-stu-id="d6cef-291">TXT</span></span>  <br/> |<span data-ttu-id="d6cef-292">1</span><span class="sxs-lookup"><span data-stu-id="d6cef-292">1</span></span>  <br/> |<span data-ttu-id="d6cef-293">工作时间</span><span class="sxs-lookup"><span data-stu-id="d6cef-293">Hours</span></span>  <br/> |<span data-ttu-id="d6cef-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d6cef-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d6cef-295">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="d6cef-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-Configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="d6cef-297">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d6cef-297">Select **Save**.</span></span>
    
    ![Azure-BP-Configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d6cef-299">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="d6cef-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d6cef-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d6cef-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="d6cef-301">To get started， go to your domains page at Azure by using [this link](https://portal.azure.com ).</span><span class="sxs-lookup"><span data-stu-id="d6cef-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="d6cef-302">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="d6cef-304">在 **"仪表板** "页上的" **所有** 资源"区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="d6cef-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="d6cef-306">On the **Settings** page for your domain， in the **DNS zone** area， select + **Record set**.</span><span class="sxs-lookup"><span data-stu-id="d6cef-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="d6cef-308">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="d6cef-309">In the **Add record set** area， in the boxes for the new record set， select the values from the first row in the following table.</span><span class="sxs-lookup"><span data-stu-id="d6cef-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="d6cef-310"> (从下拉列表 **中选择 Type** 和 **TTL** 单位值。) </span><span class="sxs-lookup"><span data-stu-id="d6cef-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d6cef-311">**名称**</span><span class="sxs-lookup"><span data-stu-id="d6cef-311">**Name**</span></span>|<span data-ttu-id="d6cef-312">**类型**</span><span class="sxs-lookup"><span data-stu-id="d6cef-312">**Type**</span></span>|<span data-ttu-id="d6cef-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d6cef-313">**TTL**</span></span>|<span data-ttu-id="d6cef-314">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="d6cef-314">**TTL unit**</span></span>|<span data-ttu-id="d6cef-315">**优先级**</span><span class="sxs-lookup"><span data-stu-id="d6cef-315">**Priority**</span></span>|<span data-ttu-id="d6cef-316">**权重**</span><span class="sxs-lookup"><span data-stu-id="d6cef-316">**Weight**</span></span>|<span data-ttu-id="d6cef-317">**端口**</span><span class="sxs-lookup"><span data-stu-id="d6cef-317">**Port**</span></span>|<span data-ttu-id="d6cef-318">**目标**</span><span class="sxs-lookup"><span data-stu-id="d6cef-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d6cef-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="d6cef-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="d6cef-320">SRV</span><span class="sxs-lookup"><span data-stu-id="d6cef-320">SRV</span></span>  <br/> |<span data-ttu-id="d6cef-321">1</span><span class="sxs-lookup"><span data-stu-id="d6cef-321">1</span></span>  <br/> |<span data-ttu-id="d6cef-322">工作时间</span><span class="sxs-lookup"><span data-stu-id="d6cef-322">Hours</span></span>  <br/> |<span data-ttu-id="d6cef-323">100</span><span class="sxs-lookup"><span data-stu-id="d6cef-323">100</span></span>  <br/> |<span data-ttu-id="d6cef-324">1</span><span class="sxs-lookup"><span data-stu-id="d6cef-324">1</span></span>  <br/> |<span data-ttu-id="d6cef-325">443</span><span class="sxs-lookup"><span data-stu-id="d6cef-325">443</span></span>  <br/> |<span data-ttu-id="d6cef-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d6cef-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="d6cef-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="d6cef-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="d6cef-328">SRV</span><span class="sxs-lookup"><span data-stu-id="d6cef-328">SRV</span></span>  <br/> |<span data-ttu-id="d6cef-329">1</span><span class="sxs-lookup"><span data-stu-id="d6cef-329">1</span></span>  <br/> |<span data-ttu-id="d6cef-330">工作时间</span><span class="sxs-lookup"><span data-stu-id="d6cef-330">Hours</span></span>  <br/> |<span data-ttu-id="d6cef-331">100</span><span class="sxs-lookup"><span data-stu-id="d6cef-331">100</span></span>  <br/> |<span data-ttu-id="d6cef-332">1</span><span class="sxs-lookup"><span data-stu-id="d6cef-332">1</span></span>  <br/> |<span data-ttu-id="d6cef-333">5061</span><span class="sxs-lookup"><span data-stu-id="d6cef-333">5061</span></span>  <br/> |<span data-ttu-id="d6cef-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d6cef-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-Configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="d6cef-336">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="d6cef-336">Select **OK**.</span></span>
    
    ![Azure-BP-Configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="d6cef-338">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="d6cef-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="d6cef-339">In the boxes for the new record， type or copy and paste the values from the second row of the table.</span><span class="sxs-lookup"><span data-stu-id="d6cef-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d6cef-p120">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="d6cef-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
