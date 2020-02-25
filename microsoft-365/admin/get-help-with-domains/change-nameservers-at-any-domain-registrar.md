---
title: 更改名称服务器以使用任意域名注册机构设置 Office 365
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 了解如何在 Office 365 中添加和设置域，以便您的服务（如电子邮件和 Skype for Business Online）使用您自己的域名。
ms.custom: okr_smb
ms.openlocfilehash: 3030fc33a6d528fd6cb4e97c27cdbb7c251e9a97
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251158"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a><span data-ttu-id="087be-103">更改名称服务器以使用任意域名注册机构设置 Office 365</span><span class="sxs-lookup"><span data-stu-id="087be-103">Change nameservers to set up Office 365 with any domain registrar</span></span>

 <span data-ttu-id="087be-104">如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="087be-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="087be-105">先检查 "[设置域（特定于主机的说明）](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) "，然后查看是否有关于注册器的说明。</span><span class="sxs-lookup"><span data-stu-id="087be-105">Check [Set up your domain (host-specific instructions)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) first to see if we have instructions for your registrar.</span></span> 
  
<span data-ttu-id="087be-106">请按照以下说明在 Office 365 中添加和设置你的域，以便你的服务（如电子邮件和 Skype for Business Online）将使用你自己的域名。</span><span class="sxs-lookup"><span data-stu-id="087be-106">Follow these instructions to add and set up your domain in Office 365 so your services like email and Skype for Business Online will use your own domain name.</span></span> <span data-ttu-id="087be-107">为此，你需要验证你的域，然后将你的域的名称服务器更改为 Office 365，以便为你设置正确的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="087be-107">To do this, you'll verify your domain, and then change your domain's nameservers to Office 365 so the correct DNS records can be set up for you.</span></span> <span data-ttu-id="087be-108">如果以下语句描述了您的情况，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="087be-108">Follow these steps if the following statements describe your situation:</span></span>
  
- <span data-ttu-id="087be-109">您拥有自己的域，并且想要将其设置为使用 Office 365。</span><span class="sxs-lookup"><span data-stu-id="087be-109">You have your own domain and want to set it up to work with Office 365.</span></span>
    
- <span data-ttu-id="087be-p102">希望 Office 365 代为管理 DNS 记录。（如果愿意，可[管理自己的 DNS 记录](../setup/add-domain.md)。）</span><span class="sxs-lookup"><span data-stu-id="087be-p102">You want Office 365 to manage your DNS records for you. (If you prefer, you can [manage your own DNS records](../setup/add-domain.md).)</span></span>
    
## <a name="add-a-txt-or-mx-record-for-verification"></a><span data-ttu-id="087be-112">添加 TXT 记录或 MX 记录进行验证</span><span class="sxs-lookup"><span data-stu-id="087be-112">Add a TXT or MX record for verification</span></span>
<span data-ttu-id="087be-113"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="087be-113"><a name="BKMK_verify"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="087be-p103">您必须仅创建这些记录中的其中一项。TXT 是首选记录类型，但某些 DNS 托管提供商不支持它，在这种情况下，您可以创建 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="087be-p103">You will create only one or the other of these records. TXT is the preferred record type, but some DNS hosting providers don't support it, in which case you can create an MX record instead.</span></span> 
  
<span data-ttu-id="087be-p104">在将域用于 Office 365 之前，必须确保你拥有该域。如果你能够在域注册机构处登录到你的帐户并创建 DNS 记录，便可向 Office 365 证明你是所有者。</span><span class="sxs-lookup"><span data-stu-id="087be-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="087be-p105">此记录仅用于验证您是否拥有自己的域；它不会影响其他任何内容。 如果需要，您可以以后将其删除。</span><span class="sxs-lookup"><span data-stu-id="087be-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a><span data-ttu-id="087be-120">在您的 DNS 托管提供商网站上查找可以在其中创建新记录的区域</span><span class="sxs-lookup"><span data-stu-id="087be-120">Find the area on your DNS hosting provider's website where you can create a new record</span></span>

1. <span data-ttu-id="087be-121">登录到您的 DNS 托管提供商的网站。</span><span class="sxs-lookup"><span data-stu-id="087be-121">Sign in to your DNS hosting provider's website.</span></span>
    
2. <span data-ttu-id="087be-122">选择你的域。</span><span class="sxs-lookup"><span data-stu-id="087be-122">Choose your domain.</span></span>
    
3. <span data-ttu-id="087be-123">查找您可以在其中编辑您的域的 DNS 记录的页面。</span><span class="sxs-lookup"><span data-stu-id="087be-123">Find the page where you can edit DNS records for your domain.</span></span>
    
### <a name="create-the-record"></a><span data-ttu-id="087be-124">创建记录</span><span class="sxs-lookup"><span data-stu-id="087be-124">Create the record</span></span>

