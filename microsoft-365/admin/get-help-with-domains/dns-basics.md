---
title: DNS 基础
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: 了解有关域及其关联的 DNS 记录，帮助你管理域。
ms.openlocfilehash: 1f5d49eb588a7c4245751360fa3309bf20496512
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658527"
---
# <a name="dns-basics"></a><span data-ttu-id="89472-103">DNS 基础</span><span class="sxs-lookup"><span data-stu-id="89472-103">DNS basics</span></span>

 <span data-ttu-id="89472-104">如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="89472-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="89472-105">域名（如 contoso.com）可通过全球范围的域注册机构和数据库托管。</span><span class="sxs-lookup"><span data-stu-id="89472-105">Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases.</span></span> <span data-ttu-id="89472-106">域名系统（DNS ）在可人工读取的计算机主机名与网络设备所用的 IP 地址之间进行映射。</span><span class="sxs-lookup"><span data-stu-id="89472-106">The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment.</span></span> <span data-ttu-id="89472-107">理解 DNS 和域注册机构的基础知识，有助于管理域。</span><span class="sxs-lookup"><span data-stu-id="89472-107">An understanding of DNS and domain registrar basics can help you manage domains.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="89472-108">域名（如 contoso.com）可通过全球范围的域注册机构和数据库托管。</span><span class="sxs-lookup"><span data-stu-id="89472-108">Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases.</span></span> <span data-ttu-id="89472-109">域名系统（DNS ）在可人工读取的计算机主机名与网络设备所用的 IP 地址之间进行映射。</span><span class="sxs-lookup"><span data-stu-id="89472-109">The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment.</span></span> <span data-ttu-id="89472-110">理解 DNS 和域注册机构的基础知识，有助于管理域。</span><span class="sxs-lookup"><span data-stu-id="89472-110">An understanding of DNS and domain registrar basics can help you manage domains.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="89472-111">域名（如 contoso.com）可通过全球范围的域注册机构和数据库托管。</span><span class="sxs-lookup"><span data-stu-id="89472-111">Domain names, like contoso.com, are managed by using a worldwide system of domain registrars and databases.</span></span> <span data-ttu-id="89472-112">域名系统（DNS ）在可人工读取的计算机主机名与网络设备所用的 IP 地址之间进行映射。</span><span class="sxs-lookup"><span data-stu-id="89472-112">The Domain Name System (DNS) provides a mapping between human-readable computer hostnames and the IP addresses used by networking equipment.</span></span> <span data-ttu-id="89472-113">理解 DNS 和域注册机构的基础知识，有助于管理员管理域。</span><span class="sxs-lookup"><span data-stu-id="89472-113">An understanding of DNS and domain registrar basics will help admins manage domains.</span></span>
  
::: moniker-end

## <a name="what-are-domain-names"></a><span data-ttu-id="89472-114">什么是域名？</span><span class="sxs-lookup"><span data-stu-id="89472-114">What are domain names?</span></span>

<span data-ttu-id="89472-115">域名用于 URL 和电子邮件地址，这些域名具有不同级别。</span><span class="sxs-lookup"><span data-stu-id="89472-115">Domain names are used in URLs and email addresses, and they have different levels.</span></span> <span data-ttu-id="89472-116">例如，mail.contoso.com 是一个具有以下三种级别的域名：</span><span class="sxs-lookup"><span data-stu-id="89472-116">For example, mail.contoso.com is a domain name with the following three levels:</span></span>
  
- <span data-ttu-id="89472-117">**.com** 是顶级域名</span><span class="sxs-lookup"><span data-stu-id="89472-117">**.com** is the top-level domain</span></span> 
    
- <span data-ttu-id="89472-118">**contoso** 是第二级域名</span><span class="sxs-lookup"><span data-stu-id="89472-118">**contoso** is the second-level domain</span></span> 
    
- <span data-ttu-id="89472-119">**mail** 是第三级域名</span><span class="sxs-lookup"><span data-stu-id="89472-119">**mail** is the third-level domain</span></span> 
    
<span data-ttu-id="89472-120">为什么使用第三级域名？</span><span class="sxs-lookup"><span data-stu-id="89472-120">Why use a third-level domain?</span></span> <span data-ttu-id="89472-121">可能希望针对市场营销或博客使用不同的域名。</span><span class="sxs-lookup"><span data-stu-id="89472-121">You might want to have different domain names for marketing or a blog.</span></span> <span data-ttu-id="89472-122">例如 blog.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="89472-122">For example, blog.contoso.com.</span></span> <span data-ttu-id="89472-123">通常添加二级域（如 contoso.com）以与 Microsoft 一起使用，但也可以根据需要使用第三级域。</span><span class="sxs-lookup"><span data-stu-id="89472-123">You typically add a second-level domain, like contoso.com, to use with Microsoft but you can also use third-level domains if you like.</span></span>
  
