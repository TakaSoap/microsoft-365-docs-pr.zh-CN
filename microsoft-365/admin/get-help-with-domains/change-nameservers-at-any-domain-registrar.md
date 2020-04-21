---
title: 更改名称服务器以使用任何域注册机构设置 Microsoft 365
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 了解如何在 Microsoft 365 中添加和设置域，以便您的服务（如电子邮件和 Skype for Business Online）使用您自己的域名。
ms.custom: okr_smb
ms.openlocfilehash: e987d1194d3ee86548a6628310ebdfd14cdbb9ea
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628502"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a><span data-ttu-id="96cce-103">更改名称服务器以使用任何域注册机构设置 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="96cce-103">Change nameservers to set up Microsoft 365 with any domain registrar</span></span>

 <span data-ttu-id="96cce-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="96cce-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="96cce-105">先检查 "[设置域（特定于主机的说明）](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) "，然后查看是否有关于注册器的说明。</span><span class="sxs-lookup"><span data-stu-id="96cce-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="96cce-106">请按照以下说明在 Microsoft 365 中添加和设置你的域，以便你的服务（如电子邮件和 Skype for Business Online）将使用你自己的域名。</span><span class="sxs-lookup"><span data-stu-id="96cce-106">Follow these instructions to add and set up your domain in Microsoft 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="96cce-107">为此，您将验证您的域，然后将您的域的名称服务器更改为 Microsoft 365，以便可以为您设置正确的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="96cce-107">To do this, you'll verify your domain, and then change your domain's nameservers to Microsoft 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="96cce-108">如果以下语句描述了您的情况，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="96cce-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="96cce-109">你拥有自己的域，并希望将其设置为使用 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="96cce-109">You have your own domain and want to set it up to work with Microsoft 365.</span></span>
    