<span data-ttu-id="087be-125">根据是要创建 TXT 记录还是 MX 记录，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="087be-125">Depending on whether you are creating a TXT record or an MX record, do one of the following:</span></span>
  
<span data-ttu-id="087be-126">**如果要创建 TXT 记录，请使用这些值：**</span><span class="sxs-lookup"><span data-stu-id="087be-126">**If you create a TXT record, use these values:**</span></span>
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="087be-127">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="087be-127">**Record Type**</span></span> <br/> |<span data-ttu-id="087be-128">**别名** 或 **主机名称**</span><span class="sxs-lookup"><span data-stu-id="087be-128">**Alias** or **Host Name**</span></span> <br/> |<span data-ttu-id="087be-129">**值**</span><span class="sxs-lookup"><span data-stu-id="087be-129">**Value**</span></span> <br/> |<span data-ttu-id="087be-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="087be-130">**TTL**</span></span> <br/> |
|<span data-ttu-id="087be-131">TXT</span><span class="sxs-lookup"><span data-stu-id="087be-131">TXT</span></span>  <br/> |<span data-ttu-id="087be-132">执行下列操作之一：键入 **@** ，将该字段留空或键入你的域名。</span><span class="sxs-lookup"><span data-stu-id="087be-132">Do one of the following: Type **@** or leave the field empty or type your domain name.</span></span>  <br/> <span data-ttu-id="087be-133">> [!NOTE]> 此字段对不同的 DNS 主机有不同的要求。</span><span class="sxs-lookup"><span data-stu-id="087be-133">> [!NOTE]> Different DNS hosts have different requirements for this field.</span></span>           
|<span data-ttu-id="087be-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="087be-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="087be-p106">> [!NOTE]> 这是一个示例。 在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。          [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="087be-p106">> [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="087be-138">将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。</span><span class="sxs-lookup"><span data-stu-id="087be-138">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span>  <br/> |
   
<span data-ttu-id="087be-139">**如果您创建 MX 记录，请使用这些值：**</span><span class="sxs-lookup"><span data-stu-id="087be-139">**If you create an MX record, use these values:**</span></span>
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="087be-140">**记录类型**</span><span class="sxs-lookup"><span data-stu-id="087be-140">**Record Type**</span></span>|<span data-ttu-id="087be-141">**别名** 或 **主机名称**</span><span class="sxs-lookup"><span data-stu-id="087be-141">**Alias** or **Host Name**</span></span>|<span data-ttu-id="087be-142">**值**</span><span class="sxs-lookup"><span data-stu-id="087be-142">**Value**</span></span>|<span data-ttu-id="087be-143">**优先级**</span><span class="sxs-lookup"><span data-stu-id="087be-143">**Priority**</span></span>|<span data-ttu-id="087be-144">**TTL**</span><span class="sxs-lookup"><span data-stu-id="087be-144">**TTL**</span></span>|
|<span data-ttu-id="087be-145">MX</span><span class="sxs-lookup"><span data-stu-id="087be-145">MX</span></span>|<span data-ttu-id="087be-146">键入" **@** "或你的域名。</span><span class="sxs-lookup"><span data-stu-id="087be-146">Type either **@** or your domain name.</span></span> |<span data-ttu-id="087be-p107">MS=ms *XXXXXXXX* > [!NOTE]> 这是一个示例。 在这里使用来自 Office 365 中的表的特定" **目标或指向的地址**"值。          [如何查找此内容？](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="087be-p107">MS=ms *XXXXXXXX* > [!NOTE]> This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |<span data-ttu-id="087be-150">为了**避免**与用于邮件流的 MX 记录发生冲突，请使用比任何现有 MX 记录的优先级更低的优先级。</span><span class="sxs-lookup"><span data-stu-id="087be-150">For **Priority**, to avoid conflicts with the MX record used for mail flow, use a lower priority than the priority for any existing MX records.</span></span> <span data-ttu-id="087be-151">有关优先级的详细信息，请参阅[什么是 MX 优先级？](../setup/domains-faq.md#what-is-mx-priority)</span><span class="sxs-lookup"><span data-stu-id="087be-151">For more information about priority, see [What is MX priority?](../setup/domains-faq.md#what-is-mx-priority)</span></span> |<span data-ttu-id="087be-152">将此值设置为 **1 小时** 或等效的分钟数 ( **60** )、秒数 ( **3600** )，等等。</span><span class="sxs-lookup"><span data-stu-id="087be-152">Set this value to **1 hour** or to the equivalent in minutes ( **60** ), seconds ( **3600** ), etc.</span></span> |
   
### <a name="save-the-record"></a><span data-ttu-id="087be-153">保存记录</span><span class="sxs-lookup"><span data-stu-id="087be-153">Save the record</span></span>

<span data-ttu-id="087be-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="087be-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="087be-155">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="087be-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  

1. <span data-ttu-id="087be-156">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="087be-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="087be-157">在 "**域**" 页上，选择要验证的域。</span><span class="sxs-lookup"><span data-stu-id="087be-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
  
3. <span data-ttu-id="087be-158">在 "**设置**" 页上，选择 "**启动安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="087be-158">On the **Setup** page, select **Start setup**.</span></span>
 
    
  
4. <span data-ttu-id="087be-159">在 "**验证域**" 页上，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="087be-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="087be-p109">DNS 更改通常需要 15 分钟左右才能生效。 但是，有时可能需要更长时间，您所做的更改才会在 Internet 的 DNS 系统中更新。 如果添加 DNS 记录后遇到邮件流问题或其他问题，请参阅 [更改域名或 DNS 记录后出现的问题的疑难解答](../get-help-with-domains/find-and-fix-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="087be-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="087be-163">更改域的名称服务器 (NS) 记录</span><span class="sxs-lookup"><span data-stu-id="087be-163">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="087be-164"><a name="BKMK_nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="087be-164"><a name="BKMK_nameservers"> </a></span></span>

<span data-ttu-id="087be-p110">当您进入到 Office 365 中的域设置向导的最后一步时，便只剩下一项任务未完成。要使用 Office 365 服务（如电子邮件）设置您的域，请在域注册机构中将您的域的名称服务器 (NS) 记录更改为指向 Office 365 主要名称服务器和次要名称服务器。然后，由于 Office 365 托管您的 DNS，将自动为您设置服务所需的 DNS 记录。 通过按照您的域注册机构在其网站的帮助内容中所提供步骤进行操作，您可以自己更新名称服务器记录。如果不熟悉 DNS，请联系域注册机构的支持人员。</span><span class="sxs-lookup"><span data-stu-id="087be-p110">When you get to the last step of the domains setup wizard in Office 365, you have one task remaining. To set up your domain with Office 365 services, like email, you change your domain's nameserver (or NS) records at your domain registrar to point to the Office 365 primary and secondary nameservers. Then, because Office 365 hosts your DNS, the required DNS records for your services are set up automatically for you. You can update the nameserver records yourself by following the steps your domain registrar may provide in the help content at their website. If you're not familiar with DNS, contact support at the domain registrar.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="087be-170">若要在域注册机构的网站上更改您的域的名称服务器，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="087be-170">To change your domain's nameservers at your domain registrar's website yourself, follow these steps:</span></span>
  
1. <span data-ttu-id="087be-171">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="087be-171">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="087be-172">创建两个名称服务器记录，或编辑现有名称服务器记录匹配以下值：</span><span class="sxs-lookup"><span data-stu-id="087be-172">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="087be-173">首选名称服务器</span><span class="sxs-lookup"><span data-stu-id="087be-173">First nameserver</span></span>  <br/> |<span data-ttu-id="087be-174">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="087be-174">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="087be-175">次要名称服务器</span><span class="sxs-lookup"><span data-stu-id="087be-175">Second nameserver</span></span>  <br/> |<span data-ttu-id="087be-176">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="087be-176">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="087be-177">应至少使用两个 nameserver 记录。</span><span class="sxs-lookup"><span data-stu-id="087be-177">You should use at least two nameserver records.</span></span> <span data-ttu-id="087be-178">如果列出了任何其他名称服务器，则可以将其删除，也可以将其更改为**ns3.bdm.microsoftonline.com**和**ns4.bdm.microsoftonline.com**。</span><span class="sxs-lookup"><span data-stu-id="087be-178">If there are any other nameservers listed, you can either delete them, or change them to **ns3.bdm.microsoftonline.com** and **ns4.bdm.microsoftonline.com**.</span></span> 
  
3. <span data-ttu-id="087be-179">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="087be-179">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="087be-p112">将您的域的 NS 记录更改为指向 Office 365 名称服务器时，当前与您的域相关联的所有服务都会受影响。如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。</span><span class="sxs-lookup"><span data-stu-id="087be-p112">When you change your domain's NS records to point to the Office 365 nameservers, all the services that are currently associated with your domain are affected. If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required. Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. <span data-ttu-id="087be-183">在域注册机构的网站上查找您可以在其中编辑您的域的名称服务器的区域。</span><span class="sxs-lookup"><span data-stu-id="087be-183">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="087be-184">创建两个名称服务器记录，或编辑现有名称服务器记录匹配以下值：</span><span class="sxs-lookup"><span data-stu-id="087be-184">Create two nameserver records, or edit the existing nameserver records to match the following values:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="087be-185">首选名称服务器</span><span class="sxs-lookup"><span data-stu-id="087be-185">First nameserver</span></span>  <br/> |<span data-ttu-id="087be-186">ns1.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="087be-186">ns1.dns.partner.microsoftonline.cn</span></span>  <br/> |
|<span data-ttu-id="087be-187">次要名称服务器</span><span class="sxs-lookup"><span data-stu-id="087be-187">Second nameserver</span></span>  <br/> |<span data-ttu-id="087be-188">ns2.dns.partner.microsoftonline.cn</span><span class="sxs-lookup"><span data-stu-id="087be-188">ns2.dns.partner.microsoftonline.cn</span></span>  <br/> |
   
   > [!TIP]
   > <span data-ttu-id="087be-189">应至少使用两个 nameserver 记录。</span><span class="sxs-lookup"><span data-stu-id="087be-189">You should use at least two nameserver records.</span></span> <span data-ttu-id="087be-190">如果列出了任何其他名称服务器，则可以将其删除，也可以将其更改为**ns3.dns.partner.microsoftonline.cn**和**ns4.dns.partner.microsoftonline.cn**。</span><span class="sxs-lookup"><span data-stu-id="087be-190">If there are any other nameservers listed, you can either delete them, or change them to **ns3.dns.partner.microsoftonline.cn** and **ns4.dns.partner.microsoftonline.cn**.</span></span> 
  
3. <span data-ttu-id="087be-191">保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="087be-191">Save your changes.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="087be-192">当您将您的域的 NS 记录更改为指向由世纪互联运营的 Office 365 时名称服务器，当前与您的域相关联的所有服务都将受到影响。</span><span class="sxs-lookup"><span data-stu-id="087be-192">When you change your domain's NS records to point to the Office 365 operated by 21Vianet nameservers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="087be-193">如果您跳过了向导中的任何步骤，或是将域用于博客、购物车或其他服务，则需要执行一些附加步骤。</span><span class="sxs-lookup"><span data-stu-id="087be-193">If you skipped any steps of the wizard, such as adding email addresses, or if you're using your domain for blogs, shopping carts, or other services, there are additional steps that are required.</span></span> <span data-ttu-id="087be-194">否则此更改可能会导致服务停机时间，例如导致电子邮件访问丢失或您的当前网站不可访问。</span><span class="sxs-lookup"><span data-stu-id="087be-194">Otherwise this change could result in service downtime, such as lack of email access or your current website being inaccessible.</span></span> 

::: moniker-end
  
<span data-ttu-id="087be-195">例如，以下是电子邮件和网站托管可能需要的一些附加步骤：</span><span class="sxs-lookup"><span data-stu-id="087be-195">For example, here are some additional steps that might be required for email and website hosting:</span></span>
  
- <span data-ttu-id="087be-196">将使用您的域的所有电子邮件地址移动到 Office 365，然后再更改您的 NS 记录。</span><span class="sxs-lookup"><span data-stu-id="087be-196">Move all email addresses that use your domain to Office 365 before you change your NS records.</span></span>
    
- <span data-ttu-id="087be-197">希望添加当前用于网站地址的域，如 www.fourthcoffee.com？</span><span class="sxs-lookup"><span data-stu-id="087be-197">Want to add a domain that's currently used with a website address, like www.fourthcoffee.com?</span></span> <span data-ttu-id="087be-198">你可以在以下步骤中添加域，以在网站托管的位置保持网站托管，以便用户在将域的 NS 记录更改为指向 Office 365 后仍可访问网站。</span><span class="sxs-lookup"><span data-stu-id="087be-198">You can take below steps while you add the domain to keep its website hosted where the site is hosted now so people can still get to the website after you change the domain's NS records to point to Office 365.</span></span>

1. <span data-ttu-id="087be-199">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="087be-199">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

3. <span data-ttu-id="087be-200">在" 域"页面上选择域。</span><span class="sxs-lookup"><span data-stu-id="087be-200">On the Domains page, select a domain.</span></span>

4. <span data-ttu-id="087be-201">在 " **DNS 设置**" 下，选择 "**自定义记录**"，然后选择 "**新建自定义记录**"。</span><span class="sxs-lookup"><span data-stu-id="087be-201">Under **DNS settings**, select **Custom Records**, and then choose **New custom record**.</span></span>

5. <span data-ttu-id="087be-202">选择要添加的 DNS 记录的类型，然后键入新记录的信息。</span><span class="sxs-lookup"><span data-stu-id="087be-202">Select the type of DNS record you want to add, and type the information for the new record.</span></span>

6. <span data-ttu-id="087be-203">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="087be-203">Select **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="087be-p116">你的名称服务器记录更新可能需要多达数小时才能在 Internet 的 DNS 系统中更新。然后，你的 Office 365 电子邮件和其他服务将全部设置为使用你的域。</span><span class="sxs-lookup"><span data-stu-id="087be-p116">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  

