---
title: 为 Azure DNS 区域创建 DNS 记录
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: 了解如何验证您的域并为 Microsoft 的 Azure DNS 区域中的电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 7104fb18a6581b7ebc853f938b85171ae1886cfd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629139"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="45175-103">为 Azure DNS 区域创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="45175-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="45175-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="45175-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="45175-105">如果 Azure 是你的 DNS 托管提供商，请按照本文中的步骤验证你的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="45175-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="45175-106">下面是要添加的主要记录。</span><span class="sxs-lookup"><span data-stu-id="45175-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="45175-107">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="45175-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="45175-108">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="45175-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="45175-109">添加 MX 记录，以便你的域的电子邮件将发送给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="45175-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="45175-110">添加 Microsoft 所需的四个 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="45175-110">Add the four CNAME records that are required for Microsoft</span></span>](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="45175-111">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="45175-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="45175-112">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="45175-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="45175-113">在 Azure 中添加这些记录后，您的域将设置为与 Microsoft 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="45175-113">After you add these records at Azure, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="45175-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="45175-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="45175-117">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="45175-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="45175-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="45175-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="45175-119">必须在购买和注册域的域注册机构中执行此过程。</span><span class="sxs-lookup"><span data-stu-id="45175-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="45175-120">注册 Azure 时，您在 DNS 区域中创建了一个资源组，然后将您的域名分配给该资源组。</span><span class="sxs-lookup"><span data-stu-id="45175-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="45175-121">该域名注册到外部域注册机构;Azure 不提供域注册服务。</span><span class="sxs-lookup"><span data-stu-id="45175-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="45175-122">若要在 Microsoft 中验证和创建域的 DNS 记录，首先需要更改域注册机构中的名称服务器，以便它们使用分配给资源组的 Azure 名称服务器。</span><span class="sxs-lookup"><span data-stu-id="45175-122">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="45175-123">若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="45175-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="45175-124">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="45175-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="45175-125">通过使用下表中的值创建两个名称服务器记录，或编辑现有的名称服务器记录以使其与这些值匹配。</span><span class="sxs-lookup"><span data-stu-id="45175-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="45175-126">下面显示了 Azure 分配的名称服务器的示例。</span><span class="sxs-lookup"><span data-stu-id="45175-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="45175-127">**第一个**名称服务器：使用 Azure 分配的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="45175-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="45175-128">**第二个 nameserver：** 使用 Azure 分配的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="45175-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-委派-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="45175-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="45175-130">You should use at least two name server records.</span></span> <span data-ttu-id="45175-131">如果在域注册机构的网站上列出了任何其他名称服务器，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="45175-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="45175-132">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="45175-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="45175-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="45175-133">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="45175-134">然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。</span><span class="sxs-lookup"><span data-stu-id="45175-134">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="45175-135">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="45175-135">Add a TXT record for verification</span></span>
<span data-ttu-id="45175-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="45175-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="45175-137">在将你的域用于 Microsoft 之前，我们必须确保你拥有此域。</span><span class="sxs-lookup"><span data-stu-id="45175-137">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="45175-138">你能够在域注册机构登录到你的帐户，并创建向 Microsoft 证明你拥有该域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="45175-138">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="45175-p107">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="45175-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="45175-141">若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="45175-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="45175-142">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="45175-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="45175-144">在**仪表板**页面上使用**搜索栏**，在 " **DNS 区域**" 中键入。</span><span class="sxs-lookup"><span data-stu-id="45175-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="45175-145">在 "结果显示" 中，选择 "**服务**" 部分下的 " **DNS 区域**"。</span><span class="sxs-lookup"><span data-stu-id="45175-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="45175-146">重定向后，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="45175-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="45175-148">在您的域的 "**设置**" 页上的 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。</span><span class="sxs-lookup"><span data-stu-id="45175-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-配置-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="45175-150">在 "**添加记录集**" 区域中新记录集对应的框中，选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="45175-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="45175-151">（从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。）</span><span class="sxs-lookup"><span data-stu-id="45175-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="45175-152">**名称**</span><span class="sxs-lookup"><span data-stu-id="45175-152">**Name**</span></span>|<span data-ttu-id="45175-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="45175-153">**Type**</span></span>|<span data-ttu-id="45175-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="45175-154">**TTL**</span></span>|<span data-ttu-id="45175-155">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="45175-155">**TTL unit**</span></span>|<span data-ttu-id="45175-156">**值**</span><span class="sxs-lookup"><span data-stu-id="45175-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="45175-157">TXT</span><span class="sxs-lookup"><span data-stu-id="45175-157">TXT</span></span>  <br/> |<span data-ttu-id="45175-158">1</span><span class="sxs-lookup"><span data-stu-id="45175-158">1</span></span>  <br/> |<span data-ttu-id="45175-159">工作时间</span><span class="sxs-lookup"><span data-stu-id="45175-159">Hours</span></span>  <br/> |<span data-ttu-id="45175-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="45175-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="45175-161">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="45175-161">**Note:** This is an example.</span></span> <span data-ttu-id="45175-162">从表中使用您的特定**目标或指向 "地址**" 值。</span><span class="sxs-lookup"><span data-stu-id="45175-162">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="45175-163">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="45175-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-最佳验证-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="45175-165">选择“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45175-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="45175-166">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="45175-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="45175-167">现在您已在域注册机构的网站上添加了记录，您将返回到 Microsoft 并请求该记录。</span><span class="sxs-lookup"><span data-stu-id="45175-167">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="45175-168">当 Microsoft 找到正确的 TXT 记录时，您的域将会得到验证。</span><span class="sxs-lookup"><span data-stu-id="45175-168">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="45175-169">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="45175-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="45175-170">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="45175-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="45175-171">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="45175-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="45175-172">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="45175-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="45175-p111">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="45175-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="45175-176">添加 MX 记录，以便你的域的电子邮件将发送给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="45175-176">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="45175-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="45175-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="45175-178">若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="45175-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="45175-179">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="45175-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="45175-181">在 "**仪表板**" 页上的 "**所有资源**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="45175-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="45175-183">在您的域的 "**设置**" 页上的 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。</span><span class="sxs-lookup"><span data-stu-id="45175-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-配置-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="45175-185">在 "**添加记录集**" 区域中新记录集对应的框中，选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="45175-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="45175-186">（从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。）</span><span class="sxs-lookup"><span data-stu-id="45175-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="45175-187">**名称**</span><span class="sxs-lookup"><span data-stu-id="45175-187">**Name**</span></span>|<span data-ttu-id="45175-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="45175-188">**Type**</span></span>|<span data-ttu-id="45175-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="45175-189">**TTL**</span></span>|<span data-ttu-id="45175-190">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="45175-190">**TTL unit**</span></span>|<span data-ttu-id="45175-191">**首选项**</span><span class="sxs-lookup"><span data-stu-id="45175-191">**Preference**</span></span>|<span data-ttu-id="45175-192">**邮件交换**</span><span class="sxs-lookup"><span data-stu-id="45175-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="45175-193">MX</span><span class="sxs-lookup"><span data-stu-id="45175-193">MX</span></span>  <br/> |<span data-ttu-id="45175-194">1</span><span class="sxs-lookup"><span data-stu-id="45175-194">1</span></span>  <br/> |<span data-ttu-id="45175-195">工作时间</span><span class="sxs-lookup"><span data-stu-id="45175-195">Hours</span></span>  <br/> |<span data-ttu-id="45175-196">10 </span><span class="sxs-lookup"><span data-stu-id="45175-196">10</span></span>  <br/> <span data-ttu-id="45175-197">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="45175-197">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="45175-198">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="45175-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="45175-199">**注意：** 从你的 Microsoft 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="45175-199">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="45175-200">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="45175-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-配置-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="45175-202">选择“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45175-202">Select **OK**.</span></span>
    
    ![Azure-BP-配置-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="45175-204">如果 " **Mx 记录**" 一节中列出了任何其他 MX 记录，则必须将其删除。</span><span class="sxs-lookup"><span data-stu-id="45175-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="45175-205">首先，在 " **DNS 区域**" 区域中，选择**MX 记录集**。</span><span class="sxs-lookup"><span data-stu-id="45175-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-配置-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="45175-207">接下来，选择要删除的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="45175-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-配置-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="45175-209">选择**上下文菜单（**"..."），然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="45175-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-配置-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="45175-211">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="45175-211">Select **Save**.</span></span>
    
    ![Azure-BP-配置-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="45175-213">添加 Microsoft 所需的四个 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="45175-213">Add the four CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="45175-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="45175-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="45175-215">若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="45175-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="45175-216">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="45175-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="45175-218">在 "**仪表板**" 页上的 "**所有资源**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="45175-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="45175-220">在您的域的 "**设置**" 页上的 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。</span><span class="sxs-lookup"><span data-stu-id="45175-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-配置-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="45175-222">添加四个 CNAME 记录中的第一个。</span><span class="sxs-lookup"><span data-stu-id="45175-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="45175-223">在 "**添加记录集**" 区域中新记录集对应的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="45175-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="45175-224">（从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。）</span><span class="sxs-lookup"><span data-stu-id="45175-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="45175-225">**名称**</span><span class="sxs-lookup"><span data-stu-id="45175-225">**Name**</span></span>|<span data-ttu-id="45175-226">**Type**</span><span class="sxs-lookup"><span data-stu-id="45175-226">**Type**</span></span>|<span data-ttu-id="45175-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="45175-227">**TTL**</span></span>|<span data-ttu-id="45175-228">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="45175-228">**TTL unit**</span></span>|<span data-ttu-id="45175-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="45175-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="45175-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="45175-230">autodiscover</span></span>  <br/> |<span data-ttu-id="45175-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="45175-231">CNAME</span></span>  <br/> |<span data-ttu-id="45175-232">1</span><span class="sxs-lookup"><span data-stu-id="45175-232">1</span></span>  <br/> |<span data-ttu-id="45175-233">工作时间</span><span class="sxs-lookup"><span data-stu-id="45175-233">Hours</span></span>  <br/> |<span data-ttu-id="45175-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="45175-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="45175-235">sip</span><span class="sxs-lookup"><span data-stu-id="45175-235">sip</span></span>  <br/> |<span data-ttu-id="45175-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="45175-236">CNAME</span></span>  <br/> |<span data-ttu-id="45175-237">1</span><span class="sxs-lookup"><span data-stu-id="45175-237">1</span></span>  <br/> |<span data-ttu-id="45175-238">工作时间</span><span class="sxs-lookup"><span data-stu-id="45175-238">Hours</span></span>  <br/> |<span data-ttu-id="45175-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="45175-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="45175-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="45175-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="45175-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="45175-241">CNAME</span></span>  <br/> |<span data-ttu-id="45175-242">1</span><span class="sxs-lookup"><span data-stu-id="45175-242">1</span></span>  <br/> |<span data-ttu-id="45175-243">工作时间</span><span class="sxs-lookup"><span data-stu-id="45175-243">Hours</span></span>  <br/> |<span data-ttu-id="45175-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="45175-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-配置-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="45175-246">选择“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45175-246">Select **OK**.</span></span>
    
    ![Azure-BP-配置-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="45175-248">添加其他三个 CNAME 记录中的每一个。</span><span class="sxs-lookup"><span data-stu-id="45175-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="45175-249">在 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。</span><span class="sxs-lookup"><span data-stu-id="45175-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="45175-250">然后，在空记录集中，使用表中下一行的值创建记录，然后再次选择 **"确定"** 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="45175-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="45175-251">重复此过程，直到创建了全部四个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="45175-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="45175-252">Optional为 MDM 添加2个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="45175-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45175-253">如果你具有适用于 Microsoft 的移动设备管理（MDM），则必须创建两个附加的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="45175-253">If you have Mobile Device Management (MDM) for Microsoft, then you must create two additional CNAME records.</span></span> <span data-ttu-id="45175-254">创建流程与你用于其他四个 CNAME 记录的流程一样，但需提供下表中的值。</span><span class="sxs-lookup"><span data-stu-id="45175-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="45175-255">（如果没有 MDM，则可以跳过此步骤。）</span><span class="sxs-lookup"><span data-stu-id="45175-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="45175-256">**名称**</span><span class="sxs-lookup"><span data-stu-id="45175-256">**Name**</span></span>|<span data-ttu-id="45175-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="45175-257">**Type**</span></span>|<span data-ttu-id="45175-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="45175-258">**TTL**</span></span>|<span data-ttu-id="45175-259">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="45175-259">**TTL unit**</span></span>|<span data-ttu-id="45175-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="45175-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45175-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="45175-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="45175-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="45175-262">CNAME</span></span>  <br/> |<span data-ttu-id="45175-263">1</span><span class="sxs-lookup"><span data-stu-id="45175-263">1</span></span>  <br/> |<span data-ttu-id="45175-264">工作时间</span><span class="sxs-lookup"><span data-stu-id="45175-264">Hours</span></span>  <br/> |<span data-ttu-id="45175-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="45175-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="45175-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="45175-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="45175-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="45175-267">CNAME</span></span>  <br/> |<span data-ttu-id="45175-268">1</span><span class="sxs-lookup"><span data-stu-id="45175-268">1</span></span>  <br/> |<span data-ttu-id="45175-269">工作时间</span><span class="sxs-lookup"><span data-stu-id="45175-269">Hours</span></span>  <br/> |<span data-ttu-id="45175-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="45175-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="45175-271">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="45175-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="45175-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="45175-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="45175-273">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="45175-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="45175-274">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="45175-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="45175-275">如果你已有域的 SPF 记录，请不要为 Microsoft 创建一个新的。</span><span class="sxs-lookup"><span data-stu-id="45175-275">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="45175-276">改为将所需的 Microsoft 值添加到当前记录，以便您具有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="45175-276">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="45175-277">若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="45175-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="45175-278">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="45175-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="45175-280">在 "**仪表板**" 页上的 "**所有资源**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="45175-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="45175-282">在 " **DNS 区域**" 区域中，选择 " **TXT" 记录集**。</span><span class="sxs-lookup"><span data-stu-id="45175-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-配置-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="45175-284">在 "**记录集属性**" 区域中新记录集对应的框中，选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="45175-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="45175-285">（从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。）</span><span class="sxs-lookup"><span data-stu-id="45175-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="45175-286">**名称**</span><span class="sxs-lookup"><span data-stu-id="45175-286">**Name**</span></span>|<span data-ttu-id="45175-287">**Type**</span><span class="sxs-lookup"><span data-stu-id="45175-287">**Type**</span></span>|<span data-ttu-id="45175-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="45175-288">**TTL**</span></span>|<span data-ttu-id="45175-289">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="45175-289">**TTL unit**</span></span>|<span data-ttu-id="45175-290">**值**</span><span class="sxs-lookup"><span data-stu-id="45175-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="45175-291">TXT</span><span class="sxs-lookup"><span data-stu-id="45175-291">TXT</span></span>  <br/> |<span data-ttu-id="45175-292">1</span><span class="sxs-lookup"><span data-stu-id="45175-292">1</span></span>  <br/> |<span data-ttu-id="45175-293">工作时间</span><span class="sxs-lookup"><span data-stu-id="45175-293">Hours</span></span>  <br/> |<span data-ttu-id="45175-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="45175-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="45175-295">**注意：** 我们建议您复制并粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="45175-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-配置-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="45175-297">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="45175-297">Select **Save**.</span></span>
    
    ![Azure-BP-配置-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="45175-299">添加 Microsoft 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="45175-299">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="45175-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="45175-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="45175-301">若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="45175-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="45175-302">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="45175-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="45175-304">在 "**仪表板**" 页上的 "**所有资源**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="45175-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="45175-306">在您的域的 "**设置**" 页上的 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。</span><span class="sxs-lookup"><span data-stu-id="45175-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-配置-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="45175-308">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="45175-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="45175-309">在 "**添加记录集**" 区域中新记录集对应的框中，选择下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="45175-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="45175-310">（从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。）</span><span class="sxs-lookup"><span data-stu-id="45175-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="45175-311">**名称**</span><span class="sxs-lookup"><span data-stu-id="45175-311">**Name**</span></span>|<span data-ttu-id="45175-312">**Type**</span><span class="sxs-lookup"><span data-stu-id="45175-312">**Type**</span></span>|<span data-ttu-id="45175-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="45175-313">**TTL**</span></span>|<span data-ttu-id="45175-314">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="45175-314">**TTL unit**</span></span>|<span data-ttu-id="45175-315">**优先级**</span><span class="sxs-lookup"><span data-stu-id="45175-315">**Priority**</span></span>|<span data-ttu-id="45175-316">**权重**</span><span class="sxs-lookup"><span data-stu-id="45175-316">**Weight**</span></span>|<span data-ttu-id="45175-317">**端口**</span><span class="sxs-lookup"><span data-stu-id="45175-317">**Port**</span></span>|<span data-ttu-id="45175-318">**目标**</span><span class="sxs-lookup"><span data-stu-id="45175-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="45175-319">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="45175-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="45175-320">SRV</span><span class="sxs-lookup"><span data-stu-id="45175-320">SRV</span></span>  <br/> |<span data-ttu-id="45175-321">1</span><span class="sxs-lookup"><span data-stu-id="45175-321">1</span></span>  <br/> |<span data-ttu-id="45175-322">工作时间</span><span class="sxs-lookup"><span data-stu-id="45175-322">Hours</span></span>  <br/> |<span data-ttu-id="45175-323">100</span><span class="sxs-lookup"><span data-stu-id="45175-323">100</span></span>  <br/> |<span data-ttu-id="45175-324">1</span><span class="sxs-lookup"><span data-stu-id="45175-324">1</span></span>  <br/> |<span data-ttu-id="45175-325">443</span><span class="sxs-lookup"><span data-stu-id="45175-325">443</span></span>  <br/> |<span data-ttu-id="45175-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="45175-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="45175-327">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="45175-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="45175-328">SRV</span><span class="sxs-lookup"><span data-stu-id="45175-328">SRV</span></span>  <br/> |<span data-ttu-id="45175-329">1</span><span class="sxs-lookup"><span data-stu-id="45175-329">1</span></span>  <br/> |<span data-ttu-id="45175-330">工作时间</span><span class="sxs-lookup"><span data-stu-id="45175-330">Hours</span></span>  <br/> |<span data-ttu-id="45175-331">100</span><span class="sxs-lookup"><span data-stu-id="45175-331">100</span></span>  <br/> |<span data-ttu-id="45175-332">1</span><span class="sxs-lookup"><span data-stu-id="45175-332">1</span></span>  <br/> |<span data-ttu-id="45175-333">5061</span><span class="sxs-lookup"><span data-stu-id="45175-333">5061</span></span>  <br/> |<span data-ttu-id="45175-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="45175-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-配置-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="45175-336">选择“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45175-336">Select **OK**.</span></span>
    
    ![Azure-BP-配置-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="45175-338">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="45175-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="45175-339">在新记录的框中，键入或复制并粘贴表中第二行的值。</span><span class="sxs-lookup"><span data-stu-id="45175-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="45175-p120">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="45175-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