- <span data-ttu-id="96cce-110">你希望 Microsoft 365 为你管理 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="96cce-110">You want Microsoft 365 to manage your DNS records for you.</span></span> <span data-ttu-id="96cce-111">（如果愿意，您可以[管理自己的 DNS 记录](../setup/add-domain.md)。）</span><span class="sxs-lookup"><span data-stu-id="96cce-111">(If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="96cce-112">添加 TXT 记录或 MX 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="96cce-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="96cce-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="96cce-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="96cce-p103">您必须仅创建这些记录中的其中一项。TXT 是首选记录类型，但某些 DNS 托管提供商不支持它，在这种情况下，您可以创建 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="96cce-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="96cce-116">在将你的域用于 Microsoft 365 之前，我们必须确保你拥有它。</span><span class="sxs-lookup"><span data-stu-id="96cce-116">Before you use your domain with Microsoft 365, we have to make sure that you own it.</span></span> <span data-ttu-id="96cce-117">你能够在域注册机构登录到你的帐户，并创建向 Microsoft 365 证明你拥有该域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="96cce-117">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96cce-p105">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="96cce-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="96cce-120">在您的 DNS 托管提供商网站上查找可以在其中创建新记录的区域</span><span class="sxs-lookup"><span data-stu-id="96cce-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="96cce-121">登录到您的 DNS 托管提供商的网站。</span><span class="sxs-lookup"><span data-stu-id="96cce-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="96cce-122">选择您的域。</span><span class="sxs-lookup"><span data-stu-id="96cce-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="96cce-123">查找您可以在其中编辑您的域的 DNS 记录的页面。</span><span class="sxs-lookup"><span data-stu-id="96cce-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="96cce-124">创建记录</span><span class="sxs-lookup"><span data-stu-id="96cce-124">Create the record</span></span>

<span data-ttu-id="96cce-125">根据是要创建 TXT 记录还是 MX 记录，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="96cce-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="96cce-126">**如果要创建 TXT 记录，请使用这些值：**</span><span class="sxs-lookup"><span data-stu-id="96cce-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="96cce-127">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="96cce-127">**Record Type**</span></span> <br/> |<span data-ttu-id="96cce-128">**别名**或**主机名称**</span><span class="sxs-lookup"><span data-stu-id="96cce-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="96cce-129">**值**</span><span class="sxs-lookup"><span data-stu-id="96cce-129">**Value**</span></span> <br/> |<span data-ttu-id="96cce-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="96cce-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="96cce-131">TXT</span><span class="sxs-lookup"><span data-stu-id="96cce-131">TXT</span></span>  <br/> |<span data-ttu-id="96cce-132">执行下列操作之一：键入 **@** ，将该字段留空或键入你的域名。</span><span class="sxs-lookup"><span data-stu-id="96cce-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="96cce-133">> [!NOTE]> 此字段对不同的 DNS 主机有不同的要求。</span><span class="sxs-lookup"><span data-stu-id="96cce-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="96cce-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="96cce-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="96cce-135">> [!NOTE]> 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="96cce-135">> [!NOTE]> This is an example.</span></span> <span data-ttu-id="96cce-136">从 Microsoft 365 中的表，使用您的特定**目标或指向**此处的地址值。</span><span class="sxs-lookup"><span data-stu-id="96cce-136">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="96cce-137">如何查找此内容？</span><span class="sxs-lookup"><span data-stu-id="96cce-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="96cce-138">将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。</span><span class="sxs-lookup"><span data-stu-id="96cce-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="96cce-139">**如果您创建 MX 记录，请使用这些值：**</span><span class="sxs-lookup"><span data-stu-id="96cce-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="96cce-140">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="96cce-140">**Record Type**</span></span>|<span data-ttu-id="96cce-141">**别名**或**主机名称**</span><span class="sxs-lookup"><span data-stu-id="96cce-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="96cce-142">**值**</span><span class="sxs-lookup"><span data-stu-id="96cce-142">**Value**</span></span>|<span data-ttu-id="96cce-143">**优先级**</span><span class="sxs-lookup"><span data-stu-id="96cce-143">**Priority**</span></span>|<span data-ttu-id="96cce-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="96cce-144">**TTL**</span></span>|
|<span data-ttu-id="96cce-145">MX</span><span class="sxs-lookup"><span data-stu-id="96cce-145">MX</span></span>|<span data-ttu-id="96cce-146">键入" **@** "或你的域名。</span><span class="sxs-lookup"><span data-stu-id="96cce-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="96cce-147">MS=ms *XXXXXXXX* > [!NOTE]> 这是一个示例。</span><span class="sxs-lookup"><span data-stu-id="96cce-147">MS=ms *XXXXXXXX* > [!NOTE]> This is an example.</span></span> <span data-ttu-id="96cce-148">从 Microsoft 365 中的表，使用您的特定**目标或指向**此处的地址值。</span><span class="sxs-lookup"><span data-stu-id="96cce-148">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="96cce-149">如何查找此项？</span><span class="sxs-lookup"><span data-stu-id="96cce-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="96cce-150">对于“**优先级**”，为避免与用于邮件流的 MX 记录发生冲突，请使用比任何现有 MX 记录的优先级要低的优先级。</span><span class="sxs-lookup"><span data-stu-id="96cce-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="96cce-151">有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.md#what-is-mx-priority)</span><span class="sxs-lookup"><span data-stu-id="96cce-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="96cce-152">将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。</span><span class="sxs-lookup"><span data-stu-id="96cce-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="96cce-153">保存记录</span><span class="sxs-lookup"><span data-stu-id="96cce-153">Save the record</span></span>

<span data-ttu-id="96cce-154">现在您已在域注册机构的网站上添加了记录，您将返回到 Microsoft 365 并请求 Microsoft 365 查找该记录。</span><span class="sxs-lookup"><span data-stu-id="96cce-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="96cce-155">当 Microsoft 365 找到正确的 TXT 记录时，您的域将会得到验证。</span><span class="sxs-lookup"><span data-stu-id="96cce-155">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="96cce-156">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="96cce-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="96cce-157">在“**域**”页面上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="96cce-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="96cce-158">在“**设置**”页面上，选择“**开始设置**”。</span><span class="sxs-lookup"><span data-stu-id="96cce-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="96cce-159">在“**验证域**”页面上，选择“**验证**”。</span><span class="sxs-lookup"><span data-stu-id="96cce-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="96cce-p109">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="96cce-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="96cce-163">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="96cce-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="96cce-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="96cce-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="96cce-165">当您转到 Microsoft 365 中的域设置向导的最后一步时，您有一个剩余的任务。</span><span class="sxs-lookup"><span data-stu-id="96cce-165">When you get to the last step of the domains setup wizard in Microsoft 365, you have one task remaining.</span></span> <span data-ttu-id="96cce-166">若要使用 Microsoft 365 服务（如电子邮件）设置域，您可以在您的域注册机构中更改域的名称服务器名称（或 NS）记录，以指向 Microsoft 365 主要和辅助名称服务器。</span><span class="sxs-lookup"><span data-stu-id="96cce-166">To set up your domain with Microsoft 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Microsoft 365 primary and secondary nameservers.</span></span> <span data-ttu-id="96cce-167">然后，由于 Microsoft 365 托管你的 DNS，将自动为你设置服务所需的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="96cce-167">Then, because Microsoft 365 hosts your DNS, the required DNS records for your services are set up automatically for you.</span></span> <span data-ttu-id="96cce-168">通过按照您的域注册机构在其网站的帮助内容中所提供步骤进行操作，您可以自己更新名称服务器记录。</span><span class="sxs-lookup"><span data-stu-id="96cce-168">You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website.</span></span> <span data-ttu-id="96cce-169">如果不熟悉 DNS，请联系域注册机构的支持人员。</span><span class="sxs-lookup"><span data-stu-id="96cce-169">If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="96cce-170">若要在域注册机构的网站上更改您的域的名称服务器，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="96cce-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="96cce-171">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="96cce-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="96cce-172">创建两个名称服务器记录，或编辑现有名称服务器记录匹配以下值：</span><span class="sxs-lookup"><span data-stu-id="96cce-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="96cce-173">首选名称服务器</span><span class="sxs-lookup"><span data-stu-id="96cce-173">First nameserver</span></span>  <br/> |<span data-ttu-id="96cce-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="96cce-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="96cce-175">次要名称服务器</span><span class="sxs-lookup"><span data-stu-id="96cce-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="96cce-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="96cce-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="96cce-177">应至少使用两个 nameserver 记录。</span><span class="sxs-lookup"><span data-stu-id="96cce-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="96cce-178">如果列出了任何其他名称服务器，则可以将其删除，也可以将其更改为**ns3.bdm.microsoftonline.com**和**ns4.bdm.microsoftonline.com**。</span><span class="sxs-lookup"><span data-stu-id="96cce-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="96cce-179">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="96cce-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="96cce-180">当您将您的域的 NS 记录更改为指向 Microsoft 365 名称服务器时，当前与您的域相关联的所有服务都将受到影响。</span><span class="sxs-lookup"><span data-stu-id="96cce-180">When you change your domain's NS records to point to the Microsoft 365 nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="96cce-181">如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。</span><span class="sxs-lookup"><span data-stu-id="96cce-181">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="96cce-182">否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。</span><span class="sxs-lookup"><span data-stu-id="96cce-182">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="96cce-183">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="96cce-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="96cce-184">创建两个名称服务器记录，或编辑现有名称服务器记录匹配以下值：</span><span class="sxs-lookup"><span data-stu-id="96cce-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="96cce-185">首选名称服务器</span><span class="sxs-lookup"><span data-stu-id="96cce-185">First nameserver</span></span>  <br/> |<span data-ttu-id="96cce-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="96cce-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="96cce-187">次要名称服务器</span><span class="sxs-lookup"><span data-stu-id="96cce-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="96cce-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="96cce-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="96cce-189">应至少使用两个 nameserver 记录。</span><span class="sxs-lookup"><span data-stu-id="96cce-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="96cce-190">如果列出了任何其他名称服务器，则可以将其删除，也可以将其更改为**ns3.dns.partner.microsoftonline.cn**和**ns4.dns.partner.microsoftonline.cn**。</span><span class="sxs-lookup"><span data-stu-id="96cce-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="96cce-191">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="96cce-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="96cce-192">当您将您的域的 NS 记录更改为指向由世纪互联运营的 Office 365 时名称服务器，当前与您的域相关联的所有服务都将受到影响。</span><span class="sxs-lookup"><span data-stu-id="96cce-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="96cce-193">如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。</span><span class="sxs-lookup"><span data-stu-id="96cce-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="96cce-194">否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。</span><span class="sxs-lookup"><span data-stu-id="96cce-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="96cce-195">例如，以下是电子邮件和网站托管可能需要的一些附加步骤：</span><span class="sxs-lookup"><span data-stu-id="96cce-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="96cce-196">在更改 NS 记录之前，请先将使用您的域的所有电子邮件地址移至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="96cce-196">Move all email addresses that use your domain to Microsoft 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="96cce-197">希望添加当前用于网站地址的域，如 www.fourthcoffee.com？</span><span class="sxs-lookup"><span data-stu-id="96cce-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="96cce-198">你可以在以下步骤中添加域，以在网站托管的位置保持网站托管，以便在你将域的 NS 记录更改为指向 Microsoft 365 后，用户仍可访问网站。</span><span class="sxs-lookup"><span data-stu-id="96cce-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Microsoft 365.</span></span>

1. <span data-ttu-id="96cce-199">在管理中心，转到“**设置**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>页面。</span><span class="sxs-lookup"><span data-stu-id="96cce-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="96cce-200">在" 域"页面上选择域。</span><span class="sxs-lookup"><span data-stu-id="96cce-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="96cce-201">在 " **DNS 设置**" 下，选择 "**自定义记录**"，然后选择 "**新建自定义记录**"。</span><span class="sxs-lookup"><span data-stu-id="96cce-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="96cce-202">选择要添加的 DNS 记录的类型，然后键入新记录的信息。</span><span class="sxs-lookup"><span data-stu-id="96cce-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="96cce-203">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="96cce-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="96cce-204">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="96cce-204">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="96cce-205">然后，你的 Microsoft 电子邮件和其他服务将全部设置为与你的域一起使用。</span><span class="sxs-lookup"><span data-stu-id="96cce-205">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  

