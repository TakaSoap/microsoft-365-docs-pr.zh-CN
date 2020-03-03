---
title: 为 Azure DNS 区域创建 DNS 记录
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: 了解如何验证您的域并为 Office 365 的 Azure DNS 区域中的电子邮件、Skype for Business Online 和其他服务设置 DNS 记录。
ms.openlocfilehash: 30e54da8ffd51165b1cc0d2eb82d9d02eefdaf4d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362737"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="2ec42-103">为 Azure DNS 区域创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="2ec42-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="2ec42-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="2ec42-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2ec42-105">如果 Azure 是你的 DNS 托管提供商，请按照本文中的步骤验证你的域并为电子邮件、Skype for Business Online 等设置 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="2ec42-106">下面是要添加的主要记录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="2ec42-107">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="2ec42-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="2ec42-108">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="2ec42-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="2ec42-109">添加一条 MX 记录，确保发往您的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="2ec42-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="2ec42-110">添加 Office 365 所需的四个 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="2ec42-110">Add the four CNAME records that are required for Office 365</span></span>](#add-the-four-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="2ec42-111">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="2ec42-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="2ec42-112">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="2ec42-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="2ec42-113">在 Azure 中添加这些记录后，您的域将设置为与 Office 365 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="2ec42-113">After you add these records at Azure, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ec42-p101">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="2ec42-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="2ec42-117">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="2ec42-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="2ec42-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="2ec42-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ec42-119">必须在购买和注册域的域注册机构中执行此过程。</span><span class="sxs-lookup"><span data-stu-id="2ec42-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="2ec42-120">注册 Azure 时，您在 DNS 区域中创建了一个资源组，然后将您的域名分配给该资源组。</span><span class="sxs-lookup"><span data-stu-id="2ec42-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="2ec42-121">该域名注册到外部域注册机构;Azure 不提供域注册服务。</span><span class="sxs-lookup"><span data-stu-id="2ec42-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="2ec42-122">若要在 Office 365 中验证和创建域的 DNS 记录，首先需要更改域注册机构中的名称服务器，以便它们使用分配给您的资源组的 Azure 名称服务器。</span><span class="sxs-lookup"><span data-stu-id="2ec42-122">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="2ec42-123">若要在域注册机构的网站上更改域的名称服务器，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="2ec42-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="2ec42-124">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="2ec42-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="2ec42-125">通过使用下表中的值创建两个名称服务器记录，或编辑现有的名称服务器记录以使其与这些值匹配。</span><span class="sxs-lookup"><span data-stu-id="2ec42-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="2ec42-126">下面显示了 Azure 分配的名称服务器的示例。</span><span class="sxs-lookup"><span data-stu-id="2ec42-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="2ec42-127">**第一个**名称服务器：使用 Azure 分配的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="2ec42-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="2ec42-128">**第二个 nameserver：** 使用 Azure 分配的名称服务器值。</span><span class="sxs-lookup"><span data-stu-id="2ec42-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Azure-BP-委派-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="2ec42-130">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="2ec42-130">You should use at least two name server records.</span></span> <span data-ttu-id="2ec42-131">如果在域注册机构的网站上列出了任何其他名称服务器，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="2ec42-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="2ec42-132">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2ec42-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2ec42-p105">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="2ec42-p105">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2ec42-135">添加 TXT 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="2ec42-135">Add a TXT record for verification</span></span>
<span data-ttu-id="2ec42-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2ec42-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2ec42-p106">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="2ec42-p106">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ec42-p107">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="2ec42-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="2ec42-141">若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="2ec42-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="2ec42-142">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-142">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="2ec42-144">在**仪表板**页面上使用**搜索栏**，在 " **DNS 区域**" 中键入。</span><span class="sxs-lookup"><span data-stu-id="2ec42-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="2ec42-145">在 "结果显示" 中，选择 "**服务**" 部分下的 " **DNS 区域**"。</span><span class="sxs-lookup"><span data-stu-id="2ec42-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="2ec42-146">重定向后，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="2ec42-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="2ec42-148">在您的域的 "**设置**" 页上的 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。</span><span class="sxs-lookup"><span data-stu-id="2ec42-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-配置-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="2ec42-150">在 "**添加记录集**" 区域中新记录集对应的框中，选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="2ec42-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="2ec42-151">（从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。）</span><span class="sxs-lookup"><span data-stu-id="2ec42-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="2ec42-152">**名称**</span><span class="sxs-lookup"><span data-stu-id="2ec42-152">**Name**</span></span>|<span data-ttu-id="2ec42-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="2ec42-153">**Type**</span></span>|<span data-ttu-id="2ec42-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2ec42-154">**TTL**</span></span>|<span data-ttu-id="2ec42-155">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="2ec42-155">**TTL unit**</span></span>|<span data-ttu-id="2ec42-156">**值**</span><span class="sxs-lookup"><span data-stu-id="2ec42-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2ec42-157">TXT</span><span class="sxs-lookup"><span data-stu-id="2ec42-157">TXT</span></span>  <br/> |<span data-ttu-id="2ec42-158">1</span><span class="sxs-lookup"><span data-stu-id="2ec42-158">1</span></span>  <br/> |<span data-ttu-id="2ec42-159">工作时间</span><span class="sxs-lookup"><span data-stu-id="2ec42-159">Hours</span></span>  <br/> |<span data-ttu-id="2ec42-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2ec42-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2ec42-161">**注意：** 此为示例。</span><span class="sxs-lookup"><span data-stu-id="2ec42-161">**Note:** This is an example.</span></span> <span data-ttu-id="2ec42-162">在这里使用来自 Office 365 中的表的具体**目标地址或指向的地址**值。</span><span class="sxs-lookup"><span data-stu-id="2ec42-162">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="2ec42-163">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="2ec42-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-最佳验证-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="2ec42-165">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="2ec42-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="2ec42-166">请在继续之前等待数分钟，以便您刚刚创建的记录可以通过 Internet 完成更新。</span><span class="sxs-lookup"><span data-stu-id="2ec42-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="2ec42-167">现在你已在域注册机构网站添加了记录，然后将返回到 Office 365 并请求 Office 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-167">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="2ec42-168">Office 365 找到正确的 TXT 记录时，表明你的域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="2ec42-168">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="2ec42-169">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="2ec42-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="2ec42-170">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="2ec42-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="2ec42-171">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="2ec42-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="2ec42-172">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="2ec42-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="2ec42-p111">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="2ec42-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="2ec42-176">添加一条 MX 记录，确保发往你的域的电子邮件发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="2ec42-176">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="2ec42-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2ec42-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="2ec42-178">若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="2ec42-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="2ec42-179">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-179">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="2ec42-181">在 "**仪表板**" 页上的 "**所有资源**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="2ec42-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="2ec42-183">在您的域的 "**设置**" 页上的 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。</span><span class="sxs-lookup"><span data-stu-id="2ec42-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-配置-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="2ec42-185">在 "**添加记录集**" 区域中新记录集对应的框中，选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="2ec42-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="2ec42-186">（从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。）</span><span class="sxs-lookup"><span data-stu-id="2ec42-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="2ec42-187">**名称**</span><span class="sxs-lookup"><span data-stu-id="2ec42-187">**Name**</span></span>|<span data-ttu-id="2ec42-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="2ec42-188">**Type**</span></span>|<span data-ttu-id="2ec42-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2ec42-189">**TTL**</span></span>|<span data-ttu-id="2ec42-190">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="2ec42-190">**TTL unit**</span></span>|<span data-ttu-id="2ec42-191">**首选项**</span><span class="sxs-lookup"><span data-stu-id="2ec42-191">**Preference**</span></span>|<span data-ttu-id="2ec42-192">**邮件交换**</span><span class="sxs-lookup"><span data-stu-id="2ec42-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2ec42-193">MX</span><span class="sxs-lookup"><span data-stu-id="2ec42-193">MX</span></span>  <br/> |<span data-ttu-id="2ec42-194">1</span><span class="sxs-lookup"><span data-stu-id="2ec42-194">1</span></span>  <br/> |<span data-ttu-id="2ec42-195">工作时间</span><span class="sxs-lookup"><span data-stu-id="2ec42-195">Hours</span></span>  <br/> |<span data-ttu-id="2ec42-196">10 </span><span class="sxs-lookup"><span data-stu-id="2ec42-196">10</span></span>  <br/> <span data-ttu-id="2ec42-197">有关优先级的详细信息，请参阅[什么是 MX 优先级？](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="2ec42-197">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="2ec42-198">*\<域密钥\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2ec42-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="2ec42-199">**注意：** 从 Office 365 帐户中获取你\* \<的域密钥\> \* 。</span><span class="sxs-lookup"><span data-stu-id="2ec42-199">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="2ec42-200">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="2ec42-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-配置-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="2ec42-202">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="2ec42-202">Select **OK**.</span></span>
    
    ![Azure-BP-配置-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="2ec42-204">如果 " **Mx 记录**" 一节中列出了任何其他 MX 记录，则必须将其删除。</span><span class="sxs-lookup"><span data-stu-id="2ec42-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="2ec42-205">首先，在 " **DNS 区域**" 区域中，选择**MX 记录集**。</span><span class="sxs-lookup"><span data-stu-id="2ec42-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Azure-BP-配置-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="2ec42-207">接下来，选择要删除的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-207">Next, select the MX record you want to delete.</span></span>
    
    ![Azure-BP-配置-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="2ec42-209">选择**上下文菜单（**"..."），然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="2ec42-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Azure-BP-配置-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="2ec42-211">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="2ec42-211">Select **Save**.</span></span>
    
    ![Azure-BP-配置-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="2ec42-213">添加 Office 365 所需的四个 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="2ec42-213">Add the four CNAME records that are required for Office 365</span></span>
<span data-ttu-id="2ec42-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2ec42-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="2ec42-215">若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="2ec42-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="2ec42-216">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-216">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="2ec42-218">在 "**仪表板**" 页上的 "**所有资源**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="2ec42-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="2ec42-220">在您的域的 "**设置**" 页上的 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。</span><span class="sxs-lookup"><span data-stu-id="2ec42-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-配置-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="2ec42-222">添加四个 CNAME 记录中的第一个。</span><span class="sxs-lookup"><span data-stu-id="2ec42-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="2ec42-223">在 "**添加记录集**" 区域中新记录集对应的框中，键入或复制并粘贴下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="2ec42-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="2ec42-224">（从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。）</span><span class="sxs-lookup"><span data-stu-id="2ec42-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="2ec42-225">**名称**</span><span class="sxs-lookup"><span data-stu-id="2ec42-225">**Name**</span></span>|<span data-ttu-id="2ec42-226">**Type**</span><span class="sxs-lookup"><span data-stu-id="2ec42-226">**Type**</span></span>|<span data-ttu-id="2ec42-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2ec42-227">**TTL**</span></span>|<span data-ttu-id="2ec42-228">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="2ec42-228">**TTL unit**</span></span>|<span data-ttu-id="2ec42-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="2ec42-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2ec42-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2ec42-230">autodiscover</span></span>  <br/> |<span data-ttu-id="2ec42-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="2ec42-231">CNAME</span></span>  <br/> |<span data-ttu-id="2ec42-232">1</span><span class="sxs-lookup"><span data-stu-id="2ec42-232">1</span></span>  <br/> |<span data-ttu-id="2ec42-233">工作时间</span><span class="sxs-lookup"><span data-stu-id="2ec42-233">Hours</span></span>  <br/> |<span data-ttu-id="2ec42-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2ec42-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="2ec42-235">sip</span><span class="sxs-lookup"><span data-stu-id="2ec42-235">sip</span></span>  <br/> |<span data-ttu-id="2ec42-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="2ec42-236">CNAME</span></span>  <br/> |<span data-ttu-id="2ec42-237">1</span><span class="sxs-lookup"><span data-stu-id="2ec42-237">1</span></span>  <br/> |<span data-ttu-id="2ec42-238">工作时间</span><span class="sxs-lookup"><span data-stu-id="2ec42-238">Hours</span></span>  <br/> |<span data-ttu-id="2ec42-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2ec42-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2ec42-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2ec42-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="2ec42-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="2ec42-241">CNAME</span></span>  <br/> |<span data-ttu-id="2ec42-242">1</span><span class="sxs-lookup"><span data-stu-id="2ec42-242">1</span></span>  <br/> |<span data-ttu-id="2ec42-243">工作时间</span><span class="sxs-lookup"><span data-stu-id="2ec42-243">Hours</span></span>  <br/> |<span data-ttu-id="2ec42-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2ec42-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Azure-BP-配置-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="2ec42-246">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="2ec42-246">Select **OK**.</span></span>
    
    ![Azure-BP-配置-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="2ec42-248">添加其他三个 CNAME 记录中的每一个。</span><span class="sxs-lookup"><span data-stu-id="2ec42-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="2ec42-249">在 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。</span><span class="sxs-lookup"><span data-stu-id="2ec42-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="2ec42-250">然后，在空记录集中，使用表中下一行的值创建记录，然后再次选择 **"确定"** 以完成该记录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="2ec42-251">重复此过程，直到创建了全部四个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="2ec42-252">Optional为 MDM 添加2个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ec42-253">如果您有 Office 365 的 Mobile Device Manager (MDM)，则必须创建另外两个 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-253">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="2ec42-254">创建流程与你用于其他四个 CNAME 记录的流程一样，但需提供下表中的值。</span><span class="sxs-lookup"><span data-stu-id="2ec42-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="2ec42-255">（如果没有 MDM，则可以跳过此步骤。）</span><span class="sxs-lookup"><span data-stu-id="2ec42-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="2ec42-256">**名称**</span><span class="sxs-lookup"><span data-stu-id="2ec42-256">**Name**</span></span>|<span data-ttu-id="2ec42-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="2ec42-257">**Type**</span></span>|<span data-ttu-id="2ec42-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2ec42-258">**TTL**</span></span>|<span data-ttu-id="2ec42-259">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="2ec42-259">**TTL unit**</span></span>|<span data-ttu-id="2ec42-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="2ec42-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2ec42-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2ec42-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="2ec42-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="2ec42-262">CNAME</span></span>  <br/> |<span data-ttu-id="2ec42-263">1</span><span class="sxs-lookup"><span data-stu-id="2ec42-263">1</span></span>  <br/> |<span data-ttu-id="2ec42-264">工作时间</span><span class="sxs-lookup"><span data-stu-id="2ec42-264">Hours</span></span>  <br/> |<span data-ttu-id="2ec42-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="2ec42-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="2ec42-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2ec42-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="2ec42-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="2ec42-267">CNAME</span></span>  <br/> |<span data-ttu-id="2ec42-268">1</span><span class="sxs-lookup"><span data-stu-id="2ec42-268">1</span></span>  <br/> |<span data-ttu-id="2ec42-269">工作时间</span><span class="sxs-lookup"><span data-stu-id="2ec42-269">Hours</span></span>  <br/> |<span data-ttu-id="2ec42-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2ec42-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2ec42-271">为 SPF 添加 TXT 记录以帮助防止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="2ec42-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2ec42-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="2ec42-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ec42-273">一个域所拥有的 SPF 的 TXT 记录不能超过一个。</span><span class="sxs-lookup"><span data-stu-id="2ec42-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2ec42-274">如果域具有多个 SPF 记录，你将收到电子邮件错误，其中随附发送和垃圾邮件分类问题。</span><span class="sxs-lookup"><span data-stu-id="2ec42-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2ec42-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ec42-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="2ec42-276">可以将所需的 Office 365 添加到当前记录，这样就拥有包含两组值的*单个*SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-276">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="2ec42-277">若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="2ec42-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="2ec42-278">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-278">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="2ec42-280">在 "**仪表板**" 页上的 "**所有资源**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="2ec42-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="2ec42-282">在 " **DNS 区域**" 区域中，选择 " **TXT" 记录集**。</span><span class="sxs-lookup"><span data-stu-id="2ec42-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Azure-BP-配置-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="2ec42-284">在 "**记录集属性**" 区域中新记录集对应的框中，选择下表中的值。</span><span class="sxs-lookup"><span data-stu-id="2ec42-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="2ec42-285">（从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。）</span><span class="sxs-lookup"><span data-stu-id="2ec42-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="2ec42-286">**名称**</span><span class="sxs-lookup"><span data-stu-id="2ec42-286">**Name**</span></span>|<span data-ttu-id="2ec42-287">**Type**</span><span class="sxs-lookup"><span data-stu-id="2ec42-287">**Type**</span></span>|<span data-ttu-id="2ec42-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2ec42-288">**TTL**</span></span>|<span data-ttu-id="2ec42-289">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="2ec42-289">**TTL unit**</span></span>|<span data-ttu-id="2ec42-290">**值**</span><span class="sxs-lookup"><span data-stu-id="2ec42-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="2ec42-291">TXT</span><span class="sxs-lookup"><span data-stu-id="2ec42-291">TXT</span></span>  <br/> |<span data-ttu-id="2ec42-292">1</span><span class="sxs-lookup"><span data-stu-id="2ec42-292">1</span></span>  <br/> |<span data-ttu-id="2ec42-293">工作时间</span><span class="sxs-lookup"><span data-stu-id="2ec42-293">Hours</span></span>  <br/> |<span data-ttu-id="2ec42-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2ec42-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="2ec42-295">**注意：** 建议复制粘贴此条目，以保证正确保留所有空格。</span><span class="sxs-lookup"><span data-stu-id="2ec42-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Azure-BP-配置-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="2ec42-297">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="2ec42-297">Select **Save**.</span></span>
    
    ![Azure-BP-配置-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="2ec42-299">添加 Office 365 所需的两条 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="2ec42-299">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="2ec42-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2ec42-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="2ec42-301">若要开始，请使用[此链接](https://portal.azure.com )转到 Azure 上的 "域" 页面。</span><span class="sxs-lookup"><span data-stu-id="2ec42-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="2ec42-302">系统将会提示您先登录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-302">You'll be prompted to log in first.</span></span>
    
    ![Azure-BP-配置-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="2ec42-304">在 "**仪表板**" 页上的 "**所有资源**" 区域中，选择要更新的域。</span><span class="sxs-lookup"><span data-stu-id="2ec42-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Azure-BP-配置-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="2ec42-306">在您的域的 "**设置**" 页上的 " **DNS 区域**" 区域中，选择 " **+ 记录集**"。</span><span class="sxs-lookup"><span data-stu-id="2ec42-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Azure-BP-配置-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="2ec42-308">添加两条 SRV 记录中的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="2ec42-309">在 "**添加记录集**" 区域中新记录集对应的框中，选择下表中第一行的值。</span><span class="sxs-lookup"><span data-stu-id="2ec42-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="2ec42-310">（从下拉列表中选择 "**类型**" 和 " **TTL 单位**" 值。）</span><span class="sxs-lookup"><span data-stu-id="2ec42-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="2ec42-311">**名称**</span><span class="sxs-lookup"><span data-stu-id="2ec42-311">**Name**</span></span>|<span data-ttu-id="2ec42-312">**Type**</span><span class="sxs-lookup"><span data-stu-id="2ec42-312">**Type**</span></span>|<span data-ttu-id="2ec42-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="2ec42-313">**TTL**</span></span>|<span data-ttu-id="2ec42-314">**TTL 单位**</span><span class="sxs-lookup"><span data-stu-id="2ec42-314">**TTL unit**</span></span>|<span data-ttu-id="2ec42-315">**优先级**</span><span class="sxs-lookup"><span data-stu-id="2ec42-315">**Priority**</span></span>|<span data-ttu-id="2ec42-316">**权重**</span><span class="sxs-lookup"><span data-stu-id="2ec42-316">**Weight**</span></span>|<span data-ttu-id="2ec42-317">**端口**</span><span class="sxs-lookup"><span data-stu-id="2ec42-317">**Port**</span></span>|<span data-ttu-id="2ec42-318">**目标**</span><span class="sxs-lookup"><span data-stu-id="2ec42-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="2ec42-319">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="2ec42-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="2ec42-320">SRV</span><span class="sxs-lookup"><span data-stu-id="2ec42-320">SRV</span></span>  <br/> |<span data-ttu-id="2ec42-321">1</span><span class="sxs-lookup"><span data-stu-id="2ec42-321">1</span></span>  <br/> |<span data-ttu-id="2ec42-322">工作时间</span><span class="sxs-lookup"><span data-stu-id="2ec42-322">Hours</span></span>  <br/> |<span data-ttu-id="2ec42-323">100</span><span class="sxs-lookup"><span data-stu-id="2ec42-323">100</span></span>  <br/> |<span data-ttu-id="2ec42-324">1</span><span class="sxs-lookup"><span data-stu-id="2ec42-324">1</span></span>  <br/> |<span data-ttu-id="2ec42-325">443</span><span class="sxs-lookup"><span data-stu-id="2ec42-325">443</span></span>  <br/> |<span data-ttu-id="2ec42-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2ec42-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="2ec42-327">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="2ec42-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="2ec42-328">SRV</span><span class="sxs-lookup"><span data-stu-id="2ec42-328">SRV</span></span>  <br/> |<span data-ttu-id="2ec42-329">1</span><span class="sxs-lookup"><span data-stu-id="2ec42-329">1</span></span>  <br/> |<span data-ttu-id="2ec42-330">工作时间</span><span class="sxs-lookup"><span data-stu-id="2ec42-330">Hours</span></span>  <br/> |<span data-ttu-id="2ec42-331">100</span><span class="sxs-lookup"><span data-stu-id="2ec42-331">100</span></span>  <br/> |<span data-ttu-id="2ec42-332">1</span><span class="sxs-lookup"><span data-stu-id="2ec42-332">1</span></span>  <br/> |<span data-ttu-id="2ec42-333">5061</span><span class="sxs-lookup"><span data-stu-id="2ec42-333">5061</span></span>  <br/> |<span data-ttu-id="2ec42-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="2ec42-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Azure-BP-配置-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="2ec42-336">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="2ec42-336">Select **OK**.</span></span>
    
    ![Azure-BP-配置-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="2ec42-338">添加另一条 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="2ec42-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="2ec42-339">在新记录的框中，键入或复制并粘贴表中第二行的值。</span><span class="sxs-lookup"><span data-stu-id="2ec42-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2ec42-p120">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="2ec42-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
