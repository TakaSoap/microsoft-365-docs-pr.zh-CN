---
title: 关于域的常见问题解答
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: 通过查找您的常见问题的答案，了解有关域的详细信息。
ms.openlocfilehash: b51b5fe56bbae56dd473dd831ec91e629d9233f3
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644575"
---
# <a name="domains-faq"></a><span data-ttu-id="f5896-103">关于域的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="f5896-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f5896-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="f5896-104">The admin center is changing.</span></span> <span data-ttu-id="f5896-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="f5896-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="f5896-106">本文包含有关 Microsoft 365 中的域的常见问题的解答。</span><span class="sxs-lookup"><span data-stu-id="f5896-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="f5896-107">如果找不到你问题的答案，请留下评论告知我们，我们会将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="f5896-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="f5896-108">本文内容</span><span class="sxs-lookup"><span data-stu-id="f5896-108">In this article</span></span>

- [<span data-ttu-id="f5896-109">什么是 MX 优先级？</span><span class="sxs-lookup"><span data-stu-id="f5896-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="f5896-110">如何验证我的域的 SPF 记录？</span><span class="sxs-lookup"><span data-stu-id="f5896-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="f5896-111">什么是域名？</span><span class="sxs-lookup"><span data-stu-id="f5896-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="f5896-112">如果我的 DNS 提供商不支持某些记录类型，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="f5896-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="f5896-113">如何在 Microsoft 365 中设置或更改默认域？</span><span class="sxs-lookup"><span data-stu-id="f5896-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="f5896-114">是否可以将自定义子域或多个域添加到 Microsoft 365？</span><span class="sxs-lookup"><span data-stu-id="f5896-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="f5896-115">如何将域从 Microsoft 365 传输到另一台主机？</span><span class="sxs-lookup"><span data-stu-id="f5896-115">How do I transfer a domain from Microsoft 365 to another host?</span></span>](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [<span data-ttu-id="f5896-116">为什么我有 "onmicrosoft.com" 域？</span><span class="sxs-lookup"><span data-stu-id="f5896-116">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="f5896-117">为什么我有 "onmicrosoft.de" 域？</span><span class="sxs-lookup"><span data-stu-id="f5896-117">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="f5896-118">如何验证我的非盈利或教育状态？</span><span class="sxs-lookup"><span data-stu-id="f5896-118">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="f5896-119">什么是 MX 优先级？</span><span class="sxs-lookup"><span data-stu-id="f5896-119">What is MX priority?</span></span>

<span data-ttu-id="f5896-120">邮件传递到最低首选项编号 (最高优先级) 的邮件 exchange 服务器，因此用于邮件路由的 MX 记录应具有最低的首选数量（通常为0或  *高*  优先级）。</span><span class="sxs-lookup"><span data-stu-id="f5896-120">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="f5896-121">创建 MX 记录时，大多数 DNS 承载提供程序都要求您设置首选项号码。</span><span class="sxs-lookup"><span data-stu-id="f5896-121">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="f5896-122">部分标签 "box"  *首选项*  ，并为其添加标签  *优先级*  。</span><span class="sxs-lookup"><span data-stu-id="f5896-122">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="f5896-123">有些用户需要一个数字，有些要求您选择 "  *低*  "、"  *中*  " 或 "  *高*  "。</span><span class="sxs-lookup"><span data-stu-id="f5896-123">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="f5896-124">如果您只有一个 MX 记录，则优先级或首选项的任何值都是很好的。</span><span class="sxs-lookup"><span data-stu-id="f5896-124">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="f5896-125">如果您有多个，请确保邮件路由的 MX 记录的优先级高于用于验证您拥有该域的用户的路径。</span><span class="sxs-lookup"><span data-stu-id="f5896-125">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="f5896-126">如何验证我的域的 SPF 记录？</span><span class="sxs-lookup"><span data-stu-id="f5896-126">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="f5896-127">必须具有或  **仅为 SPF 创建一个 TXT 记录**，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="f5896-127">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="f5896-128">如果已有 SPF 记录，则应向其追加新的 Microsoft 365 值，而不是创建一个新的。</span><span class="sxs-lookup"><span data-stu-id="f5896-128">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="f5896-129">在添加或更新了 Microsoft 电子邮件的 SPF 记录后，应进行检查以确保使用以下工具之一时的语法正确：</span><span class="sxs-lookup"><span data-stu-id="f5896-129">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="f5896-130">SPF 记录测试工具</span><span class="sxs-lookup"><span data-stu-id="f5896-130">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="f5896-131">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="f5896-131">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="f5896-132">"挖出 web 界面"</span><span class="sxs-lookup"><span data-stu-id="f5896-132">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="f5896-133">什么是域名？</span><span class="sxs-lookup"><span data-stu-id="f5896-133">What is a domain name?</span></span>

<span data-ttu-id="f5896-134">域是 **@** 注册电子邮件地址后和 Web 地址中 **www.**</span><span class="sxs-lookup"><span data-stu-id="f5896-134">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="f5896-135">后显示的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="f5896-135">in web addresses.</span></span> <span data-ttu-id="f5896-136">它通常采用您组织的名称和标准 Internet 后缀的形式，如  *yourbusiness.com*  或  *stateuniversity.edu。*</span><span class="sxs-lookup"><span data-stu-id="f5896-136">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="f5896-137">将自定义域（如 "\*\* \@ contoso.com\*\*"）与 Microsoft 365 结合使用，可以帮助为你的品牌建立可信度和认可。</span><span class="sxs-lookup"><span data-stu-id="f5896-137">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="f5896-138">你可以 [在 Microsoft 365 中购买域，我们将自动对其进行设置](../get-help-with-domains/buy-a-domain-name.md)，也可以从域注册机构购买或将已有的域引入。</span><span class="sxs-lookup"><span data-stu-id="f5896-138">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="f5896-139">如果我的 DNS 提供商不支持某些记录类型，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="f5896-139">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="f5896-140">如果您管理自己的 DNS 记录，并且 DNS 主机不支持 Microsoft 365 需要的所有 DNS 记录，则某些 Microsoft 365 功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="f5896-140">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="f5896-141">我们建议您将您的域转移到支持所有必需的 DNS 记录的注册器。</span><span class="sxs-lookup"><span data-stu-id="f5896-141">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="f5896-142">支持所有必需的 DNS 记录的提供程序：</span><span class="sxs-lookup"><span data-stu-id="f5896-142">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="f5896-143">Dynadot</span><span class="sxs-lookup"><span data-stu-id="f5896-143">Dynadot</span></span>
    
- <span data-ttu-id="f5896-144">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="f5896-144">eNomCentral</span></span>
    
- <span data-ttu-id="f5896-145">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="f5896-145">Europe Registry</span></span>
    
- <span data-ttu-id="f5896-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="f5896-146">GoDaddy</span></span>
    
- <span data-ttu-id="f5896-147">悬停</span><span class="sxs-lookup"><span data-stu-id="f5896-147">Hover</span></span>
    
- <span data-ttu-id="f5896-148">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="f5896-148">MyHosting.com</span></span>
    
- <span data-ttu-id="f5896-149">Name.com</span><span class="sxs-lookup"><span data-stu-id="f5896-149">Name.com</span></span>
    
- <span data-ttu-id="f5896-150">几乎免费的语音</span><span class="sxs-lookup"><span data-stu-id="f5896-150">Nearly Free Speech</span></span>
    
- <span data-ttu-id="f5896-151">Nettica</span><span class="sxs-lookup"><span data-stu-id="f5896-151">Nettica</span></span>
    
- <span data-ttu-id="f5896-152">网络信息中心 (NIC)</span><span class="sxs-lookup"><span data-stu-id="f5896-152">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="f5896-153">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="f5896-153">Network Solutions</span></span>
    
- <span data-ttu-id="f5896-154">Register.com</span><span class="sxs-lookup"><span data-stu-id="f5896-154">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="f5896-155">如何在 Microsoft 365 中设置或更改默认域？</span><span class="sxs-lookup"><span data-stu-id="f5896-155">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="f5896-156">您必须至少有一个添加到 Microsoft 365 的自定义域，然后才能选择默认域。</span><span class="sxs-lookup"><span data-stu-id="f5896-156">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f5896-157">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f5896-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f5896-158">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f5896-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f5896-159">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="f5896-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="f5896-160">在 " **域** " 页上，选择要将其设置为新电子邮件地址的默认域的域。</span><span class="sxs-lookup"><span data-stu-id="f5896-160">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="f5896-161">选择“**设为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="f5896-161">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="f5896-162">您不能更改  *onmicrosoft.com*  域的名称。</span><span class="sxs-lookup"><span data-stu-id="f5896-162">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="f5896-163">您不能更改  *onmicrosoft.de*  域的名称。</span><span class="sxs-lookup"><span data-stu-id="f5896-163">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="f5896-164">您不能更改  *partner.onmschina.cn*  域的名称。</span><span class="sxs-lookup"><span data-stu-id="f5896-164">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="f5896-165">是否可以将自定义子域或多个域添加到 Microsoft 365？</span><span class="sxs-lookup"><span data-stu-id="f5896-165">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="f5896-166">是。</span><span class="sxs-lookup"><span data-stu-id="f5896-166">Yes.</span></span> <span data-ttu-id="f5896-167">若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。</span><span class="sxs-lookup"><span data-stu-id="f5896-167">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="f5896-168">如果要让 Microsoft 管理具有 NS 记录的 DNS 设置，或者如果您从 Microsoft 购买了域，则无法添加子域。</span><span class="sxs-lookup"><span data-stu-id="f5896-168">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="f5896-169">是的！</span><span class="sxs-lookup"><span data-stu-id="f5896-169">Yes!</span></span> <span data-ttu-id="f5896-170">若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。</span><span class="sxs-lookup"><span data-stu-id="f5896-170">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="f5896-171">如果要让 Microsoft 管理具有 NS 记录的 DNS 设置，或者如果您从 Microsoft 购买了域，则无法添加子域。</span><span class="sxs-lookup"><span data-stu-id="f5896-171">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="f5896-172">是的！</span><span class="sxs-lookup"><span data-stu-id="f5896-172">Yes!</span></span> <span data-ttu-id="f5896-173">若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。</span><span class="sxs-lookup"><span data-stu-id="f5896-173">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="f5896-174">如果您正在让世纪管理具有 NS 记录的 DNS 设置，则不能添加子域。</span><span class="sxs-lookup"><span data-stu-id="f5896-174">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="f5896-175">通常情况下，最多可以向 Microsoft 365 订阅添加900个域。</span><span class="sxs-lookup"><span data-stu-id="f5896-175">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="f5896-176">例如，可以添加域 contoso.com 和 contosomarketing.com，然后添加子域 www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com 等等。</span><span class="sxs-lookup"><span data-stu-id="f5896-176">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="f5896-177">添加子域时，将根据正在验证的父域自动对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="f5896-177">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="f5896-178">将多个域添加到 Microsoft 365 时，可以在添加的任何域中承载电子邮件)  (之类的任何服务。</span><span class="sxs-lookup"><span data-stu-id="f5896-178">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="f5896-179">*当您将电子邮件更改为 Microsoft 365 时，通过更新域的 MX 记录，发送到该域的所有电子邮件都将开始进入 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="f5896-179">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="f5896-180">如果向 Microsoft 365 订阅添加了 contoso.com 域，您还可以将子域 xyz.contoso.com 添加到另一个 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="f5896-180">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="f5896-181">添加子域时，系统会提示您在 DNS 托管提供程序中添加 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="f5896-181">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a><span data-ttu-id="f5896-182">如何将域从 Microsoft 365 传输到另一台主机？</span><span class="sxs-lookup"><span data-stu-id="f5896-182">How do I transfer a domain from Microsoft 365 to another host?</span></span>

<span data-ttu-id="f5896-183">有关转移域的过程，请参阅将 [域从 Microsoft 转移到另一台主机](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host)。</span><span class="sxs-lookup"><span data-stu-id="f5896-183">For the procedure to transfer a domain, see [Transfer a domain from Microsoft to another host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span></span>

## <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="f5896-184">从我的自定义域试点 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f5896-184">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="f5896-185">有关从自定义域到 Microsoft 365 邮箱的试点 Microsoft 365 电子邮件功能的过程，请参阅 [试点 microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain)。</span><span class="sxs-lookup"><span data-stu-id="f5896-185">For the procedure to pilot Microsoft 365 email functionality from a custom domain to a Microsoft 365 mailbox, see [Pilot Microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="f5896-186">为什么我有 "onmicrosoft.com" 域？</span><span class="sxs-lookup"><span data-stu-id="f5896-186">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="f5896-187">当您注册服务时，Microsoft 365 将为您创建一个域，如 *contoso.onmicrosoft.com*。</span><span class="sxs-lookup"><span data-stu-id="f5896-187">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="f5896-188">注册时创建的用户 ID 包括域，如 *alan@contoso.onmicrosoft.com*。</span><span class="sxs-lookup"><span data-stu-id="f5896-188">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="f5896-189">**如果您想让您的电子邮件看起来像 *alan \@ contoso.com*：** [购买域](../get-help-with-domains/buy-a-domain-name.md) ，或者只需按照 " [将用户和域添加到 Microsoft 365](add-domain.md) " 中的步骤（如果已将其拥有）。</span><span class="sxs-lookup"><span data-stu-id="f5896-189">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="f5896-190">**注册后，不能重命名 .onmicrosoft 域。**</span><span class="sxs-lookup"><span data-stu-id="f5896-190">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="f5896-191">例如，如果您选择的初始域是 "fourthcoffee.onmicrosoft.com"，则不能将其更改为 "fabrikam.onmicrosoft.com"。</span><span class="sxs-lookup"><span data-stu-id="f5896-191">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="f5896-192">若要使用不同的 onmicrosoft.com 域，您必须启动一个使用 Microsoft 365 的新订阅。</span><span class="sxs-lookup"><span data-stu-id="f5896-192">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="f5896-193">**您不能重命名团队网站 URL。**</span><span class="sxs-lookup"><span data-stu-id="f5896-193">**You can't rename your team site URL.**</span></span> <span data-ttu-id="f5896-194">您的团队网站 URL 基于您的 onmicrosoft.com 域名。</span><span class="sxs-lookup"><span data-stu-id="f5896-194">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="f5896-195">遗憾的是，由于 SharePoint Online 体系结构的工作方式，无法重命名团队网站。</span><span class="sxs-lookup"><span data-stu-id="f5896-195">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="f5896-196">**您不能删除您的 .onmicrosoft 域。**</span><span class="sxs-lookup"><span data-stu-id="f5896-196">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="f5896-197">Microsoft 365 需要将其保留，因为它在你的订阅的幕后使用。</span><span class="sxs-lookup"><span data-stu-id="f5896-197">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="f5896-198">但在添加自定义域之后，您无需自己使用域。</span><span class="sxs-lookup"><span data-stu-id="f5896-198">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="f5896-199">即使在添加了域之后，也可以继续使用初始 onmicrosoft.com 域。</span><span class="sxs-lookup"><span data-stu-id="f5896-199">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="f5896-200">它仍适用于电子邮件和其他服务，因此是你的选择。</span><span class="sxs-lookup"><span data-stu-id="f5896-200">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="f5896-201">为什么我有 "onmicrosoft.de" 域？</span><span class="sxs-lookup"><span data-stu-id="f5896-201">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="f5896-202">当您注册服务时，Microsoft 365 将为您创建一个域，如 *contoso.onmicrosoft.de*。</span><span class="sxs-lookup"><span data-stu-id="f5896-202">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="f5896-203">注册时创建的用户 ID 包括域，如 *alan@contoso.onmicrosoft.de*。</span><span class="sxs-lookup"><span data-stu-id="f5896-203">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="f5896-204">**如果您想让您的电子邮件看起来像 *alan@contoso.de*：** [购买域](../get-help-with-domains/buy-a-domain-name.md) ，或者只需按照 " [将用户和域添加到 Microsoft 365](add-domain.md) 中的步骤" 中的步骤。如果你已拥有它。</span><span class="sxs-lookup"><span data-stu-id="f5896-204">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="f5896-205">**注册后，不能重命名 .onmicrosoft 域。**</span><span class="sxs-lookup"><span data-stu-id="f5896-205">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="f5896-206">例如，如果您选择的初始域是 "fourthcoffee.onmicrosoft.de"，则不能将其更改为 "fabrikam.onmicrosoft.de"。</span><span class="sxs-lookup"><span data-stu-id="f5896-206">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="f5896-207">若要使用不同的 onmicrosoft.de 域，您必须启动一个使用 Microsoft 365 的新订阅。</span><span class="sxs-lookup"><span data-stu-id="f5896-207">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="f5896-208">**您不能重命名团队网站 URL。**</span><span class="sxs-lookup"><span data-stu-id="f5896-208">**You can't rename your team site URL.**</span></span> <span data-ttu-id="f5896-209">您的团队网站 URL 基于您的 onmicrosoft.de 域名。遗憾的是，由于 SharePoint Online 体系结构的工作方式，无法重命名团队网站。</span><span class="sxs-lookup"><span data-stu-id="f5896-209">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="f5896-210">**您不能删除您的 .onmicrosoft 域。**</span><span class="sxs-lookup"><span data-stu-id="f5896-210">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="f5896-211">Microsoft 365 需要将其保留，因为它在你的订阅的幕后使用。</span><span class="sxs-lookup"><span data-stu-id="f5896-211">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="f5896-212">但在添加自定义域之后，您无需自己使用域。</span><span class="sxs-lookup"><span data-stu-id="f5896-212">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="f5896-213">即使在添加了域之后，也可以继续使用初始 onmicrosoft.de 域。</span><span class="sxs-lookup"><span data-stu-id="f5896-213">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="f5896-214">它仍适用于电子邮件和其他服务，因此是你的选择。</span><span class="sxs-lookup"><span data-stu-id="f5896-214">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="f5896-215">如何验证我的非盈利或教育状态？</span><span class="sxs-lookup"><span data-stu-id="f5896-215">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="f5896-216">在[管理中心](https://docs.microsoft.com/microsoft-365/admin/admin-home)中选择 "**设置**" 以启动向导。</span><span class="sxs-lookup"><span data-stu-id="f5896-216">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="f5896-217"> (务必先登录到 Microsoft 365。 ) </span><span class="sxs-lookup"><span data-stu-id="f5896-217">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="f5896-218">若要成为你的学校的管理员，请选择 "在 Microsoft 365 中  **成为管理员** " 选项。</span><span class="sxs-lookup"><span data-stu-id="f5896-218">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="f5896-219">系统将提示你在你的域的 DNS 主机网站上添加 TXT DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="f5896-219">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="f5896-220">为什么？</span><span class="sxs-lookup"><span data-stu-id="f5896-220">Why?</span></span> <span data-ttu-id="f5896-221">由于通过在 DNS 主机上登录并为你的域添加记录，你可以向 Microsoft 365 证明你拥有此域名。</span><span class="sxs-lookup"><span data-stu-id="f5896-221">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="f5896-222">添加记录后，您将返回到 Microsoft 365 门户，并确认您已添加它，以便 Microsoft 365 可以进行检查。</span><span class="sxs-lookup"><span data-stu-id="f5896-222">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="f5896-223">是否有非盈利的，想要获取 Microsoft 365？</span><span class="sxs-lookup"><span data-stu-id="f5896-223">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="f5896-224">[请确保您的组织符合](https://www.microsoft.com/en-us/nonprofits/eligibility) 条件，然后注册服务。</span><span class="sxs-lookup"><span data-stu-id="f5896-224">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="f5896-225">想要了解有关成为你的学校的管理员的详细信息吗？</span><span class="sxs-lookup"><span data-stu-id="f5896-225">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="f5896-226">[了解相关信息](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。</span><span class="sxs-lookup"><span data-stu-id="f5896-226">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>