<span data-ttu-id="89472-124">在 [Microsoft 365 和 Office 365 平台服务说明](https://go.microsoft.com/fwlink/?LinkId=402693)中了解有关对于每种类型的服务你可以使用域执行的操作的更多信息。</span><span class="sxs-lookup"><span data-stu-id="89472-124">Learn more about what you can do with domains for each type of offering in the [Microsoft 365 and Office 365 platform service description](https://go.microsoft.com/fwlink/?LinkId=402693).</span></span>
  
## <a name="understand-dns-record-types"></a><span data-ttu-id="89472-125">了解 DNS 记录类型</span><span class="sxs-lookup"><span data-stu-id="89472-125">Understand DNS record types</span></span>

<span data-ttu-id="89472-126">域 DNS 主机上存储的 DNS 记录用于定向域的通信。</span><span class="sxs-lookup"><span data-stu-id="89472-126">DNS records stored at a DNS host for your domain are used to direct traffic for your domain.</span></span> <span data-ttu-id="89472-127">下表介绍了常用的 DNS 记录以及如何使用。</span><span class="sxs-lookup"><span data-stu-id="89472-127">The following table describes frequently used DNS records and how they're used.</span></span>
  
|<span data-ttu-id="89472-128">**NS（名称服务器）记录**</span><span class="sxs-lookup"><span data-stu-id="89472-128">**NS (nameserver) record**</span></span>|<span data-ttu-id="89472-129">**标识属于域的“权威名称服务器”的名称服务器。 当你更改域的名称服务器时，你将更改管理 DNS 记录的位置以及 DNS 系统查找邮件服务器等相关信息的位置。 Microsoft 有其自己的名称服务器，或者你也可以一直使用你的域已设置好的名称服务器。**</span><span class="sxs-lookup"><span data-stu-id="89472-129">**Identifies the name servers that are the "authoritative nameservers" for a domain. When you change the nameservers for your domain, you change where your DNS records are managed and where the DNS system looks for information about mail servers and so on. Microsoft has its own nameservers, or you may decide to keep using the nameservers that are already set up with your domain.**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89472-130">记录（地址记录）</span><span class="sxs-lookup"><span data-stu-id="89472-130">A record (address record)</span></span>  <br/> |<span data-ttu-id="89472-131">让一个域名和一个 IP 地址产生关联。</span><span class="sxs-lookup"><span data-stu-id="89472-131">Associates a domain name with an IP address.</span></span>  <br/> |
|<span data-ttu-id="89472-132">CNAME（别名或规范名称）记录</span><span class="sxs-lookup"><span data-stu-id="89472-132">CNAME (alias or canonical) record</span></span>  <br/> |<span data-ttu-id="89472-133">将一个域重定向到 DNS 系统中的另一个域。</span><span class="sxs-lookup"><span data-stu-id="89472-133">Redirects one domain to another in the DNS system.</span></span> <span data-ttu-id="89472-134">当名称服务器查找一个域，且找到一个 CNAME 记录时，它会用 CNAME 替换第一个域名，然后查找新的名称。</span><span class="sxs-lookup"><span data-stu-id="89472-134">When a name server looks up a domain and finds that it has a CNAME record, the server replaces the first domain name with the CNAME, and then looks up the new name.</span></span>  <br/> |
|<span data-ttu-id="89472-135">MX（邮件交换器）记录</span><span class="sxs-lookup"><span data-stu-id="89472-135">MX (mail exchanger) record</span></span>  <br/> |<span data-ttu-id="89472-136">指向应发送您的电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="89472-136">Points to where your email should be sent.</span></span> <span data-ttu-id="89472-137">它还具有一个优先级字段，以便您可以按优先顺序向不同服务器发送邮件。</span><span class="sxs-lookup"><span data-stu-id="89472-137">It also has a priority field so that you can send mail to different servers in a priority order.</span></span>  <br/> |
|<span data-ttu-id="89472-138">SPF（发送方策略框架）记录</span><span class="sxs-lookup"><span data-stu-id="89472-138">SPF (sender policy framework) record</span></span>  <br/> |<span data-ttu-id="89472-139">有助于防止电子邮件欺诈和网络钓鱼的 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="89472-139">A TXT record that helps prevent email spoofing and phishing.</span></span>  <br/> |
|<span data-ttu-id="89472-140">SRV（服务）记录</span><span class="sxs-lookup"><span data-stu-id="89472-140">SRV (service) record</span></span>  <br/> |<span data-ttu-id="89472-141">由 Skype for Business Online 和 Exchange Online 用来协调 Microsoft 服务间的信息流。</span><span class="sxs-lookup"><span data-stu-id="89472-141">Used by Skype for Business Online and Exchange Online to coordinate the flow of information between Microsoft services.</span></span> <span data-ttu-id="89472-142">例如在 Outlook Web App 中查看联机状态、使用 Skype for Business Online、Skype 或其他即使消息工具与其他公司的人员交流，SRV 记录必不可少。</span><span class="sxs-lookup"><span data-stu-id="89472-142">For example, the SRV records are required to see presence in Outlook Web App, and to use Skype for Business Online, Skype, or other instant messaging tools with people in other companies.</span></span>  <br/> |
|<span data-ttu-id="89472-143">TTL（生存时间）</span><span class="sxs-lookup"><span data-stu-id="89472-143">TTL (time-to-live)</span></span>  <br/> |<span data-ttu-id="89472-144">服务器查找更新版本之前名称服务器保留 DNS 记录的时间量。</span><span class="sxs-lookup"><span data-stu-id="89472-144">The amount of time that a nameserver keeps a DNS record before the server looks for an updated version.</span></span>  <br/> |
   
## <a name="how-does-dns-work"></a><span data-ttu-id="89472-145">DNS 如何工作？</span><span class="sxs-lookup"><span data-stu-id="89472-145">How does DNS work?</span></span>

<span data-ttu-id="89472-146">使用云服务（如 Microsoft 365）设置域包括更改或添加域的 [DNS 记录](dns-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="89472-146">Part of setting up your domain with a cloud service like Microsoft 365 includes changing or adding [DNS records](dns-basics.md) for the domain.</span></span> <span data-ttu-id="89472-147">由于 DNS、域名系统和域名在 Internet 中的工作方式，需要这些更改才能知道从何处发送或查找内容，例如电子邮件和网站。</span><span class="sxs-lookup"><span data-stu-id="89472-147">These changes are required because of how the Internet works with the DNS, Domain Name System, and domain names, to know where to send or find things, like email and websites.</span></span> 
  
<span data-ttu-id="89472-148">Internet 已设置为使用 DNS 或域名系统（允许我们使用熟悉的名称，如 contoso.com），可在标有难以记住的数字（称为 Internet 协议 (IP) 地址）的范围下查找实际的特定 Internet 位置。</span><span class="sxs-lookup"><span data-stu-id="89472-148">The Internet is set up to use DNS, or Domain Name System, which lets us use familiar names, like contoso.com, to locate specific Internet locations that are actually, under the covers, labeled with hard-to-remember numbers called IP (Internet Protocol) addresses.</span></span> <span data-ttu-id="89472-149">IP 地址类似于 70.42.241.42，因此，您可以更轻松地使用域名来识别电子邮件主机和网站等位置。</span><span class="sxs-lookup"><span data-stu-id="89472-149">IP addresses look something like 70.42.241.42, so you can see it's much easier to use a domain name to identify locations like email hosts and websites.</span></span>
  
<span data-ttu-id="89472-150">简而言之：DNS 记录告诉 Internet 在何处发送电子邮件（如 joe@contoso.com）或查找使用域名的网站（如 www.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="89472-150">So that's the short answer: DNS records tell the Internet where to send email (like joe@contoso.com) or find websites (like www.contoso.com) that use your domain name.</span></span> <span data-ttu-id="89472-151">存储合适的信息至正确的域 DNS 记录中时，DNS 系统正确路由，例如电子邮件能够到达 Microsoft 365，而不是其它地方。</span><span class="sxs-lookup"><span data-stu-id="89472-151">When you put the right information into the right DNS records for your domain, the DNS system routes everything correctly so your email, for example, arrives in Microsoft 365 instead of somewhere else.</span></span>
  
<span data-ttu-id="89472-152">域的 DNS 记录可以通过其他方式发挥作用。</span><span class="sxs-lookup"><span data-stu-id="89472-152">A domain's DNS records can be helpful in other ways, too.</span></span> <span data-ttu-id="89472-153">例如，Exchange 检查允许 Outlook 自动设置与合适 Exchange Server 的连接的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="89472-153">For example, Exchange checks a DNS record that lets Outlook automatically set up a connection to the right Exchange server.</span></span>
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a><span data-ttu-id="89472-154">DNS 记录帮助 Internet 将电子邮件发送到正确的位置</span><span class="sxs-lookup"><span data-stu-id="89472-154">DNS records help the Internet send email to the right place</span></span>

<span data-ttu-id="89472-155">如上所述，DNS 实际会路由 Internet 上的流量，将友好域名映射到难于记住的 IP 地址。 </span><span class="sxs-lookup"><span data-stu-id="89472-155">As you read above, DNS essentially directs traffic around the Internet, mapping friendly domain names to those hard-to-remember IP addresses.</span></span> <span data-ttu-id="89472-156">一个 DNS 记录（称为 MX 记录）专门用于向合适的主机发送电子邮件。 </span><span class="sxs-lookup"><span data-stu-id="89472-156">One DNS record, called the MX record, is specifically for sending email to the right host.</span></span>
  
<span data-ttu-id="89472-157">DNS 记录就是域信息的数据库。</span><span class="sxs-lookup"><span data-stu-id="89472-157">DNS records are like a database of information about your domain.</span></span> <span data-ttu-id="89472-158">记录及其数值保存在区域文件中，文件中含有各域记录及其数值的列表。</span><span class="sxs-lookup"><span data-stu-id="89472-158">The records and their values are kept in something called a zone file, which includes a list of each record for your domain and what its value is.</span></span> <span data-ttu-id="89472-159">域注册机构和其他 DNS 托管公司在网站上提供用户界面，因此可在域区域文件中编辑记录。</span><span class="sxs-lookup"><span data-stu-id="89472-159">Domain registrars and other DNS hosting companies provide a UI on their websites so you can edit the records in your domain's zone file.</span></span> <span data-ttu-id="89472-160">在那里可更新域的 MX 记录，发送电子邮件至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="89472-160">And that's where you update the MX record for your domain, to send email messages to Microsoft 365.</span></span>
  
 <span data-ttu-id="89472-161">*当将你的电子邮件更改为 Microsoft 365 时，在下一步中更新的域的 MX 记录，那么发送到该域的所有电子邮件都将开始传送到 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="89472-161">*When you change your email to Microsoft 365, by updating your domain's MX record in the next step, ALL email sent to that domain will start coming to Microsoft 365.*</span></span>  <span data-ttu-id="89472-162">如果其他用户的电子邮件使用你的域，必须为每个这些用户设置 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="89472-162">If other people use your domain for email, you must set up Microsoft 365 mailboxes for each of those people.</span></span> 
  
<span data-ttu-id="89472-163">听起来很复杂？ </span><span class="sxs-lookup"><span data-stu-id="89472-163">Sound complicated?</span></span> <span data-ttu-id="89472-164">可能是，我们将引导您完成 Microsoft 域设置中的每个步骤。</span><span class="sxs-lookup"><span data-stu-id="89472-164">Well, it can be, but we walk you through each step in the Microsoft domain setup.</span></span>
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a><span data-ttu-id="89472-165">DNS 告知 Internet 在哪里查找网站</span><span class="sxs-lookup"><span data-stu-id="89472-165">DNS tells the Internet where to look for websites too</span></span>

<span data-ttu-id="89472-166">输入网站地址（例如 www.contoso.com）时，Internet 首先会检查其中一个 DNS 服务器，查找用于（本例中）contoso.com 的名称服务器（NS）记录。</span><span class="sxs-lookup"><span data-stu-id="89472-166">When you type in a website address, for example, www.contoso.com, the Internet first checks with one of the DNS servers for something called a name server (NS) record for (in this case) contoso.com.</span></span> <span data-ttu-id="89472-167">NS 记录告诉 Internet 应在哪里查找含有所有此域的其他 DNS 记录的区域文件。</span><span class="sxs-lookup"><span data-stu-id="89472-167">The NS record tells the Internet where it should look for the zone file that has all the other DNS record values for that domain.</span></span> <span data-ttu-id="89472-168">存在大量相互连接的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="89472-168">There are lots of DNS servers, all connected to each other.</span></span> <span data-ttu-id="89472-169">服务器协同工作，跟踪所有已注册域名，域名必须唯一，而且是域区域文件所在的位置。</span><span class="sxs-lookup"><span data-stu-id="89472-169">The servers work together to keep track of all registered domain names, which have to be unique, and where the domain's zone files are.</span></span>
  
::: moniker range="o365-worldwide"

<span data-ttu-id="89472-170">假设 contoso.com 的 NS 记录为 “godaddy.com”。</span><span class="sxs-lookup"><span data-stu-id="89472-170">Let's say that the NS record for contoso.com says "godaddy.com."</span></span> <span data-ttu-id="89472-171">现在 Internet 知道，GoDaddy.com 是查找区域文件的位置，区域文件列出了用于 contoso.com 的所有其他 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="89472-171">Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com.</span></span> <span data-ttu-id="89472-172">这些 DNS 记录包含 MS 记录，显示发送 contoso.com 电子邮件和其他记录的位置。</span><span class="sxs-lookup"><span data-stu-id="89472-172">Those DNS records include the MX record that says where to send emails for contoso.com and other records.</span></span> <span data-ttu-id="89472-173">如果 MX 拥有一个数值 "send email to Microsoft 365"，表示所有发送至 contoso.com 电子邮件地址（如 joe@contoso.com）的所有电子邮件将被发送到那里。</span><span class="sxs-lookup"><span data-stu-id="89472-173">If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent.</span></span> <span data-ttu-id="89472-174">随后只要此位置有一个名为“joe”的收件箱，电子邮件就会被递送。</span><span class="sxs-lookup"><span data-stu-id="89472-174">Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="89472-175">假设 contoso.com 的 NS 记录为 “godaddy.com”。</span><span class="sxs-lookup"><span data-stu-id="89472-175">Let's say that the NS record for contoso.com says "godaddy.com."</span></span> <span data-ttu-id="89472-176">现在 Internet 知道，GoDaddy.com 是查找区域文件的位置，区域文件列出了用于 contoso.com 的所有其他 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="89472-176">Now the Internet knows that GoDaddy.com is where to look for the zone file listing all the other DNS records for contoso.com.</span></span> <span data-ttu-id="89472-177">这些 DNS 记录包含 MS 记录，显示发送 contoso.com 电子邮件和其他记录的位置。</span><span class="sxs-lookup"><span data-stu-id="89472-177">Those DNS records include the MX record that says where to send emails for contoso.com and other records.</span></span> <span data-ttu-id="89472-178">如果 MX 拥有一个数值 "send email to Microsoft 365"，表示所有发送至 contoso.com 电子邮件地址（如 joe@contoso.com）的所有电子邮件将被发送到那里。</span><span class="sxs-lookup"><span data-stu-id="89472-178">If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent.</span></span> <span data-ttu-id="89472-179">随后只要此位置有一个名为“joe”的收件箱，电子邮件就会被递送。</span><span class="sxs-lookup"><span data-stu-id="89472-179">Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="89472-180">假设 contoso.com 的 NS 记录为 “hichina.com”。</span><span class="sxs-lookup"><span data-stu-id="89472-180">Let's say that the NS record for contoso.com says "hichina.com."</span></span> <span data-ttu-id="89472-181">现在 Internet 知道，hichina.com 是查找区域文件的位置，区域文件列出了用于 contoso.com 的所有其他 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="89472-181">Now the Internet knows that hichina.com is where to look for the zone file listing all the other DNS records for contoso.com.</span></span> <span data-ttu-id="89472-182">这些 DNS 记录包含 MS 记录，显示发送 contoso.com 电子邮件和其他记录的位置。</span><span class="sxs-lookup"><span data-stu-id="89472-182">Those DNS records include the MX record that says where to send emails for contoso.com and other records.</span></span> <span data-ttu-id="89472-183">如果 MX 拥有一个数值 "send email to Microsoft 365"，表示所有发送至 contoso.com 电子邮件地址（如 joe@contoso.com）的所有电子邮件将被发送到那里。</span><span class="sxs-lookup"><span data-stu-id="89472-183">If the MX record has a value that says (but in technical terms) "send email to Microsoft 365," that's where all the email messages sent to a contoso.com email address (like joe@contoso.com) will be sent.</span></span> <span data-ttu-id="89472-184">随后只要此位置有一个名为“joe”的收件箱，电子邮件就会被递送。</span><span class="sxs-lookup"><span data-stu-id="89472-184">Then, as long as there's a mailbox called "joe" at that location, the email will be delivered.</span></span>

::: moniker-end

<span data-ttu-id="89472-185">如果在域设置步骤中设置域，必须输入以使用 Microsoft 365 工作的实际值为你列出。</span><span class="sxs-lookup"><span data-stu-id="89472-185">The actual values that you must enter for all of this to work with Microsoft 365 are listed for you when you're setting up your domain, in the domain setup steps.</span></span> <span data-ttu-id="89472-186">若要手动执行设置，可将值复制并粘贴到 DNS 主机上的正确 DNS 记录（MX 记录、CNAME 记录等）中，这可能是域注册机构，但不强制。</span><span class="sxs-lookup"><span data-stu-id="89472-186">If you're doing the set up manually, you copy and paste the values into the correct DNS records (MX record, CNAME records, and so on) at your DNS host, which might be your domain registrar but doesn't have to be.</span></span>
  
::: moniker range="o365-worldwide"

<span data-ttu-id="89472-187">为什么域区域文件可能是在域注册机构之外的其他位置？</span><span class="sxs-lookup"><span data-stu-id="89472-187">Why might your domain's zone file be somewhere besides at your domain registrar?</span></span> <span data-ttu-id="89472-188">嗯，你可能会在域注册机构（如 GoDaddy）中注册域名，但 DNS 记录可能被托管在其他位置，如独立 DNS 托管公司或 web 托管公司。</span><span class="sxs-lookup"><span data-stu-id="89472-188">Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company.</span></span> <span data-ttu-id="89472-189">域 NS 记录存储的信息，能够使 DNS 服务器知道在哪里查找。</span><span class="sxs-lookup"><span data-stu-id="89472-189">The NS records for your domain store that information so all the DNS servers know where to look.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="89472-190">为什么域区域文件可能是在域注册机构之外的其他位置？</span><span class="sxs-lookup"><span data-stu-id="89472-190">Why might your domain's zone file be somewhere besides at your domain registrar?</span></span> <span data-ttu-id="89472-191">嗯，你可能会在域注册机构（如 GoDaddy）中注册域名，但 DNS 记录可能被托管在其他位置，如独立 DNS 托管公司或 web 托管公司。</span><span class="sxs-lookup"><span data-stu-id="89472-191">Well, you might register your domain name at a domain registrar like GoDaddy, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company.</span></span> <span data-ttu-id="89472-192">域 NS 记录存储的信息，能够使 DNS 服务器知道在哪里查找。</span><span class="sxs-lookup"><span data-stu-id="89472-192">The NS records for your domain store that information so all the DNS servers know where to look.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="89472-193">为什么域区域文件可能是在域注册机构之外的其他位置？</span><span class="sxs-lookup"><span data-stu-id="89472-193">Why might your domain's zone file be somewhere besides at your domain registrar?</span></span> <span data-ttu-id="89472-194">嗯，你可能会在域注册机构（如 HiChina）中注册域名，但 DNS 记录可能被托管在其他位置，如独立 DNS 托管公司或 web 托管公司。</span><span class="sxs-lookup"><span data-stu-id="89472-194">Well, you might register your domain name at a domain registrar like HiChina, but your DNS records might be managed somewhere else, at a separate DNS hosting company or a web hosting company.</span></span> <span data-ttu-id="89472-195">域 NS 记录存储的信息，能够使 DNS 服务器知道在哪里查找。</span><span class="sxs-lookup"><span data-stu-id="89472-195">The NS records for your domain store that information so all the DNS servers know where to look.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a><span data-ttu-id="89472-196">为什么要在 Microsoft 365 中添加域？</span><span class="sxs-lookup"><span data-stu-id="89472-196">Why add a domain in Microsoft 365?</span></span>


<span data-ttu-id="89472-197">添加自定义域（如 fourthcoffee.com）至 Microsoft 365，让你能够使用更短、更熟悉的电子邮件和 userID 及服务。</span><span class="sxs-lookup"><span data-stu-id="89472-197">Adding a custom domain, like fourthcoffee.com, to Microsoft 365 lets you use a shorter, more familiar email address and userID with the service.</span></span> <span data-ttu-id="89472-198">注册 Microsoft 365 帐户时，将会[提供一个域供使用](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)，但它包含 "onmicrosoft.com"。</span><span class="sxs-lookup"><span data-stu-id="89472-198">You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Microsoft 365 account, but it includes "onmicrosoft.com."</span></span> <span data-ttu-id="89472-199">如果计划将 Microsoft 365 用于电子邮件，许多人更愿意添加组织或商业域。</span><span class="sxs-lookup"><span data-stu-id="89472-199">Many people prefer to add their organization or business domain if they plan to use Microsoft 365 for email.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="89472-200">如果只希望下载和使用 Microsoft 应用（如 Outlook 或 Word），则不需要添加域：[在 PC 或 Mac 上安装 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 即可。</span><span class="sxs-lookup"><span data-stu-id="89472-200">If you just want to download and use Microsoft apps, like Outlook or Word, you don't need to add a domain: [Install Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> 
  
<span data-ttu-id="89472-201">您可以在 Microsoft 365 中为您的电子邮件、公共网站和即时消息地址使用您的域名。</span><span class="sxs-lookup"><span data-stu-id="89472-201">You can use your domain name in Microsoft 365 with your email, public website, and instant messaging address.</span></span>
  
- <span data-ttu-id="89472-202">**电子邮件：** 域名可以让你自定义电子邮件，因此可以使用比附带账户的 [初始 onmicrosoft.com 电子邮件](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)更短、更易记的地址。</span><span class="sxs-lookup"><span data-stu-id="89472-202">**Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account.</span></span> <span data-ttu-id="89472-203">因此替代 joe@contoso.onmicrosoft.com，电子邮件地址（也是用于登录到 Microsoft 365 的工作帐户）可能是 joe@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="89472-203">So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Microsoft 365) could be joe@contoso.com.</span></span> 
    
- <span data-ttu-id="89472-204">**网站：** 如果你有包含 SharePoint Online 公共网站的 Microsoft 365 订阅（不能再购买），你的公共网站附带有如下初始地址：contoso-public.sharepoint.com。</span><span class="sxs-lookup"><span data-stu-id="89472-204">**Website:** If you have an Microsoft 365 subscription that includes a SharePoint Online Public Website (no longer available for purchase), your public website comes with an initial address like this: contoso-public.sharepoint.com.</span></span> <span data-ttu-id="89472-205">如果你为你的企业设置网站，则可以使用自定义域名将网站地址重命名为类似于 www.contoso.com 的地址。</span><span class="sxs-lookup"><span data-stu-id="89472-205">If you set up your website for your business, you can use a custom domain name to rename the website address to something like www.contoso.com.</span></span> 
    
- <span data-ttu-id="89472-206">**即时消息**：也可以自定义 Skype for Business Online 地址以使用你的域名，以便你组织中的人员可以在 Skype for Business Online 上使用更容易记住的较短地址（如 joe@contoso.com）相互联系。</span><span class="sxs-lookup"><span data-stu-id="89472-206">**Instant messaging:** Your Skype for Business Online address can also be customized to use your domain name, so people in your organization can connect with each other on Skype for Business Online by using a shorter, easier-to-remember address (like joe@contoso.com).</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a><span data-ttu-id="89472-207">为什么要在 Microsoft 365 中添加域？</span><span class="sxs-lookup"><span data-stu-id="89472-207">Why add a domain in Microsoft 365?</span></span>


<span data-ttu-id="89472-208">添加自定义域（如 fourthcoffee.com）至 Microsoft 365，让你能够使用更短、更熟悉的电子邮件和 userID 及服务。</span><span class="sxs-lookup"><span data-stu-id="89472-208">Adding a custom domain, like fourthcoffee.com, to Microsoft 365 lets you use a shorter, more familiar email address and userID with the service.</span></span> <span data-ttu-id="89472-209">注册 Microsoft 365 帐户时，将会[提供一个域供使用](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)，但它包含 "onmicrosoft.com"。</span><span class="sxs-lookup"><span data-stu-id="89472-209">You're [given a domain to use](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) when you sign up for a Microsoft 365 account, but it includes "onmicrosoft.com."</span></span> <span data-ttu-id="89472-210">如果计划将 Microsoft 365 用于电子邮件，许多人更愿意添加组织或商业域。</span><span class="sxs-lookup"><span data-stu-id="89472-210">Many people prefer to add their organization or business domain if they plan to use Microsoft 365 for email.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="89472-211">如果只希望下载和使用 Microsoft 365 应用（如 Outlook 或 Word），则不需要添加域：[在 PC 或 Mac 上安装 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 即可。</span><span class="sxs-lookup"><span data-stu-id="89472-211">If you just want to download and use Microsoft 365 apps, like Outlook or Word, you don't need to add a domain: [Install Office on your PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> 
  
<span data-ttu-id="89472-212">您可以在 Microsoft 365 中为您的电子邮件、公共网站和即时消息地址使用您的域名。</span><span class="sxs-lookup"><span data-stu-id="89472-212">You can use your domain name in Microsoft 365 with your email, public website, and instant messaging address.</span></span>
  
- <span data-ttu-id="89472-213">**电子邮件：** 域名可以让你自定义电子邮件，因此可以使用比附带账户的 [初始 onmicrosoft.com 电子邮件](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)更短、更易记的地址。</span><span class="sxs-lookup"><span data-stu-id="89472-213">**Email:** Your domain name lets you customize your email, so you can use a shorter, easier-to-remember address than [the initial onmicrosoft.com email address](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) that comes with your account.</span></span> <span data-ttu-id="89472-214">因此替代 joe@contoso.onmicrosoft.com，电子邮件地址（也是用于登录到 Microsoft 365 的工作帐户）可能是 joe@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="89472-214">So instead of joe@contoso.onmicrosoft.com, the email address (which is also the work account that you use to sign in to Microsoft 365) could be joe@contoso.com.</span></span> 
    
- <span data-ttu-id="89472-215">**网站：** 如果你有包含 SharePoint Online 公共网站的订阅（不能再购买），你的公共网站附带有如下初始地址：contoso-public.sharepoint.com。</span><span class="sxs-lookup"><span data-stu-id="89472-215">**Website:** If you have a subscription that includes a SharePoint Online Public Website (no longer available for purchase), your public website comes with an initial address like this: contoso-public.sharepoint.com.</span></span> <span data-ttu-id="89472-216">如果你为你的企业设置网站，则可以使用自定义域名将网站地址重命名为类似于 www.contoso.com 的地址。</span><span class="sxs-lookup"><span data-stu-id="89472-216">If you set up your website for your business, you can use a custom domain name to rename the website address to something like www.contoso.com.</span></span> 
    
- <span data-ttu-id="89472-217">**即时消息**：也可以自定义 Skype for Business Online 地址以使用你的域名，以便你组织中的人员可以在 Skype for Business Online 上使用更容易记住的较短地址（如 joe@contoso.com）相互联系。</span><span class="sxs-lookup"><span data-stu-id="89472-217">**Instant messaging:** Your Skype for Business Online address can also be customized to use your domain name, so people in your organization can connect with each other on Skype for Business Online by using a shorter, easier-to-remember address (like joe@contoso.com).</span></span> 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a><span data-ttu-id="89472-218">Microsoft 365 所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="89472-218">The DNS records required for Microsoft 365</span></span>

<span data-ttu-id="89472-219">对于 Microsoft 365，需要几个 DNS 记录才能使用你的域。</span><span class="sxs-lookup"><span data-stu-id="89472-219">There are a number of DNS records required for Microsoft 365 to work with your domain.</span></span> <span data-ttu-id="89472-220">除了设置您的域的 MX 记录来将电子邮件发送到 Microsoft 365，还有一些记录可以帮助您完成以下任务：确保 Outlook 可以自动连接到正确的 Exchange 服务器，设置即时消息，帮助防止垃圾电子邮件等。</span><span class="sxs-lookup"><span data-stu-id="89472-220">In addition to setting up your domain's MX record so email will be sent to Microsoft 365, there are records to help with tasks like making sure Outlook can automatically connect to the right Exchange server, setting up instant messaging, and helping to prevent spam email.</span></span>
  
<span data-ttu-id="89472-221">可[查找值列表](information-for-dns-records.md)来设置域。</span><span class="sxs-lookup"><span data-stu-id="89472-221">You can [find a list of values](information-for-dns-records.md) to set up your domain.</span></span> <span data-ttu-id="89472-222">它们包含在 Microsoft 365 管理中心中。</span><span class="sxs-lookup"><span data-stu-id="89472-222">They're included right in the Microsoft 365 admin center.</span></span> 
  
<span data-ttu-id="89472-223">或者，如果您正在筹划部署，您可能希望查看 Microsoft 365 所需的所有 DNS 记录的列表、其函数和示例值。</span><span class="sxs-lookup"><span data-stu-id="89472-223">Or, if you're planning a deployment, you may want to review a list of all the DNS records required for Microsoft 365, what their function is, and example values.</span></span> <span data-ttu-id="89472-224">查看 “[Microsoft 365 的外部域名系统记录](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)”。</span><span class="sxs-lookup"><span data-stu-id="89472-224">Check out [External Domain Name System records for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span>
  
## <a name="how-can-i-learn-more"></a><span data-ttu-id="89472-225">如何了解更多信息？</span><span class="sxs-lookup"><span data-stu-id="89472-225">How can I learn more?</span></span>

<span data-ttu-id="89472-226">请查看以下内容之一：</span><span class="sxs-lookup"><span data-stu-id="89472-226">Check out one of the following:</span></span> 
  
- <span data-ttu-id="89472-227">不确定域的注册位置？</span><span class="sxs-lookup"><span data-stu-id="89472-227">Not sure where your domain is registered?</span></span> [<span data-ttu-id="89472-228">获取查找域名注册机构的帮助。</span><span class="sxs-lookup"><span data-stu-id="89472-228">Get help finding your domain registrar.</span></span>](find-your-domain-registrar.md)
- <span data-ttu-id="89472-229">了解[为什么您必须完成向导步骤操作](../setup/add-domain.md)，然后才能将您的域与 Microsoft 365 配合使用。</span><span class="sxs-lookup"><span data-stu-id="89472-229">Find out [why you have to complete the wizard steps](../setup/add-domain.md) before you can use your domain with Microsoft 365.</span></span>
