---
title: 关于域的常见问题解答
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
description: 通过在 FAQ 中查找问题的答案，了解有关域的详细信息。
ms.openlocfilehash: c82d5d01d64ad01f68d0c1ba73860511aa1718aa
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44398902"
---
# <a name="domains-faq"></a><span data-ttu-id="cec71-103">关于域的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="cec71-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="cec71-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="cec71-104">The admin center is changing.</span></span> <span data-ttu-id="cec71-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="cec71-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="cec71-106">本文包含有关 Office 365 中的域的常见问题的解答。</span><span class="sxs-lookup"><span data-stu-id="cec71-106">This article contains answers to Frequently Asked Questions about domains in Office 365.</span></span>

<span data-ttu-id="cec71-107">如果找不到你问题的答案，请留下评论告知我们，我们会将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="cec71-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="cec71-108">什么是 MX 优先级？</span><span class="sxs-lookup"><span data-stu-id="cec71-108">What is MX priority?</span></span>

<span data-ttu-id="cec71-109">邮件传递到具有最低首选项号码（最高优先级）的邮件 exchange 服务器，因此用于邮件路由的 MX 记录的首选项数量（通常为0或*高*优先级）应最低。</span><span class="sxs-lookup"><span data-stu-id="cec71-109">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="cec71-110">创建 MX 记录时，大多数 DNS 承载提供程序都要求您设置首选项号码。</span><span class="sxs-lookup"><span data-stu-id="cec71-110">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="cec71-111">部分标签 "box"*首选项*，并为其添加标签*优先级*。</span><span class="sxs-lookup"><span data-stu-id="cec71-111">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="cec71-112">有些用户需要一个数字，有些要求您选择 "*低*"、"*中*" 或 "*高*"。</span><span class="sxs-lookup"><span data-stu-id="cec71-112">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="cec71-113">如果您只有一个 MX 记录，则优先级或首选项的任何值都是很好的。</span><span class="sxs-lookup"><span data-stu-id="cec71-113">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="cec71-114">如果您有多个，请确保邮件路由的 MX 记录的优先级高于用于验证您拥有该域的用户的路径。</span><span class="sxs-lookup"><span data-stu-id="cec71-114">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="cec71-115">如何验证我的域的 SPF 记录？</span><span class="sxs-lookup"><span data-stu-id="cec71-115">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="cec71-116">必须具有或**仅为 SPF 创建一个 TXT 记录**，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="cec71-116">It's important that you have or create **only one TXT record for SPF**.</span></span> <span data-ttu-id="cec71-117">如果已有 SPF 记录，则应向其追加新的 Office 365 值，而不是创建一个新的。</span><span class="sxs-lookup"><span data-stu-id="cec71-117">If you already have an SPF record, you should append the new Office 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="cec71-118">在添加或更新了 Microsoft 电子邮件的 SPF 记录后，应进行检查以确保使用以下工具之一时的语法正确：</span><span class="sxs-lookup"><span data-stu-id="cec71-118">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="cec71-119">SPF 记录测试工具</span><span class="sxs-lookup"><span data-stu-id="cec71-119">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="cec71-120">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="cec71-120">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="cec71-121">"挖出 web 界面"</span><span class="sxs-lookup"><span data-stu-id="cec71-121">Dig web interface</span></span>](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a><span data-ttu-id="cec71-122">Office 365 如何管理我的 DNS 记录？</span><span class="sxs-lookup"><span data-stu-id="cec71-122">How does Office 365 manage my DNS records?</span></span>

<span data-ttu-id="cec71-123">有两个选项可用于使用 Office 365 的 DNS 管理：</span><span class="sxs-lookup"><span data-stu-id="cec71-123">There are two options for DNS management with Office 365:</span></span>
  
1. <span data-ttu-id="cec71-124">您可以更改您的名称服务器（NS）记录，然后 Microsoft 会处理所有服务特定的记录，如设置电子邮件的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="cec71-124">You change your nameserver (NS) records, and then Microsoft takes care of all the service-specific records, like setting up your MX record for email.</span></span> <span data-ttu-id="cec71-125">**适合**</span><span class="sxs-lookup"><span data-stu-id="cec71-125">**(Recommended)**</span></span>
    
2. <span data-ttu-id="cec71-126">您可以在 DNS 主机上添加电子邮件和其他 Office 365 服务的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="cec71-126">You add DNS records for email and other Office 365 services at your DNS host yourself.</span></span> <span data-ttu-id="cec71-127">**（仅限专家）**</span><span class="sxs-lookup"><span data-stu-id="cec71-127">**(Experts only)**</span></span>
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a><span data-ttu-id="cec71-128">Office 365 创建并托管 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="cec71-128">Office 365 creates and hosts the DNS records</span></span> 
<span data-ttu-id="cec71-129">**优点**</span><span class="sxs-lookup"><span data-stu-id="cec71-129">**Advantages**</span></span> 
- <span data-ttu-id="cec71-130">您无需担心在为 Office 365 服务的 DNS 记录输入的值中出现错误。</span><span class="sxs-lookup"><span data-stu-id="cec71-130">You don't have to worry about making mistakes in the values you enter for the DNS records for Office 365 services.</span></span>  
- <span data-ttu-id="cec71-131">您选择的域注册机构和 DNS 主机具有更大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="cec71-131">You have more flexibility in your choice of domain registrar and DNS host.</span></span> 
- <span data-ttu-id="cec71-132">只要提供程序不支持所有必需的记录类型，任何允许您更改你的名称服务器记录的提供程序都能正常工作。</span><span class="sxs-lookup"><span data-stu-id="cec71-132">Any provider that lets you change your nameserver records will work, even if the provider doesn't support all the required record types.</span></span>   
- <span data-ttu-id="cec71-133">如果 Office 365 添加了新的 DNS 记录，则无需进行更新。</span><span class="sxs-lookup"><span data-stu-id="cec71-133">When Office 365 adds new DNS records, you don't have to make updates.</span></span>  

#### <a name="disadvantages"></a><span data-ttu-id="cec71-134">缺点</span><span class="sxs-lookup"><span data-stu-id="cec71-134">Disadvantages</span></span> 
- <span data-ttu-id="cec71-135">您不能将 DNS 记录更改为托管在 Office 365 之外的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cec71-135">You can't change your DNS records to host email outside of Office 365.</span></span> 
- <span data-ttu-id="cec71-136">如果您已将公共网站与您的域一起使用，如 www.fourthcoffee.com，则必须将用户重定向到 Office 365 中的该地址。</span><span class="sxs-lookup"><span data-stu-id="cec71-136">If you already use a public website with your domain for its address, like www.fourthcoffee.com, you must redirect people to that address from Office 365.</span></span> 
- <span data-ttu-id="cec71-137">设置重定向需要静态 IP 地址，这对公共网站来说并不总是很容易使用。</span><span class="sxs-lookup"><span data-stu-id="cec71-137">Setting up redirection requires a static IP address, which is not always easily available for public websites.</span></span> <span data-ttu-id="cec71-138">-如果当前的域注册机构不允许更改域的名称服务器记录，则必须切换到不同的注册器，才能使用此 DNS 管理选项。</span><span class="sxs-lookup"><span data-stu-id="cec71-138">- If your current domain registrar doesn't allow you to change your domain's nameserver records, you have to switch to a different registrar to use this DNS management option.</span></span>  

 ### <a name="you-manage-the-dns-records-yourself"></a><span data-ttu-id="cec71-139">您自己管理 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="cec71-139">You manage the DNS records yourself</span></span> 
 #### <a name="advantages"></a><span data-ttu-id="cec71-140">优点</span><span class="sxs-lookup"><span data-stu-id="cec71-140">Advantages</span></span>
