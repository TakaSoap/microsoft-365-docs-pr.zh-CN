---
title: 更改名称服务器以设置Microsoft 365注册机构的域名
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 了解如何在 Microsoft 365 中添加和设置域，以便电子邮件和 Skype for Business Online 等服务使用你自己的域名。
ms.openlocfilehash: 9c26f9afcf17857c4b3b8f05b89253272cf20e56
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924499"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="8d724-103">更改名称服务器以设置Microsoft 365注册机构的域名</span><span class="sxs-lookup"><span data-stu-id="8d724-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="8d724-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="8d724-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8d724-105">请按照以下说明在 Microsoft 365中添加和设置你的域，以便电子邮件Teams服务将使用你自己的域名。</span><span class="sxs-lookup"><span data-stu-id="8d724-105">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="8d724-106">为此，您需要验证您的域，然后将您的域的名称服务器更改为 Microsoft 365以便您可以设置正确的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="8d724-106">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="8d724-107">如果以下语句描述了您的情况，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="8d724-107">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="8d724-108">你有你自己的域，并且想要设置它以使用Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8d724-108">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="8d724-109">您希望Microsoft 365管理 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="8d724-109">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="8d724-110"> (如果愿意，可以管理 [自己的 DNS](../setup/add-domain.md)记录 .) </span><span class="sxs-lookup"><span data-stu-id="8d724-110">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="8d724-111">添加 TXT 记录或 MX 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="8d724-111">Add a TXT or MX record for verification</span></span>

> [!NOTE]
> <span data-ttu-id="8d724-p103">您必须仅创建这些记录中的其中一项。TXT 是首选记录类型，但某些 DNS 托管提供商不支持它，在这种情况下，您可以创建 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="8d724-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="8d724-p104">在将域用于 Microsoft 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 365 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="8d724-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d724-p105">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="8d724-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="8d724-118">在 DNS 托管提供商网站上查找可在其中创建新记录的区域</span><span class="sxs-lookup"><span data-stu-id="8d724-118">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="8d724-119">登录到您的 DNS 托管提供商的网站。</span><span class="sxs-lookup"><span data-stu-id="8d724-119">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="8d724-120">选择您的域。</span><span class="sxs-lookup"><span data-stu-id="8d724-120">Choose your domain.</span></span>
    
3. <span data-ttu-id="8d724-121">查找您可以在其中编辑您的域的 DNS 记录的页面。</span><span class="sxs-lookup"><span data-stu-id="8d724-121">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="8d724-122">创建记录</span><span class="sxs-lookup"><span data-stu-id="8d724-122">Create the record</span></span>

<span data-ttu-id="8d724-123">根据是要创建 TXT 记录还是 MX 记录，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8d724-123">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="8d724-124">**如果要创建 TXT 记录，请使用这些值：**</span><span class="sxs-lookup"><span data-stu-id="8d724-124">**If you create a TXT record, use these values:**</span></span>
    

|<span data-ttu-id="8d724-125">记录类型</span><span class="sxs-lookup"><span data-stu-id="8d724-125">Record type</span></span><br/> |<span data-ttu-id="8d724-126">别名或主机名</span><span class="sxs-lookup"><span data-stu-id="8d724-126">Alias or host name</span></span> <br/> |<span data-ttu-id="8d724-127">值</span><span class="sxs-lookup"><span data-stu-id="8d724-127">Value</span></span> <br/> |<span data-ttu-id="8d724-128">TTL</span><span class="sxs-lookup"><span data-stu-id="8d724-128">TTL</span></span><br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8d724-129">TXT</span><span class="sxs-lookup"><span data-stu-id="8d724-129">TXT</span></span>  <br/> |<span data-ttu-id="8d724-130">执行下列操作之一：键入 **@** ，将该字段留空或键入你的域名。</span><span class="sxs-lookup"><span data-stu-id="8d724-130">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="8d724-131">> [!NOTE]> 此字段对不同的 DNS 主机有不同的要求。</span><span class="sxs-lookup"><span data-stu-id="8d724-131">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="8d724-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8d724-132">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="8d724-133">**注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="8d724-133">**Note:** This is an example.</span></span> <span data-ttu-id="8d724-134">在这里使用来自 Microsoft 365 中的表的具体“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="8d724-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="8d724-135">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="8d724-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8d724-136">将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。</span><span class="sxs-lookup"><span data-stu-id="8d724-136">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="8d724-137">**如果您创建 MX 记录，请使用这些值：**</span><span class="sxs-lookup"><span data-stu-id="8d724-137">**If you create an MX record, use these values:**</span></span>
    
