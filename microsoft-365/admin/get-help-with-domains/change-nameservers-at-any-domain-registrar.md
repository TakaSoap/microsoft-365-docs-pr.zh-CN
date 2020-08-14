---
title: 更改名称服务器以使用任何域注册机构设置 Microsoft 365
f1.keywords:
- CSH
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
description: 了解如何在 Microsoft 365 中添加和设置域，以便您的服务（如电子邮件和 Skype for Business Online）使用您自己的域名。
ms.openlocfilehash: 6a99ee90db3bb71038309175b32bd4d96097aa5a
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662228"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="59588-103">更改名称服务器以使用任何域注册机构设置 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59588-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="59588-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="59588-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="59588-105">检查 [设置您的域 (特定主机的说明) ](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) 先查看是否有注册注册程序的说明。</span><span class="sxs-lookup"><span data-stu-id="59588-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="59588-106">请按照以下说明在 Microsoft 365 中添加和设置你的域，以便你的服务（如电子邮件和团队）将使用你自己的域名。</span><span class="sxs-lookup"><span data-stu-id="59588-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Teams will use your own domain name.</span></span> <span data-ttu-id="59588-107">为此，您将验证您的域，然后将您的域的名称服务器更改为 Microsoft 365，以便可以为您设置正确的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="59588-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="59588-108">如果以下语句描述了您的情况，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="59588-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="59588-109">你拥有自己的域，并希望将其设置为使用 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="59588-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="59588-110">你希望 Microsoft 365 为你管理 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="59588-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="59588-111"> (如果您愿意，您可以 [管理自己的 DNS 记录](../setup/add-domain.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="59588-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="59588-112">添加 TXT 记录或 MX 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="59588-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="59588-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="59588-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="59588-p103">您必须仅创建这些记录中的其中一项。TXT 是首选记录类型，但某些 DNS 托管提供商不支持它，在这种情况下，您可以创建 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="59588-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="59588-p104">在将域用于 Microsoft 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Microsoft 365 证明你是域所有者。</span><span class="sxs-lookup"><span data-stu-id="59588-p104">Before you use your domain with Microsoft 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="59588-p105">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="59588-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="59588-120">在您的 DNS 托管提供商网站上查找可以在其中创建新记录的区域</span><span class="sxs-lookup"><span data-stu-id="59588-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="59588-121">登录到您的 DNS 托管提供商的网站。</span><span class="sxs-lookup"><span data-stu-id="59588-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="59588-122">选择您的域。</span><span class="sxs-lookup"><span data-stu-id="59588-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="59588-123">查找您可以在其中编辑您的域的 DNS 记录的页面。</span><span class="sxs-lookup"><span data-stu-id="59588-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="59588-124">创建记录</span><span class="sxs-lookup"><span data-stu-id="59588-124">Create the record</span></span>