- <span data-ttu-id="cec71-141">您可以控制 Office 365 服务的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="cec71-141">You control the DNS records for Office 365 services.</span></span>   
- <span data-ttu-id="cec71-142">如果您有一个包含域的公共网站（如 www.fourthcoffee.com），则无需担心如何使用重定向来确保用户在 Office 365 中设置域后仍可访问您的网站。</span><span class="sxs-lookup"><span data-stu-id="cec71-142">If you have a public website with your domain for its address, like www.fourthcoffee.com, you don't have to worry about using redirection to make sure people can still get to your website after you set up your domain in Office 365.</span></span>    
- <span data-ttu-id="cec71-143">您可以灵活地将电子邮件托管在其他位置，如本地 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="cec71-143">You have the flexibility to host email somewhere else, such as with an on-premises Exchange server.</span></span>  
 
#### <a name="disadvantages"></a><span data-ttu-id="cec71-144">缺点</span><span class="sxs-lookup"><span data-stu-id="cec71-144">Disadvantages</span></span>
<span data-ttu-id="cec71-145">您必须自己设置适用于 Office 365 服务的 DNS 记录（除非您有 GoDaddy 域）。</span><span class="sxs-lookup"><span data-stu-id="cec71-145">You have to set up the DNS records for Office 365 services yourself (unless you have a GoDaddy domain).</span></span> 
-  <span data-ttu-id="cec71-146">如果当前 DNS 主机不支持 Microsoft 365 的所有必需的记录类型，则某些功能将不可用，您可能需要切换到其他 DNS 主机。</span><span class="sxs-lookup"><span data-stu-id="cec71-146">If your current DNS host doesn't support all of the required record types for Microsoft 365, some features won't be available and you might need to switch to a different DNS host.</span></span> 
- <span data-ttu-id="cec71-147">当 Office 365 更改 DNS 记录的要求或添加新服务时，您必须在 DNS 主机上自己进行更新。</span><span class="sxs-lookup"><span data-stu-id="cec71-147">When Office 365 changes requirements for DNS records, or adds new services, you have to make updates yourself at your DNS host.</span></span> 
   
## <a name="what-is-a-domain-name"></a><span data-ttu-id="cec71-148">什么是域名？</span><span class="sxs-lookup"><span data-stu-id="cec71-148">What is a domain name?</span></span>