|<span data-ttu-id="8d724-138">记录类型</span><span class="sxs-lookup"><span data-stu-id="8d724-138">Record type</span></span>|<span data-ttu-id="8d724-139">别名或主机名</span><span class="sxs-lookup"><span data-stu-id="8d724-139">Alias or host name</span></span>|<span data-ttu-id="8d724-140">值</span><span class="sxs-lookup"><span data-stu-id="8d724-140">Value</span></span>|<span data-ttu-id="8d724-141">优先级</span><span class="sxs-lookup"><span data-stu-id="8d724-141">Priority</span></span>|<span data-ttu-id="8d724-142">TTL</span><span class="sxs-lookup"><span data-stu-id="8d724-142">TTL</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8d724-143">MX</span><span class="sxs-lookup"><span data-stu-id="8d724-143">MX</span></span>|<span data-ttu-id="8d724-144">键入" **@** "或你的域名。</span><span class="sxs-lookup"><span data-stu-id="8d724-144">Type either **@** or your domain name.</span></span> |<span data-ttu-id="8d724-145">MS=ms *XXXXXXXX* **注意：** 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="8d724-145">MS=ms *XXXXXXXX* **Note:** This is an example.</span></span> <span data-ttu-id="8d724-146">在这里使用来自 Microsoft 365 中的表的具体“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="8d724-146">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="8d724-147">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="8d724-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8d724-148">对于“**优先级**”，为避免与用于邮件流的 MX 记录发生冲突，请使用比任何现有 MX 记录的优先级要低的优先级。</span><span class="sxs-lookup"><span data-stu-id="8d724-148">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="8d724-149">有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="8d724-149">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> |<span data-ttu-id="8d724-150">将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。</span><span class="sxs-lookup"><span data-stu-id="8d724-150">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="8d724-151">保存记录</span><span class="sxs-lookup"><span data-stu-id="8d724-151">Save the record</span></span>