<span data-ttu-id="59588-125">根据是要创建 TXT 记录还是 MX 记录，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="59588-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="59588-126">**如果要创建 TXT 记录，请使用这些值：**</span><span class="sxs-lookup"><span data-stu-id="59588-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="59588-127">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="59588-127">**Record Type**</span></span> <br/> |<span data-ttu-id="59588-128">**别名**或**主机名称**</span><span class="sxs-lookup"><span data-stu-id="59588-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="59588-129">**值**</span><span class="sxs-lookup"><span data-stu-id="59588-129">**Value**</span></span> <br/> |<span data-ttu-id="59588-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="59588-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="59588-131">TXT</span><span class="sxs-lookup"><span data-stu-id="59588-131">TXT</span></span>  <br/> |<span data-ttu-id="59588-132">执行下列操作之一：键入 **@** ，将该字段留空或键入你的域名。</span><span class="sxs-lookup"><span data-stu-id="59588-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="59588-133">> [!NOTE]> 此字段对不同的 DNS 主机有不同的要求。</span><span class="sxs-lookup"><span data-stu-id="59588-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="59588-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="59588-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="59588-135">> [!NOTE]> 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="59588-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="59588-136">在这里使用来自 Microsoft 365 中的表的具体“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="59588-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="59588-137">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="59588-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="59588-138">将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。</span><span class="sxs-lookup"><span data-stu-id="59588-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="59588-139">**如果您创建 MX 记录，请使用这些值：**</span><span class="sxs-lookup"><span data-stu-id="59588-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="59588-140">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="59588-140">**Record Type**</span></span>|<span data-ttu-id="59588-141">**别名**或**主机名称**</span><span class="sxs-lookup"><span data-stu-id="59588-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="59588-142">**值**</span><span class="sxs-lookup"><span data-stu-id="59588-142">**Value**</span></span>|<span data-ttu-id="59588-143">**优先级**</span><span class="sxs-lookup"><span data-stu-id="59588-143">**Priority**</span></span>|<span data-ttu-id="59588-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="59588-144">**TTL**</span></span>|
|<span data-ttu-id="59588-145">MX</span><span class="sxs-lookup"><span data-stu-id="59588-145">MX</span></span>|<span data-ttu-id="59588-146">键入" **@** "或你的域名。</span><span class="sxs-lookup"><span data-stu-id="59588-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="59588-147">MS=ms *XXXXXXXX* > [!NOTE]> 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="59588-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="59588-148">在这里使用来自 Microsoft 365 中的表的具体“**目标地址或指向的地址**”值。</span><span class="sxs-lookup"><span data-stu-id="59588-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="59588-149">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="59588-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="59588-150">对于“**优先级**”，为避免与用于邮件流的 MX 记录发生冲突，请使用比任何现有 MX 记录的优先级要低的优先级。</span><span class="sxs-lookup"><span data-stu-id="59588-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="59588-151">有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.md#what-is-mx-priority)</span><span class="sxs-lookup"><span data-stu-id="59588-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="59588-152">将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。</span><span class="sxs-lookup"><span data-stu-id="59588-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="59588-153">保存记录</span><span class="sxs-lookup"><span data-stu-id="59588-153">Save the record</span></span>

<span data-ttu-id="59588-154">在域注册机构网站添加了记录后，你将返回到 Microsoft 365 并请求 Microsoft 365 查找记录。</span><span class="sxs-lookup"><span data-stu-id="59588-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="59588-155">Microsoft 365 找到正确的 TXT 记录表明域已通过验证。</span><span class="sxs-lookup"><span data-stu-id="59588-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="59588-156">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="59588-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="59588-157">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="59588-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="59588-158">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="59588-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="59588-159">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="59588-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="59588-p109">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="59588-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="59588-163">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="59588-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="59588-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="59588-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="59588-165">当您转到 Microsoft 365 中的域设置向导的最后一步时，您有一个剩余的任务。</span><span class="sxs-lookup"><span data-stu-id="59588-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="59588-166">若要使用 Microsoft 365 服务（如电子邮件）设置域，您可以更改域的 nameserver (或域注册机构中的 NS) 记录，以指向 Microsoft 365 主要和辅助名称服务器。</span><span class="sxs-lookup"><span data-stu-id="59588-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="59588-167">然后，由于 Microsoft 365 托管你的 DNS，将自动为你设置服务所需的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="59588-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="59588-168">通过按照您的域注册机构在其网站的帮助内容中所提供步骤进行操作，您可以自己更新名称服务器记录。</span><span class="sxs-lookup"><span data-stu-id="59588-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="59588-169">如果不熟悉 DNS，请联系域注册机构的支持人员。</span><span class="sxs-lookup"><span data-stu-id="59588-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="59588-170">若要在域注册机构的网站上更改您的域的名称服务器，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="59588-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="59588-171">在域注册机构网站上查找可以在其中更改您的域的名称服务器的区域或可使用自定义名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="59588-171">Find the area on the domain registrar's website where you can change the nameservers for your domain or an area where you can use custom nameservers.</span></span>
    