<span data-ttu-id="cec71-149">域是 **@** 注册电子邮件地址后和 Web 地址中 **www.**</span><span class="sxs-lookup"><span data-stu-id="cec71-149">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="cec71-150">后显示的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="cec71-150">in web addresses.</span></span> <span data-ttu-id="cec71-151">它通常采用您组织的名称和标准 Internet 后缀的形式，如*yourbusiness.com*或*stateuniversity.edu。*</span><span class="sxs-lookup"><span data-stu-id="cec71-151">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="cec71-152">将自定义域（**如 "contoso.com \@ "）** 与 Office 365 结合使用，可以帮助为你的品牌建立可信度和认可。</span><span class="sxs-lookup"><span data-stu-id="cec71-152">Using a custom domain like "**rob\@contoso.com**" with Office 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="cec71-153">你可以[在 Office 365 中购买域，我们将自动对其进行设置](../get-help-with-domains/buy-a-domain-name.md)，也可以从域注册机构购买或将已有的域引入。</span><span class="sxs-lookup"><span data-stu-id="cec71-153">You can [buy a domain in Office 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a><span data-ttu-id="cec71-154">是否可以将从 Microsoft 那里购买的域转移到另一个提供商？</span><span class="sxs-lookup"><span data-stu-id="cec71-154">Can I transfer a domain I purchased from Microsoft to another provider?</span></span>

<span data-ttu-id="cec71-155">可以，但在购买 Office 365 后的60天后，不能将 Office 365 域传输到另一个注册机构。</span><span class="sxs-lookup"><span data-stu-id="cec71-155">Yes, but you can't transfer an Office 365 domain to another registrar until 60 days after you purchased it with Office 365.</span></span>

<span data-ttu-id="cec71-156">请注意， *Whois*查询会将作为通配符的 Office 365 购买的域注册器显示为 "中西部域" LLC。</span><span class="sxs-lookup"><span data-stu-id="cec71-156">Please note that a *Whois* query will show an Office 365 purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="cec71-157">但是，应仅与 Office 365 购买域联系，以了解有关 office 365 的事宜。</span><span class="sxs-lookup"><span data-stu-id="cec71-157">However, only Office 365 should be contacted regarding your Office 365 purchased domain.</span></span>
  
<span data-ttu-id="cec71-158">按照以下步骤获取 Office 365 中的代码，然后转到其他域注册机构的网站以设置将您的域名转移到该注册器。</span><span class="sxs-lookup"><span data-stu-id="cec71-158">Follow the steps below to get the code at Office 365, and then go to the other domain registrar's website to set up transferring your domain name to that registrar.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cec71-159">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cec71-159">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cec71-160">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cec71-160">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cec71-161">在 "管理中心" 中，转到 "**设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">许可证</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="cec71-161">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="cec71-162">在 "**域**" 页上，选择要转移到其他域注册机构的 Office 365 域，然后选择 "**域传输**  >  **启用域传输**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-162">On the **Domains** page, select the Office 365 domain that you want to transfer to another domain registrar, and then select **Domain Transfer** > **Enable domain transfer**.</span></span>
       
4. <span data-ttu-id="cec71-163">按照准备转移您的域的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="cec71-163">Follow the steps to prepare for transferring your domain.</span></span>
    
5. <span data-ttu-id="cec71-164">在获取代码之后，转到域注册机构的网站，您想要提前管理您的域名，并按照其传输域的指导进行操作（在其网站上搜索帮助）。</span><span class="sxs-lookup"><span data-stu-id="cec71-164">After you get the code, go to the website of the domain registrar where you want to manage your domain name going forward and follow their directions for transferring a domain (search for help on their website).</span></span>
    
6. <span data-ttu-id="cec71-165">如果需要再次查看该代码，请在 Office 365 中的 "**域设置**" 页上，选择 "**查看域传输的授权代码**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-165">If you need to see the code again, on the **Domain settings** page in Office 365, select **View authorization code for domain transfer**.</span></span>
    
7. <span data-ttu-id="cec71-166">传输完成后，你将在新域注册机构中续订你的域。</span><span class="sxs-lookup"><span data-stu-id="cec71-166">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>
    
8. <span data-ttu-id="cec71-167">若要完成此过程，请返回到管理中心**域**页面，并选择 "**完成域传输**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-167">To finish the process, go back to the admin center **Domains** page and select **Complete Domain Transfer**.</span></span> 

<span data-ttu-id="cec71-168">*注意：请注意，Office 365 购买的域不符合名称服务器更改或在 Office 365 租户之间传输域的情况。 如果需要其中任一项，则需要将域注册转移到其他注册器。*</span><span class="sxs-lookup"><span data-stu-id="cec71-168">*Note: Please note that Office 365 purchased domains are not eligible for Name Server changes or transferring the domain between Office 365 Tenants.  If either of these are required, the domain registration will need to be transferred to another registrar.*</span></span>
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a><span data-ttu-id="cec71-169">如何更改我的 DNS 记录在 Office 365 中的管理方式？</span><span class="sxs-lookup"><span data-stu-id="cec71-169">How do I change how my DNS records are managed in Office 365?</span></span>

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a><span data-ttu-id="cec71-170">将 DNS 管理更改为 Office 365 之外的 DNS 主机</span><span class="sxs-lookup"><span data-stu-id="cec71-170">Change DNS management to a DNS host outside Office 365</span></span>
   
1. <span data-ttu-id="cec71-171">登录到您的域的域注册机构。</span><span class="sxs-lookup"><span data-stu-id="cec71-171">Sign in to the domain registrar for your domain.</span></span>
    
2. <span data-ttu-id="cec71-172">在注册器网站上查找您更新 nameserver 记录的区域，并更新名称服务器以指向您的域的 DNS 主机。</span><span class="sxs-lookup"><span data-stu-id="cec71-172">Find the area on the registrar's website where you update nameserver records, and update the nameservers to point to your domain's DNS host.</span></span> <span data-ttu-id="cec71-173">（DNS 主机通常是域注册机构。）</span><span class="sxs-lookup"><span data-stu-id="cec71-173">(The DNS host is often the domain registrar.)</span></span>
    
3. <span data-ttu-id="cec71-174">按照链接转到域安装向导：</span><span class="sxs-lookup"><span data-stu-id="cec71-174">Follow a link to go to the domains setup wizard:</span></span>

::: moniker range="o365-worldwide"

4. <span data-ttu-id="cec71-175">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cec71-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

4. <span data-ttu-id="cec71-176">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cec71-176">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

4. <span data-ttu-id="cec71-177">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cec71-177">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
5. <span data-ttu-id="cec71-178">在 "**域**" 页上，选择要切换的域，然后选择 " **DNS 管理**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-178">On the **Domains** page, select the domain you're switching, and select **DNS management**.</span></span>
    
6. <span data-ttu-id="cec71-179">在 "域安装向导" 的 "**设置联机服务**" 页上，选择 "**我将管理自己的 DNS 记录**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-179">In the domains setup wizard, on the **Set up your online services** page, select **I'll manage my own DNS records**, and then select **Next**.</span></span>
    
7. <span data-ttu-id="cec71-180">将向导建议的 DNS 记录添加到你的注册机构网站的 "**更新 DNS 设置**" 页上。</span><span class="sxs-lookup"><span data-stu-id="cec71-180">Add the DNS records suggested by the wizard on the **Update DNS settings** page to your registrar's website.</span></span> 
    
8. <span data-ttu-id="cec71-181">添加记录后，返回到 Office 365 并选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-181">After you've added the records, come back to Office 365 and select **Verify**.</span></span>
    

### <a name="change-dns-management-to-office-365"></a><span data-ttu-id="cec71-182">将 DNS 管理更改为 Office 365</span><span class="sxs-lookup"><span data-stu-id="cec71-182">Change DNS management to Office 365</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cec71-183">在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。。</span><span class="sxs-lookup"><span data-stu-id="cec71-183">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page..</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cec71-184">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cec71-184">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cec71-185">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cec71-185">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="cec71-186">在 "**域**" 页上，选择要切换的域，然后选择 " **DNS 管理**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-186">On the **Domains** page, select the domain you're switching, and select **DNS Management**.</span></span>
    
3. <span data-ttu-id="cec71-187">在 "域设置向导" 的 "**设置联机服务**" 页上，选择 "**设置我的联机服务"。（推荐）**，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-187">In the domains setup wizard, on the **Set up your online services** page, select **Set up my online services for me. (Recommended)**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="cec71-188">如果尚未验证域，请按照第一步操作。</span><span class="sxs-lookup"><span data-stu-id="cec71-188">If you haven't verified the domain yet, follow the steps to do that first.</span></span>
    
5. <span data-ttu-id="cec71-189">在 "**更新 DNS 设置**" 页上，列出了 Office 365 的名称服务器。</span><span class="sxs-lookup"><span data-stu-id="cec71-189">On the **Update DNS settings** page, we list the nameservers for Office 365.</span></span> <span data-ttu-id="cec71-190">转到域的域注册机构，并将名称服务器更新为 Office 365 名称服务器。</span><span class="sxs-lookup"><span data-stu-id="cec71-190">Go to the domain registrar for your domain, and update the nameservers to the Office 365 nameservers.</span></span> 
    
4. <span data-ttu-id="cec71-191">更新名称服务器后，请**至少等待一小时**。</span><span class="sxs-lookup"><span data-stu-id="cec71-191">After you've updated the nameservers, **wait at least an hour**.</span></span> <span data-ttu-id="cec71-192">然后，返回到 Office 365 中的向导，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-192">Then, back in the wizard in Office 365, select **Verify**.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="cec71-193">如果我的 DNS 提供商不支持某些记录类型，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="cec71-193">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="cec71-194">如果您管理自己的 DNS 记录，并且 DNS 主机不支持 Office 365 所需的所有 DNS 记录，则某些 Office 365 功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="cec71-194">If you manage your own DNS records and your DNS host does not support all the DNS records that Office 365 needs, some Office 365 features won't work.</span></span> <span data-ttu-id="cec71-195">我们建议您将您的域转移到支持所有必需的 DNS 记录的注册器。</span><span class="sxs-lookup"><span data-stu-id="cec71-195">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="cec71-196">支持所有必需的 DNS 记录的提供程序：</span><span class="sxs-lookup"><span data-stu-id="cec71-196">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="cec71-197">Dynadot</span><span class="sxs-lookup"><span data-stu-id="cec71-197">Dynadot</span></span>
    
- <span data-ttu-id="cec71-198">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="cec71-198">eNomCentral</span></span>
    
- <span data-ttu-id="cec71-199">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="cec71-199">Europe Registry</span></span>
    
- <span data-ttu-id="cec71-200">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="cec71-200">GoDaddy</span></span>
    
- <span data-ttu-id="cec71-201">悬停</span><span class="sxs-lookup"><span data-stu-id="cec71-201">Hover</span></span>
    
- <span data-ttu-id="cec71-202">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="cec71-202">MyHosting.com</span></span>
    
- <span data-ttu-id="cec71-203">Name.com</span><span class="sxs-lookup"><span data-stu-id="cec71-203">Name.com</span></span>
    
- <span data-ttu-id="cec71-204">几乎免费的语音</span><span class="sxs-lookup"><span data-stu-id="cec71-204">Nearly Free Speech</span></span>
    
- <span data-ttu-id="cec71-205">Nettica</span><span class="sxs-lookup"><span data-stu-id="cec71-205">Nettica</span></span>
    
- <span data-ttu-id="cec71-206">网络信息中心 (NIC)</span><span class="sxs-lookup"><span data-stu-id="cec71-206">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="cec71-207">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="cec71-207">Network Solutions</span></span>
    
- <span data-ttu-id="cec71-208">Register.com</span><span class="sxs-lookup"><span data-stu-id="cec71-208">Register.com</span></span>
    
 <span data-ttu-id="cec71-209">**如果不支持 SRV 记录**，以下 Office 365 功能将不可用：</span><span class="sxs-lookup"><span data-stu-id="cec71-209">**If SRV records are not supported**, the following Office 365 features are not available:</span></span> 
  
- <span data-ttu-id="cec71-210">Skype for business Online IM 和状态与 Outlook Web App 的集成</span><span class="sxs-lookup"><span data-stu-id="cec71-210">Skype for Business Online IM and presence integration with Outlook Web App</span></span>
    
- <span data-ttu-id="cec71-211">其他组织中与 Skype for Business Online 用户的外部通信（联合）。</span><span class="sxs-lookup"><span data-stu-id="cec71-211">External communication (federation) with Skype for Business Online users in other organizations.</span></span>
    
- <span data-ttu-id="cec71-212">使用 Microsoft 帐户（以前称为 Windows Live ID）登录的 Skype for Business Online 用户的公共 Internet 连接（PIC）。</span><span class="sxs-lookup"><span data-stu-id="cec71-212">Public Internet Connectivity (PIC) with Skype for Business Online users signed in with a Microsoft account (formerly known as a Windows Live ID).</span></span>
    
 <span data-ttu-id="cec71-213">**如果不支持多个 CNAME 记录，** 则必须在 Skype For business Online 的以下功能之间进行选择：</span><span class="sxs-lookup"><span data-stu-id="cec71-213">**If multiple CNAME records are not supported,** you have to choose between the following features for Skype for Business Online:</span></span> 
  
- <span data-ttu-id="cec71-214">电子邮件桌面客户端和移动客户端可以使用自动发现自动查找 Exchange Online 服务，以便用户无需输入服务器名称即可登录。</span><span class="sxs-lookup"><span data-stu-id="cec71-214">Email desktop clients and mobile clients can use Autodiscover to automatically find the Exchange Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="cec71-215">Skype for Business Online 桌面客户端可以使用自动发现自动查找 Skype for Business Online 服务，以便用户无需输入服务器名称即可登录。</span><span class="sxs-lookup"><span data-stu-id="cec71-215">Skype for Business Online desktop clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>
    
- <span data-ttu-id="cec71-216">Skype for Business Online 移动客户端可以使用自动发现来自动查找 Skype for Business Online 服务，以便用户无需输入服务器名称即可登录。</span><span class="sxs-lookup"><span data-stu-id="cec71-216">Skype for Business Online mobile clients can use Autodiscover to automatically find the Skype for Business Online service so that users can sign in without having to enter a server name.</span></span>

- <span data-ttu-id="cec71-217">Microsoft 团队与 Skype for Business 的联盟（本地或联机）。</span><span class="sxs-lookup"><span data-stu-id="cec71-217">Microsoft Teams federation with Skype for Business, either on-premises or online.</span></span> <span data-ttu-id="cec71-218">有关详细信息，请参阅为[Microsoft 团队准备贵组织的网络](https://docs.microsoft.com/microsoftteams/prepare-network)。</span><span class="sxs-lookup"><span data-stu-id="cec71-218">For more information, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span></span>
    
 <span data-ttu-id="cec71-219">**如果 SPF/TXT 记录不受支持，则**其他人可能可以使用您的域发送垃圾邮件或其他恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cec71-219">**If SPF/TXT records are not supported**, other people may be able to use your domain to send spam or other malicious email.</span></span> <span data-ttu-id="cec71-220">SPF 记录通过识别授权从您的域发送电子邮件的服务器来发挥作用。</span><span class="sxs-lookup"><span data-stu-id="cec71-220">SPF records work by identifying the servers that are authorized to send email from your domain.</span></span> 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a><span data-ttu-id="cec71-221">如何设置或更改 Office 365 中的默认域？</span><span class="sxs-lookup"><span data-stu-id="cec71-221">How do I set or change the default domain in Office 365?</span></span>

<span data-ttu-id="cec71-222">您必须至少有一个添加到 Office 365 的自定义域，然后才能选择默认域。</span><span class="sxs-lookup"><span data-stu-id="cec71-222">You must have at least one custom domain that you've added to Office 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cec71-223">在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cec71-223">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cec71-224">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cec71-224">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cec71-225">在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="cec71-225">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="cec71-226">在 "**域**" 页上，选择要将其设置为新电子邮件地址的默认域的域。</span><span class="sxs-lookup"><span data-stu-id="cec71-226">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="cec71-227">选择“**设为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="cec71-227">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="cec71-228">您不能更改*onmicrosoft.com*域的名称。</span><span class="sxs-lookup"><span data-stu-id="cec71-228">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="cec71-229">您不能更改*onmicrosoft.de*域的名称。</span><span class="sxs-lookup"><span data-stu-id="cec71-229">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="cec71-230">您不能更改*partner.onmschina.cn*域的名称。</span><span class="sxs-lookup"><span data-stu-id="cec71-230">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a><span data-ttu-id="cec71-231">我可以将自定义子域或多个域添加到 Office 365 吗？</span><span class="sxs-lookup"><span data-stu-id="cec71-231">Can I add custom subdomains or multiple domains to Office 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="cec71-232">是的！</span><span class="sxs-lookup"><span data-stu-id="cec71-232">Yes!</span></span> <span data-ttu-id="cec71-233">若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。</span><span class="sxs-lookup"><span data-stu-id="cec71-233">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="cec71-234">如果要让 Microsoft 管理具有 NS 记录的 DNS 设置，或者如果您从 Microsoft 购买了域，则无法添加子域。</span><span class="sxs-lookup"><span data-stu-id="cec71-234">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="cec71-235">是的！</span><span class="sxs-lookup"><span data-stu-id="cec71-235">Yes!</span></span> <span data-ttu-id="cec71-236">若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。</span><span class="sxs-lookup"><span data-stu-id="cec71-236">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="cec71-237">如果要让 Microsoft 管理具有 NS 记录的 DNS 设置，或者如果您从 Microsoft 购买了域，则无法添加子域。</span><span class="sxs-lookup"><span data-stu-id="cec71-237">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="cec71-238">是的！</span><span class="sxs-lookup"><span data-stu-id="cec71-238">Yes!</span></span> <span data-ttu-id="cec71-239">若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。</span><span class="sxs-lookup"><span data-stu-id="cec71-239">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="cec71-240">如果您正在让世纪管理具有 NS 记录的 DNS 设置，则不能添加子域。</span><span class="sxs-lookup"><span data-stu-id="cec71-240">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="cec71-241">通常情况下，最多可以向 Office 365 订阅添加900个域。</span><span class="sxs-lookup"><span data-stu-id="cec71-241">Typically, you can add up to 900 domains to your Office 365 subscription.</span></span>
  
<span data-ttu-id="cec71-242">例如，可以添加域 contoso.com 和 contosomarketing.com，然后添加子域 www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com 等等。</span><span class="sxs-lookup"><span data-stu-id="cec71-242">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="cec71-243">添加子域时，将根据正在验证的父域自动对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="cec71-243">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="cec71-244">将多个域添加到 Office 365 时，可以在已添加的任何域中承载任何服务（如电子邮件）。</span><span class="sxs-lookup"><span data-stu-id="cec71-244">When you add multiple domains to Office 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="cec71-245">*当您将电子邮件更改为 Office 365 时，通过更新域的 MX 记录，发送到该域的所有电子邮件都将开始进入 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="cec71-245">*When you change your email to Office 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Office 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="cec71-246">如果您已向 Office 365 租户添加了 contoso.com 域，您还可以将子域 xyz.contoso.com 添加到另一个 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="cec71-246">If you have already added a contoso.com domain to an Office 365 tenant, you can also add the subdomain xyz.contoso.com to another Office 365 tenant.</span></span> <span data-ttu-id="cec71-247">添加子域时，系统将提示您在 DNS 托管提供程序中添加 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="cec71-247">When adding the subdomain, you will be prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="cec71-248">为什么我有 "onmicrosoft.com" 域？</span><span class="sxs-lookup"><span data-stu-id="cec71-248">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="cec71-249">当您注册服务时，Office 365 将为您创建一个域，如*contoso.onmicrosoft.com*。</span><span class="sxs-lookup"><span data-stu-id="cec71-249">Office 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="cec71-250">注册时创建的用户 ID 包括域，如*alan@contoso.onmicrosoft.com*。</span><span class="sxs-lookup"><span data-stu-id="cec71-250">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="cec71-251">**如果您想让您的电子邮件看起来像*alan \@ contoso.com*：** [购买域](../get-help-with-domains/buy-a-domain-name.md)，或者只需按照 "[将用户和域添加到 Office 365](add-domain.md)中的步骤" 中的步骤，如果您已拥有它。</span><span class="sxs-lookup"><span data-stu-id="cec71-251">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="cec71-252">**注册后，不能重命名 .onmicrosoft 域。**</span><span class="sxs-lookup"><span data-stu-id="cec71-252">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="cec71-253">例如，如果您选择的初始域是 "fourthcoffee.onmicrosoft.com"，则不能将其更改为 "fabrikam.onmicrosoft.com"。</span><span class="sxs-lookup"><span data-stu-id="cec71-253">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="cec71-254">若要使用不同的 onmicrosoft.com 域，必须启动一个使用 Office 365 的新订阅。</span><span class="sxs-lookup"><span data-stu-id="cec71-254">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="cec71-255">**您不能重命名团队网站 URL。**</span><span class="sxs-lookup"><span data-stu-id="cec71-255">**You can't rename your team site URL.**</span></span> <span data-ttu-id="cec71-256">您的团队网站 URL 基于您的 onmicrosoft.com 域名。</span><span class="sxs-lookup"><span data-stu-id="cec71-256">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="cec71-257">遗憾的是，由于 SharePoint Online 体系结构的工作方式，无法重命名团队网站。</span><span class="sxs-lookup"><span data-stu-id="cec71-257">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="cec71-258">**您不能删除您的 .onmicrosoft 域。**</span><span class="sxs-lookup"><span data-stu-id="cec71-258">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="cec71-259">Office 365 需要将其保留，因为它在你的订阅的幕后使用。</span><span class="sxs-lookup"><span data-stu-id="cec71-259">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="cec71-260">但在添加自定义域之后，您无需自己使用域。</span><span class="sxs-lookup"><span data-stu-id="cec71-260">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="cec71-261">即使在添加了域之后，也可以继续使用初始 onmicrosoft.com 域。</span><span class="sxs-lookup"><span data-stu-id="cec71-261">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="cec71-262">它仍适用于电子邮件和其他服务，因此是你的选择。</span><span class="sxs-lookup"><span data-stu-id="cec71-262">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="cec71-263">为什么我有 "onmicrosoft.de" 域？</span><span class="sxs-lookup"><span data-stu-id="cec71-263">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="cec71-264">当您注册服务时，Office 365 将为您创建一个域，如*contoso.onmicrosoft.de*。</span><span class="sxs-lookup"><span data-stu-id="cec71-264">Office 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="cec71-265">注册时创建的用户 ID 包括域，如*alan@contoso.onmicrosoft.de*。</span><span class="sxs-lookup"><span data-stu-id="cec71-265">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="cec71-266">**如果您想让您的电子邮件看起来像*alan@contoso.de*：** [购买域](../get-help-with-domains/buy-a-domain-name.md)，或者只需按照[将用户和域添加到 Office 365](add-domain.md)中的步骤（如果您已拥有它）。</span><span class="sxs-lookup"><span data-stu-id="cec71-266">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Office 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="cec71-267">**注册后，不能重命名 .onmicrosoft 域。**</span><span class="sxs-lookup"><span data-stu-id="cec71-267">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="cec71-268">例如，如果您选择的初始域是 "fourthcoffee.onmicrosoft.de"，则不能将其更改为 "fabrikam.onmicrosoft.de"。</span><span class="sxs-lookup"><span data-stu-id="cec71-268">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="cec71-269">若要使用不同的 onmicrosoft.de 域，必须启动一个使用 Office 365 的新订阅。</span><span class="sxs-lookup"><span data-stu-id="cec71-269">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Office 365.</span></span> 
    
- <span data-ttu-id="cec71-270">**您不能重命名团队网站 URL。**</span><span class="sxs-lookup"><span data-stu-id="cec71-270">**You can't rename your team site URL.**</span></span> <span data-ttu-id="cec71-271">您的团队网站 URL 基于您的 onmicrosoft.de 域名。遗憾的是，由于 SharePoint Online 体系结构的工作方式，无法重命名团队网站。</span><span class="sxs-lookup"><span data-stu-id="cec71-271">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="cec71-272">**您不能删除您的 .onmicrosoft 域。**</span><span class="sxs-lookup"><span data-stu-id="cec71-272">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="cec71-273">Office 365 需要将其保留，因为它在你的订阅的幕后使用。</span><span class="sxs-lookup"><span data-stu-id="cec71-273">Office 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="cec71-274">但在添加自定义域之后，您无需自己使用域。</span><span class="sxs-lookup"><span data-stu-id="cec71-274">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="cec71-275">即使在添加了域之后，也可以继续使用初始 onmicrosoft.de 域。</span><span class="sxs-lookup"><span data-stu-id="cec71-275">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="cec71-276">它仍适用于电子邮件和其他服务，因此是你的选择。</span><span class="sxs-lookup"><span data-stu-id="cec71-276">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="cec71-277">如何验证我的非盈利或教育状态？</span><span class="sxs-lookup"><span data-stu-id="cec71-277">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="cec71-278">在[管理中心](https://docs.microsoft.com/microsoft-365/admin/admin-home)中选择 "**设置**" 以启动向导。</span><span class="sxs-lookup"><span data-stu-id="cec71-278">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="cec71-279">（请务必先登录到 Office 365。）</span><span class="sxs-lookup"><span data-stu-id="cec71-279">(Be sure to sign in to Office 365 first.)</span></span> 
    
2. <span data-ttu-id="cec71-280">若要成为你的学校的管理员，请选择 "在 Office 365 中**成为管理员**" 选项。</span><span class="sxs-lookup"><span data-stu-id="cec71-280">To become the admin for your school, select the **Become an admin** option in Office 365.</span></span> 
    
3. <span data-ttu-id="cec71-281">系统将提示你在你的域的 DNS 主机网站上添加 TXT DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="cec71-281">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="cec71-282">为什么？</span><span class="sxs-lookup"><span data-stu-id="cec71-282">Why?</span></span> <span data-ttu-id="cec71-283">由于通过在 DNS 主机上登录并为您的域添加记录，因此您可以向 Office 365 证明您拥有此域名。</span><span class="sxs-lookup"><span data-stu-id="cec71-283">Because by signing in at the DNS host and adding a record for your domain, you prove to Office 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="cec71-284">添加记录后，您将返回到 Office 365 门户，并确认您已添加它，以便 Office 365 可以进行检查。</span><span class="sxs-lookup"><span data-stu-id="cec71-284">After you add the record, you'll go back to the Office 365 portal and confirm that you've added it, so Office 365 can check.</span></span>
    
<span data-ttu-id="cec71-285">是否有非盈利的，希望获取 Office 365？</span><span class="sxs-lookup"><span data-stu-id="cec71-285">Have a nonprofit and want to get Office 365?</span></span> <span data-ttu-id="cec71-286">[请确保您的组织符合](https://www.microsoft.com/en-us/nonprofits/eligibility)条件，然后注册服务。</span><span class="sxs-lookup"><span data-stu-id="cec71-286">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="cec71-287">想要了解有关成为你的学校的管理员的详细信息吗？</span><span class="sxs-lookup"><span data-stu-id="cec71-287">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="cec71-288">[了解相关信息](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。</span><span class="sxs-lookup"><span data-stu-id="cec71-288">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a><span data-ttu-id="cec71-289">是否可以使用自定义域中的几个电子邮件地址来试点生产 Office 365？</span><span class="sxs-lookup"><span data-stu-id="cec71-289">Can I pilot Office 365 with just a few email addresses from my custom domain?</span></span>

<span data-ttu-id="cec71-290">您可以，但有一些限制：</span><span class="sxs-lookup"><span data-stu-id="cec71-290">You can, but there are limitations:</span></span>
  
- <span data-ttu-id="cec71-291">您当前的电子邮件提供商必须提供电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="cec71-291">Your current email provider must provide email forwarding.</span></span>
    
- <span data-ttu-id="cec71-292">您需要在 DNS 托管提供商处管理与 Office 365 相关的 DNS 记录，而不是让 Office 365 为您管理这些记录。</span><span class="sxs-lookup"><span data-stu-id="cec71-292">You need to manage your Office 365-related DNS records at your DNS hosting provider, rather than having Office 365 manage these records for you.</span></span> <span data-ttu-id="cec71-293">若要了解这需要什么，请参阅当你想要管理自己的 DNS 记录时，将你的域添加到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cec71-293">To learn what this entails, see Add your domain to Office 365 when you want to manage your own DNS records.</span></span>
    
- <span data-ttu-id="cec71-294">某些 Office 365 功能将不可用：</span><span class="sxs-lookup"><span data-stu-id="cec71-294">Some Office 365 features won't be available:</span></span>
- <span data-ttu-id="cec71-295">用户将无法查看其他电子邮件提供商的用户的忙/闲信息。</span><span class="sxs-lookup"><span data-stu-id="cec71-295">Users won't be able to see free/busy information for the users who are on the other email provider.</span></span>
- <span data-ttu-id="cec71-296">管理员将无法从一个位置管理每个人的帐户。</span><span class="sxs-lookup"><span data-stu-id="cec71-296">Admins won't be able to administer everyone's accounts from one place.</span></span>
- <span data-ttu-id="cec71-297">用户可能无法使用 Office 365 垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="cec71-297">Users may not be able to use Office 365 spam filtering</span></span>

### <a name="how-to-set-up-an-office-365-pilot"></a><span data-ttu-id="cec71-298">如何设置 Office 365 试点</span><span class="sxs-lookup"><span data-stu-id="cec71-298">How to set up an Office 365 pilot</span></span>
    
1. <span data-ttu-id="cec71-299">登录到 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="cec71-299">Sign in to the Microsoft 365 admin center</span></span>
    
    1. <span data-ttu-id="cec71-300">使用工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cec71-300">Sign in to Office 365 with your work or school account.</span></span>
        
    2. <span data-ttu-id="cec71-301">转到 "**设置** \> **域**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-301">Go to **Settings** \> **Domains**.</span></span> 
    
2. <span data-ttu-id="cec71-302">验证您是否拥有要使用的域</span><span class="sxs-lookup"><span data-stu-id="cec71-302">Verify that you own the domain you want to use</span></span>
    
    1. <span data-ttu-id="cec71-303">在 "**域**" 页上，选择 "**添加域**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-303">On the **Domains** page, select **Add domain**.</span></span> 
        
    2. <span data-ttu-id="cec71-304">在面板中，键入域（在此示例中为 cohowinery.com），然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-304">In the panel, type the domain, in this example cohowinery.com, and then select **Next**.</span></span> 
        
    3. <span data-ttu-id="cec71-305">在 "**验证**域" 页上，按照分步说明操作。</span><span class="sxs-lookup"><span data-stu-id="cec71-305">On the **Verify** domain page, follow the step-by-step instructions.</span></span> 
        
    4. <span data-ttu-id="cec71-306">在下拉列表中，选择您的 DNS 托管提供商，然后按照说明操作以表明您拥有该域。</span><span class="sxs-lookup"><span data-stu-id="cec71-306">In the drop-down list, select your DNS hosting provider, and follow the instructions to show that you own the domain.</span></span>
        
    5. <span data-ttu-id="cec71-307">选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-307">Select **Verify**.</span></span> <span data-ttu-id="cec71-308">要使 DNS 更改生效，需要几分钟和72小时的时间。</span><span class="sxs-lookup"><span data-stu-id="cec71-308">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span> 
        
    6. <span data-ttu-id="cec71-309">验证成功后，系统将要求你修改 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="cec71-309">When verification is successful, you'll be asked to modify your DNS records.</span></span>
    
3. <span data-ttu-id="cec71-310">将域标记为在 Exchange Online 中共享</span><span class="sxs-lookup"><span data-stu-id="cec71-310">Mark the domain as shared in Exchange Online</span></span>
    
    1. <span data-ttu-id="cec71-311">转到**Exchange 管理中心**（EAC）。</span><span class="sxs-lookup"><span data-stu-id="cec71-311">Go to the **Exchange admin center** (EAC).</span></span> 
        
    2. <span data-ttu-id="cec71-312">在 "**邮件流**" 部分，选择 "**接受域**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-312">In the **Mail flow** section, select **Accepted domains**.</span></span> 
        
    3. <span data-ttu-id="cec71-313">双击要修改的域。</span><span class="sxs-lookup"><span data-stu-id="cec71-313">Double-click the domain you want to modify.</span></span>
        
    4. <span data-ttu-id="cec71-314">在打开的窗口中，选择 "**内部中继**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-314">In the window that opens, select **Internal Relay**.</span></span> 
        
    5. <span data-ttu-id="cec71-315">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cec71-315">Select **Save**.</span></span> <span data-ttu-id="cec71-316">此设置可能需要几分钟时间才能生效。</span><span class="sxs-lookup"><span data-stu-id="cec71-316">This setting may require a few minutes to take effect.</span></span> 
    
4. <span data-ttu-id="cec71-317">（可选）取消阻止现有的电子邮件服务器</span><span class="sxs-lookup"><span data-stu-id="cec71-317">Optionally, unblock the existing email server</span></span>
    
    1. <span data-ttu-id="cec71-318">Office 365 使用 Exchange Online Protection （EOP）进行垃圾邮件保护。</span><span class="sxs-lookup"><span data-stu-id="cec71-318">Office 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="cec71-319">如果 EOP 检测到当前邮件服务器要转发的大量垃圾邮件，则可能会阻止邮件，从而阻止转发工作。</span><span class="sxs-lookup"><span data-stu-id="cec71-319">If EOP detects a high volume of spam being forwarded by your current mail server, it may block it, which would prevent forwarding from working.</span></span> <span data-ttu-id="cec71-320">如果你确信其他电子邮件提供商使用的垃圾邮件保护，则可以在 Office 365 中对其服务器进行白名单。</span><span class="sxs-lookup"><span data-stu-id="cec71-320">If you are confident with the spam protection your other email provider uses, you can whitelist their server in Office 365.</span></span> <span data-ttu-id="cec71-321">但是，这还将允许通过原始服务器到达的所有垃圾邮件进入 Office 365 邮箱，并且您无法评估 Office 365 如何防止垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="cec71-321">However, this will also allow any spam that arrives through your original server to come through to the Office 365 mailboxes, and you won't be able to evaluate how well Office 365 prevents spam.</span></span>
    
    2. <span data-ttu-id="cec71-322">转到 Exchange 管理中心（EAC）。</span><span class="sxs-lookup"><span data-stu-id="cec71-322">Go to Exchange admin center (EAC).</span></span>
        
    3. <span data-ttu-id="cec71-323">在 EAC 中，选择 "**保护**"，然后选择 "**连接筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-323">In EAC, select **Protection**, and then select **Connection filter**.</span></span> 
        
    4. <span data-ttu-id="cec71-324">在 " **IP 允许" 列表**中，选择 **+** ""，然后添加可以从当前电子邮件提供商获取的邮件服务器 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="cec71-324">In the **IP Allow list**, select **+**, and add the mail server IP address that you can get from your current email provider.</span></span> 
    
5. <span data-ttu-id="cec71-325">创建用户帐户并设置主（答复）地址</span><span class="sxs-lookup"><span data-stu-id="cec71-325">Create user accounts and set the primary (reply-to) address</span></span>
    
    1. <span data-ttu-id="cec71-326">转到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="cec71-326">Go to the Microsoft 365 admin center.</span></span>
        
    2. <span data-ttu-id="cec71-327">在左侧导航栏上，选择 "**用户** \> **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-327">On the left navigation bar, select **Users** \> **Active Users**.</span></span> 
        
    3. <span data-ttu-id="cec71-328">创建用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cec71-328">Create the user accounts.</span></span>
        
    4. <span data-ttu-id="cec71-329">对于每个帐户，请选择 " **+ （新建）**"，然后填写所需的信息。</span><span class="sxs-lookup"><span data-stu-id="cec71-329">For each account select **+ (New)**, and fill out the required information.</span></span> 
        
    5. <span data-ttu-id="cec71-330">若要使用户的电子邮件与当前的电子邮件相同，**用户名**字段应与用户现有的电子邮件地址完全相同。</span><span class="sxs-lookup"><span data-stu-id="cec71-330">To keep user's email the same as it is currently, the **User name** field should be exactly the same as the user's existing email address.</span></span> 
        
    6. <span data-ttu-id="cec71-331">在 "用户名" 旁边的下拉列表中，选择您的自定义域名称。</span><span class="sxs-lookup"><span data-stu-id="cec71-331">Next to User name, select your custom domain name from the drop-down list.</span></span>
        
    7. <span data-ttu-id="cec71-332">选择 "**创建** \> **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="cec71-332">Select **Create** \> **Close**.</span></span> 
        
6. <span data-ttu-id="cec71-333">在 DNS 托管提供程序中更新 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="cec71-333">Update DNS records at your DNS hosting provider</span></span>
    
    1. <span data-ttu-id="cec71-334">登录到您的 DNS 托管提供商的网站，并在[任何 dns 托管提供商处遵循适用于 Office 365 步骤的 CREATE DNS 记录](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="cec71-334">Sign in to your DNS hosting provider's website, and follow the [Create DNS records at any DNS hosting provider for Office 365 steps](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> <span data-ttu-id="cec71-335">**请进行以下异常：**</span><span class="sxs-lookup"><span data-stu-id="cec71-335">**Make the following exceptions:**</span></span>
    
        1. <span data-ttu-id="cec71-336">不要创建新的 MX 记录或更改现有的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="cec71-336">Do not create a new MX record or change your existing MX record.</span></span>
            
        2. <span data-ttu-id="cec71-337">如果您以前的电子邮件提供商已经有一个发件人策略框架（SPF）记录，而不是为 Exchange Online 创建新的 SPF （TXT）记录，则只需将 "include include spf.protection.outlook.com" 添加到当前的 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="cec71-337">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, just add "include:spf.protection.outlook.com" to the current TXT record.</span></span> <span data-ttu-id="cec71-338">例如，"v = spf1 mx 包括:adatum，其中包括 include spf.protection.outlook.com ~ all"。</span><span class="sxs-lookup"><span data-stu-id="cec71-338">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>
            
        3. <span data-ttu-id="cec71-339">如果您尚未安装 SPF 记录，请修改 Office 365 建议的项，以包含当前电子邮件提供程序的域以及 spf.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="cec71-339">If you don't have an SPF record yet, modify the one recommended by Office 365 to include the domain for your current email provider, plus spf.protection.outlook.com.</span></span> <span data-ttu-id="cec71-340">这将从这两个电子邮件系统中授权出传出邮件。</span><span class="sxs-lookup"><span data-stu-id="cec71-340">This authorizes outgoing messages from both email systems.</span></span>
            
7. <span data-ttu-id="cec71-341">在当前提供商处设置电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="cec71-341">Set up email forwarding at your current provider</span></span>
    
    1. <span data-ttu-id="cec71-342">在当前电子邮件提供商处，为您的用户电子邮件帐户设置到您的 onmicrosoft.com 域的转发：</span><span class="sxs-lookup"><span data-stu-id="cec71-342">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>
        
    2. <span data-ttu-id="cec71-343">用户 A 的邮箱应转发到 usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="cec71-343">User A's mailbox should forward to usera@yourcompany.onmicrosoft.com</span></span>
        
    3. <span data-ttu-id="cec71-344">用户 B 的邮箱应转发到 userb@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="cec71-344">User B's mailbox should forward to userb@yourcompany.onmicrosoft.com</span></span>
        
    4. <span data-ttu-id="cec71-345">完成此步骤时：</span><span class="sxs-lookup"><span data-stu-id="cec71-345">When you complete this step:</span></span>
        
    5. <span data-ttu-id="cec71-346">发送到 usera@yourcompany.com 和 userb@yourcompany.com 的所有邮件将在 Office 365 中提供。</span><span class="sxs-lookup"><span data-stu-id="cec71-346">All mail sent to usera@yourcompany.com and userb@yourcompany.com will be available in Office 365.</span></span>
    
    6. <span data-ttu-id="cec71-347">注意：</span><span class="sxs-lookup"><span data-stu-id="cec71-347">Notes:</span></span>
        
        - <span data-ttu-id="cec71-348">有关设置转发的确切步骤，请与当前的电子邮件提供商联系。</span><span class="sxs-lookup"><span data-stu-id="cec71-348">Contact your current email provider for the exact steps for setting up forwarding.</span></span>
            
        - <span data-ttu-id="cec71-349">您无需在当前电子邮件提供程序中保留邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="cec71-349">You don't need to keep a copy of messages at the current email provider.</span></span>
            
        - <span data-ttu-id="cec71-350">大多数提供程序将转发电子邮件，使发件人的答复地址保持不变，以便回复转到原始发件人。</span><span class="sxs-lookup"><span data-stu-id="cec71-350">Most providers forward email leaving the Reply-to address of the sender intact, so that replies go to the original sender.</span></span>
    
8. <span data-ttu-id="cec71-351">测试邮件流</span><span class="sxs-lookup"><span data-stu-id="cec71-351">Test mail flow</span></span>
    
    1. <span data-ttu-id="cec71-352">使用用户 A 的凭据登录到 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="cec71-352">Sign in to Outlook Web App using User A's credentials.</span></span>
        
    2. <span data-ttu-id="cec71-353">执行以下测试：</span><span class="sxs-lookup"><span data-stu-id="cec71-353">Perform the following tests:</span></span>
        
    3. <span data-ttu-id="cec71-354">测试本地 Microsoft 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cec71-354">Test local Microsoft email.</span></span> <span data-ttu-id="cec71-355">例如，向用户 B 发送电子邮件。应立即传递此电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cec71-355">For example, send an email to User B. This email should be delivered immediately.</span></span> <span data-ttu-id="cec71-356">在这种情况下，将不会将邮件路由到原始服务器上的用户 B 的邮箱，因为 Office 365 将该邮箱视为本地邮箱。</span><span class="sxs-lookup"><span data-stu-id="cec71-356">In this scenario, the message will not be routed to User B's mailbox on your original server because Office 365 sees the mailbox as being local.</span></span>
        
    4. <span data-ttu-id="cec71-357">将电子邮件测试给其他电子邮件系统上的人。</span><span class="sxs-lookup"><span data-stu-id="cec71-357">Test email to someone who's on the other email system.</span></span> <span data-ttu-id="cec71-358">例如，将电子邮件发送到用户 C。应将此电子邮件传递到原始邮件服务器上的用户 C 邮箱。</span><span class="sxs-lookup"><span data-stu-id="cec71-358">For example, send an email to User C. This email should be delivered to User C's mailbox on your original mail server.</span></span>
        
    5. <span data-ttu-id="cec71-359">从外部帐户或从其他电子邮件系统上的员工电子邮件帐户中，验证是否在其他电子邮件系统上正确设置了转发。</span><span class="sxs-lookup"><span data-stu-id="cec71-359">From an outside account, or from an employee's email account on the other email system, verify that forwarding is set up properly on the other email system.</span></span> <span data-ttu-id="cec71-360">例如，在用户 C 的原始服务器帐户或 Hotmail 帐户中，向用户发送一封电子邮件，并验证它是否到达用户 A 的 Office 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="cec71-360">For example, from User C's original server account or a Hotmail account, send User A an email and verify that it arrives in User A's Office 365 mailbox.</span></span>
        
9. <span data-ttu-id="cec71-361">移动邮箱内容</span><span class="sxs-lookup"><span data-stu-id="cec71-361">Move mailbox contents</span></span>
    
    1. <span data-ttu-id="cec71-362">由于只有两个用户需要移动，并且由于用户 A 和用户 B 都使用 Outlook，因此可以通过打开旧电子邮件移动电子邮件。PST 文件，然后复制邮件、日历项目、联系人等内容，如 Outlook 数据文件（.pst）中的 "导入 Outlook 项目" 中所示。</span><span class="sxs-lookup"><span data-stu-id="cec71-362">Since there are only two users to move, and since User A and User B are both using Outlook already, the email can be moved by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, etc. as shown in Import Outlook items from an Outlook Data File (.pst).</span></span> <span data-ttu-id="cec71-363">在 Office 365 邮箱中的正确位置进行组织后，可以从任何位置通过任何设备访问这些项目。</span><span class="sxs-lookup"><span data-stu-id="cec71-363">Once organized in the proper locations in the Office 365 mailbox, the items can all be accessed from any device, anywhere.</span></span>
        
    2. <span data-ttu-id="cec71-364">当涉及更多邮箱或员工尚未使用 Outlook 时，您可以使用 Exchange 管理中心提供的迁移工具。</span><span class="sxs-lookup"><span data-stu-id="cec71-364">When more mailboxes are involved, or if the employees are not already using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="cec71-365">若要开始，请转到 Exchange 管理中心，并按照将电子邮件从 IMAP 服务器迁移到 Exchange Online 邮箱中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="cec71-365">To get started, go to Exchange admin center and follow the directions in Migrate Email from an IMAP Server to Exchange Online Mailboxes.</span></span>
    