<span data-ttu-id="8d724-152">在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="8d724-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="8d724-153">Microsoft 365 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="8d724-153">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="8d724-154">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="8d724-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="8d724-155">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="8d724-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="8d724-156">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="8d724-156">On the **Setup** page, select **Start setup**.</span></span>
 
  
4. <span data-ttu-id="8d724-157">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="8d724-157">On the **Verify domain** page, select **Verify**.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="8d724-p109">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="8d724-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="8d724-161">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="8d724-161">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="8d724-162">当您在 Microsoft 365 中到达域设置向导的最后一步时，您还有一项任务。</span><span class="sxs-lookup"><span data-stu-id="8d724-162">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="8d724-163">若要使用 Microsoft 365 服务（如电子邮件）设置域，您可以在域注册机构中更改域的名称服务器 (或 NS) 记录，以指向 Microsoft 365 主名称服务器和辅助名称服务器。</span><span class="sxs-lookup"><span data-stu-id="8d724-163">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="8d724-164">然后，由于Microsoft 365 DNS，系统会自动为服务设置所需的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="8d724-164">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="8d724-165">通过按照您的域注册机构在其网站的帮助内容中所提供步骤进行操作，您可以自己更新名称服务器记录。</span><span class="sxs-lookup"><span data-stu-id="8d724-165">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="8d724-166">如果不熟悉 DNS，请联系域注册机构的支持人员。</span><span class="sxs-lookup"><span data-stu-id="8d724-166">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="8d724-167">若要在域注册机构的网站上更改您的域的名称服务器，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8d724-167">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="8d724-168">在域注册机构网站上查找区域，您可以在其中更改域的名称服务器或使用自定义名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="8d724-168">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="8d724-169">创建名称机记录，或编辑现有名称机记录以匹配以下值：</span><span class="sxs-lookup"><span data-stu-id="8d724-169">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>

    - <span data-ttu-id="8d724-170">第一个名称 ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8d724-170">First nameserver: ns1.bdm.microsoftonline.com</span></span>
    - <span data-ttu-id="8d724-171">第二个名称 ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8d724-171">Second nameserver: ns2.bdm.microsoftonline.com</span></span>
    - <span data-ttu-id="8d724-172">第三个名称 ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8d724-172">Third nameserver: ns3.bdm.microsoftonline.com</span></span>
    - <span data-ttu-id="8d724-173">第四个名称 ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8d724-173">Fourth nameserver: ns4.bdm.microsoftonline.com</span></span>
      
   
   > [!TIP]
   > <span data-ttu-id="8d724-174">最好添加所有四条记录，但如果注册机构仅支持两条，ns1.bdm.microsoftonline.com **和\*\*\*\*ns2.bdm.microsoftonline.com。**</span><span class="sxs-lookup"><span data-stu-id="8d724-174">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="8d724-175">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8d724-175">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="8d724-176">将域的 NS 记录更改为指向Microsoft 365服务器时，当前与域关联的所有服务都受到影响。</span><span class="sxs-lookup"><span data-stu-id="8d724-176">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="8d724-177">如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。</span><span class="sxs-lookup"><span data-stu-id="8d724-177">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="8d724-178">否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。</span><span class="sxs-lookup"><span data-stu-id="8d724-178">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="8d724-179">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="8d724-179">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="8d724-180">创建两个名称服务器记录，或编辑现有名称服务器记录匹配以下值：</span><span class="sxs-lookup"><span data-stu-id="8d724-180">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>

   - <span data-ttu-id="8d724-181">第一个名称 ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="8d724-181">First nameserver: ns1.dns.partner.microsoftonline.cn</span></span>
   - <span data-ttu-id="8d724-182">第二个名称 ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="8d724-182">Second nameserver: ns2.dns.partner.microsoftonline.cn</span></span>
    
   > [!TIP]
   > <span data-ttu-id="8d724-183">应至少使用两个名称机记录。</span><span class="sxs-lookup"><span data-stu-id="8d724-183">You should use at least two nameserver records.</span></span> <span data-ttu-id="8d724-184">如果列出了任何其他名称服务器，您可以删除它们，或者将它们更改为 ns3.dns.partner.microsoftonline.cn **ns4.dns.partner.microsoftonline.cn** **。**</span><span class="sxs-lookup"><span data-stu-id="8d724-184">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="8d724-185">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8d724-185">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="8d724-186">当您将域的 NS 记录更改为指向由世纪Office 365服务器运营的域时，当前与域关联的所有服务都受到影响。</span><span class="sxs-lookup"><span data-stu-id="8d724-186">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="8d724-187">如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。</span><span class="sxs-lookup"><span data-stu-id="8d724-187">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="8d724-188">否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。</span><span class="sxs-lookup"><span data-stu-id="8d724-188">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="8d724-189">例如，以下是电子邮件和网站托管可能需要的一些附加步骤：</span><span class="sxs-lookup"><span data-stu-id="8d724-189">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="8d724-190">在更改 NS 记录之前，Microsoft 365域的所有电子邮件地址进行移动。</span><span class="sxs-lookup"><span data-stu-id="8d724-190">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="8d724-191">希望添加当前用于网站地址的域，如 www.fourthcoffee.com？</span><span class="sxs-lookup"><span data-stu-id="8d724-191">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="8d724-192">在添加域以保持其网站现在托管位置的托管位置时，您可以采取以下步骤，以便当您将域的 NS 记录更改为指向网站记录后，用户仍可访问Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8d724-192">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="8d724-193">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="8d724-193">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="8d724-194">在" **域**"页面上选择域。</span><span class="sxs-lookup"><span data-stu-id="8d724-194">On the **Domains** page, select a domain.</span></span>

3. <span data-ttu-id="8d724-195">在"域详细信息"页上，选择 **"DNS 记录"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8d724-195">On the domain details page, select the **DNS records** tab.</span></span>
 
4. <span data-ttu-id="8d724-196">选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="8d724-196">Select **Add record**.</span></span>

5. <span data-ttu-id="8d724-197">在"**添加自定义 DNS** 记录"窗格中，从"类型"下拉列表中选择" (**地址**) " 。</span><span class="sxs-lookup"><span data-stu-id="8d724-197">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **A (Address)**.</span></span>

6. <span data-ttu-id="8d724-198">在" **主机名"或"别名"** 框中，键入 **@** 。</span><span class="sxs-lookup"><span data-stu-id="8d724-198">In the **Host name or Alias** box, type **@**.</span></span>

7. <span data-ttu-id="8d724-199">在 **"IP 地址** "框中，键入当前托管该地址的网站的静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8d724-199">In the **IP Address** box, type the static IP address for the website where it's currently hosted.</span></span> <span data-ttu-id="8d724-200">例如，172.16.140.1。</span><span class="sxs-lookup"><span data-stu-id="8d724-200">For example, 172.16.140.1.</span></span>
    