2. <span data-ttu-id="59588-172">创建 nameserver 记录，或编辑现有的名称服务器记录以匹配以下值：</span><span class="sxs-lookup"><span data-stu-id="59588-172">Create nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="59588-173">首选名称服务器</span><span class="sxs-lookup"><span data-stu-id="59588-173">First nameserver</span></span>  <br/> |<span data-ttu-id="59588-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="59588-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="59588-175">次要名称服务器</span><span class="sxs-lookup"><span data-stu-id="59588-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="59588-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="59588-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="59588-177">第三个名称服务器</span><span class="sxs-lookup"><span data-stu-id="59588-177">Third nameserver</span></span>  <br/> |<span data-ttu-id="59588-178">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="59588-178">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="59588-179">第四个名称服务器</span><span class="sxs-lookup"><span data-stu-id="59588-179">Fourth nameserver</span></span>  <br/> |<span data-ttu-id="59588-180">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="59588-180">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="59588-181">最好添加所有四条记录，但如果您的注册机构仅支持两个，请添加 **ns1.bdm.microsoftonline.com** 和 **ns2.bdm.microsoftonline.com**。</span><span class="sxs-lookup"><span data-stu-id="59588-181">It's best to add all four records, but if your registrar only supports two, add **ns1.bdm.microsoftonline.com** and **ns2.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="59588-182">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="59588-182">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="59588-183">当您将您的域的 NS 记录更改为指向 Microsoft 365 名称服务器时，当前与您的域相关联的所有服务都将受到影响。</span><span class="sxs-lookup"><span data-stu-id="59588-183">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="59588-184">如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。</span><span class="sxs-lookup"><span data-stu-id="59588-184">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="59588-185">否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。</span><span class="sxs-lookup"><span data-stu-id="59588-185">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="59588-186">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="59588-186">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="59588-187">创建两个名称服务器记录，或编辑现有名称服务器记录匹配以下值：</span><span class="sxs-lookup"><span data-stu-id="59588-187">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="59588-188">首选名称服务器</span><span class="sxs-lookup"><span data-stu-id="59588-188">First nameserver</span></span>  <br/> |<span data-ttu-id="59588-189">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="59588-189">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="59588-190">次要名称服务器</span><span class="sxs-lookup"><span data-stu-id="59588-190">Second nameserver</span></span>  <br/> |<span data-ttu-id="59588-191">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="59588-191">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="59588-192">应至少使用两个 nameserver 记录。</span><span class="sxs-lookup"><span data-stu-id="59588-192">You should use at least two nameserver records.</span></span> <span data-ttu-id="59588-193">如果列出了任何其他名称服务器，则可以将其删除，也可以将其更改为 **ns3.dns.partner.microsoftonline.cn** 和 **ns4.dns.partner.microsoftonline.cn**。</span><span class="sxs-lookup"><span data-stu-id="59588-193">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="59588-194">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="59588-194">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="59588-195">当您将您的域的 NS 记录更改为指向由世纪互联运营的 Office 365 时名称服务器，当前与您的域相关联的所有服务都将受到影响。</span><span class="sxs-lookup"><span data-stu-id="59588-195">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="59588-196">如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。</span><span class="sxs-lookup"><span data-stu-id="59588-196">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="59588-197">否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。</span><span class="sxs-lookup"><span data-stu-id="59588-197">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="59588-198">例如，以下是电子邮件和网站托管可能需要的一些附加步骤：</span><span class="sxs-lookup"><span data-stu-id="59588-198">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="59588-199">在更改 NS 记录之前，请先将使用您的域的所有电子邮件地址移至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="59588-199">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="59588-200">希望添加当前用于网站地址的域，如 www.fourthcoffee.com？</span><span class="sxs-lookup"><span data-stu-id="59588-200">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="59588-201">你可以在以下步骤中添加域，以在网站托管的位置保持网站托管，以便在你将域的 NS 记录更改为指向 Microsoft 365 后，用户仍可访问网站。</span><span class="sxs-lookup"><span data-stu-id="59588-201">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="59588-202">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="59588-202">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="59588-203">在 " **域** " 页上，选择域，然后选择 " **DNS 记录**"。</span><span class="sxs-lookup"><span data-stu-id="59588-203">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="59588-204">在 " **DNS 设置**" 下，选择 " **自定义记录**"，然后选择 " **新建自定义记录**"。</span><span class="sxs-lookup"><span data-stu-id="59588-204">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

4. <span data-ttu-id="59588-205">选择要添加的 DNS 记录的类型，然后键入新记录的信息。</span><span class="sxs-lookup"><span data-stu-id="59588-205">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

5. <span data-ttu-id="59588-206">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="59588-206">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="59588-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="59588-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="59588-208">然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。</span><span class="sxs-lookup"><span data-stu-id="59588-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