> [!IMPORTANT]
>  <span data-ttu-id="8d724-201">这必须是网站的 _静态_ IP 地址，而不是 _动态_ IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8d724-201">This must be a _static_ IP address for the website, not a _dynamic_ IP address.</span></span> <span data-ttu-id="8d724-202">若要确保您可以获取公共网站的静态 IP 地址，请与承载您的网站的网站核实。</span><span class="sxs-lookup"><span data-stu-id="8d724-202">To make sure you can get a static IP address for your public website, check with the site that hosts your website.</span></span>
   
8. <span data-ttu-id="8d724-203">如果要更改记录的 TTL 设置，请从 **TTL** 下拉列表中选择一个新的时间长度。</span><span class="sxs-lookup"><span data-stu-id="8d724-203">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="8d724-204">否则，继续执行步骤 9。</span><span class="sxs-lookup"><span data-stu-id="8d724-204">Otherwise, continue to step 9.</span></span>
    
9. <span data-ttu-id="8d724-205">选择" **保存** "。</span><span class="sxs-lookup"><span data-stu-id="8d724-205">Select **Save**.</span></span> 
    
<span data-ttu-id="8d724-206">此外，您可以创建 CNAME 记录以帮助客户找到您的网站。</span><span class="sxs-lookup"><span data-stu-id="8d724-206">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1.  <span data-ttu-id="8d724-207">选择 **"添加记录"。**</span><span class="sxs-lookup"><span data-stu-id="8d724-207">Select **Add record**.</span></span>

3.  <span data-ttu-id="8d724-208">在"**添加自定义 DNS** 记录"窗格中，从"类型"下拉列表中选择 **"CNAME (别名) "。**</span><span class="sxs-lookup"><span data-stu-id="8d724-208">In the **Add a custom DNS record** pane, from the **Type** dropdown list, select **CNAME (Alias)**.</span></span>
4.  <span data-ttu-id="8d724-209">在" **主机名"或"别名"** 框中，键入 **www**。</span><span class="sxs-lookup"><span data-stu-id="8d724-209">In the **Host name or Alias** box, type **www**.</span></span>
5.  <span data-ttu-id="8d724-210">在" **指向地址"** 框中，键入网站的 (FQDN) 完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="8d724-210">In the **Points to address** box, type the fully qualified domain name (FQDN) for your website.</span></span> <span data-ttu-id="8d724-211">例如，**contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="8d724-211">For example, **contoso.com**.</span></span>
6.  <span data-ttu-id="8d724-212">如果要更改记录的 TTL 设置，请从 **TTL** 下拉列表中选择一个新的时间长度。</span><span class="sxs-lookup"><span data-stu-id="8d724-212">If you want to change the TTL setting for the record, select a new length of time from the **TTL** dropdown list.</span></span> <span data-ttu-id="8d724-213">否则，继续执行步骤 6。</span><span class="sxs-lookup"><span data-stu-id="8d724-213">Otherwise, continue to step 6.</span></span>
7.  <span data-ttu-id="8d724-214">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="8d724-214">Select **Save**.</span></span>

<span data-ttu-id="8d724-215">将名称服务器记录更新为指向 Microsoft 后，域设置即完成。</span><span class="sxs-lookup"><span data-stu-id="8d724-215">After the nameserver records are updated to point to Microsoft, your domain setup is complete.</span></span> <span data-ttu-id="8d724-216">电子邮件被路由到 Microsoft，并且发送到你的网站地址的流量将继续转到你的当前网站主机。'</span><span class="sxs-lookup"><span data-stu-id="8d724-216">Email is routed to Microsoft, and traffic to your website address continues to go to your current website host.\`</span></span>
    
> [!NOTE]
> <span data-ttu-id="8d724-217">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="8d724-217">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="8d724-218">然后，你的 Microsoft 电子邮件和其他服务都将设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="8d724-218">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="8d724-219">相关内容</span><span class="sxs-lookup"><span data-stu-id="8d724-219">Related content</span></span>

<span data-ttu-id="8d724-220">[添加 DNS 记录以连接域](create-dns-records-at-any-dns-hosting-provider.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="8d724-220">[Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="8d724-221">[查找并修复添加域或 DNS 记录之后出现的问题](find-and-fix-issues.md)（文章）</span><span class="sxs-lookup"><span data-stu-id="8d724-221">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="8d724-222">[管理域](index.yml)（链接页）</span><span class="sxs-lookup"><span data-stu-id="8d724-222">[Manage domains](index.yml) (link page)</span></span>
