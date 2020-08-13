---
title: 设置 SPF 以防欺骗
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何更新域名服务 (DNS) 记录，以便可以在 Office 365 中使用发件人策略框架 (SPF) 和自定义域。
ms.openlocfilehash: be773fe3265ac6cfd62d261196d4af1d14c91ef2
ms.sourcegitcommit: 9489aaf255f8bf165e6debc574e20548ad82e882
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2020
ms.locfileid: "46632135"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="ee68c-103">设置 SPF 以防欺骗</span><span class="sxs-lookup"><span data-stu-id="ee68c-103">Set up SPF to help prevent spoofing</span></span>

 <span data-ttu-id="ee68c-p101">**摘要：** 本文介绍了如何更新域名服务 (DNS) 记录，以便可以在 Office 365 中结合使用发件人策略框架 (SPF) 和自定义域。SPF 有助于验证从自定义域发送的出站电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p101">**Summary:** This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF) with your custom domain in Office 365. Using SPF helps to validate outbound email sent from your custom domain.</span></span>

<span data-ttu-id="ee68c-p102">若要使用自定义域，Office 365 要求你将发件人策略框架 (SPF) TXT 记录添加到 DNS 记录中，这样做有助于防止欺骗发生。SPF 标识允许哪些邮件服务器代表你发送邮件。一般来说，SPF 以及 DKIM、DMARC 和 Office 365 支持的其他技术可有助于防止欺骗和钓鱼发生。以 TXT 记录的形式添加 SPF 后，DNS 可使用此记录来确定哪些邮件服务器可以代表你的自定义域发送邮件。收件人邮件系统可以参阅 SPF TXT 记录，从而确定从你的自定义域发送的邮件是否来自已获授权的邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p102">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing. SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="ee68c-p103">例如，假设自定义域 contoso.com 使用 Office 365。你添加一个 SPF TXT 记录，将 Office 365 邮件服务器列为你的域的合法邮件服务器。当接收邮件服务器从 joe@contoso.com 收到一封邮件时，服务器会查找 contoso.com 的 SPF TXT 记录，并确定这封邮件是否有效。如果接收服务器确定这封邮件不是来自 SPF 记录中列出的 Office 365 邮件服务器，则可以选择将这封邮件作为垃圾邮件拒绝。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p103">For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="ee68c-p104">另外，如果自定义域没有 SPF TXT 记录，某些接收服务器可能会彻底拒绝邮件。这是因为接收服务器无法验证邮件是否来自已获授权的邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p104">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="ee68c-p105">如果你已经为 Office 365 设置了邮件，则表明已经将 Microsoft 的邮件服务器作为 SPF TXT 记录添加在 DNS 中。不过，在某些情况下，可能需要在 DNS 中更新 SPF TXT 记录。例如：</span><span class="sxs-lookup"><span data-stu-id="ee68c-p105">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:</span></span>

- <span data-ttu-id="ee68c-p106">以前，如果要使用 SharePoint Online，必须向自定义域添加不同的 SPF TXT 记录。现在，不再需要这样做。此更改应该会降低 SharePoint Online 通知邮件最终被转入垃圾电子邮件文件夹的风险。如果即将达到查找限制 10 次，且看到"超出了查找限制"和"跃点过多"的错误消息，请更新 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p106">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="ee68c-124">如果您拥有安装了 Office 365 和本地 Exchange 的混合环境。</span><span class="sxs-lookup"><span data-stu-id="ee68c-124">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="ee68c-125">打算设置 DKIM 和 DMARC（推荐）。</span><span class="sxs-lookup"><span data-stu-id="ee68c-125">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="updating-your-spf-txt-record-for-office-365"></a><span data-ttu-id="ee68c-126">为 Office 365 更新您的 SPF TXT 记录</span><span class="sxs-lookup"><span data-stu-id="ee68c-126">Updating your SPF TXT record for Office 365</span></span>

<span data-ttu-id="ee68c-p107">更新 DNS 中的 TXT 记录之前，需要收集一些信息，并确定记录的格式。这将有助于防止生成 DNS 错误。有关高级示例和支持的 SPF 语法的更详细地介绍，请参阅 [SPF 在 Office 365 中防止欺骗和钓鱼的工作原理](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p107">Before you update the TXT record in DNS, you need to gather some information and determine the format of the record. This will help prevent you from generating DNS errors. For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="ee68c-130">收集此信息：</span><span class="sxs-lookup"><span data-stu-id="ee68c-130">Gather this information:</span></span>

- <span data-ttu-id="ee68c-p108">自定义域的当前 SPF TXT 记录。有关说明，请参阅[收集创建 Office 365 DNS 记录所需的信息](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p108">The current SPF TXT record for your custom domain. For instructions, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span>

- <span data-ttu-id="ee68c-p109">所有本地邮件服务器的外部 IP 地址。例如，**131.107.2.200**。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p109">External IP addresses of all on-premises messaging servers. For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="ee68c-p110">用于需要包含在 SPF TXT 记录中的所有第三方域的域名。一些批量邮件提供商已设置供其客户使用的子域。例如，MailChimp 公司已经设置了 **servers.mcsv.net**。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p110">Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="ee68c-p111">确定要对 SPF TXT 记录使用的强制规则。我们建议使用 **-all**。有关其他语法选项的详细信息，请参阅 [Office 365 的 SPF TXT 记录语法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p111">Determine what enforcement rule you want to use for your SPF TXT record. We recommend **-all**. For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

### <a name="to-add-or-update-your-spf-txt-record"></a><span data-ttu-id="ee68c-141">添加或更新您的 SPF TXT 记录</span><span class="sxs-lookup"><span data-stu-id="ee68c-141">To add or update your SPF TXT record</span></span>

1. <span data-ttu-id="ee68c-142">请务必熟悉下表中的 SPF 语法。</span><span class="sxs-lookup"><span data-stu-id="ee68c-142">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ||<span data-ttu-id="ee68c-143">如果您正在使用...</span><span class="sxs-lookup"><span data-stu-id="ee68c-143">If you're using...</span></span>|<span data-ttu-id="ee68c-144">对于客户而言很常见？</span><span class="sxs-lookup"><span data-stu-id="ee68c-144">Common for customers?</span></span>|<span data-ttu-id="ee68c-145">添加以下内容...</span><span class="sxs-lookup"><span data-stu-id="ee68c-145">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="ee68c-146">1</span><span class="sxs-lookup"><span data-stu-id="ee68c-146">1</span></span>|<span data-ttu-id="ee68c-147">所有电子邮件系统（必需）</span><span class="sxs-lookup"><span data-stu-id="ee68c-147">Any email system (required)</span></span>|<span data-ttu-id="ee68c-p112">常见。所有 SPF TXT 记录都以此值开头</span><span class="sxs-lookup"><span data-stu-id="ee68c-p112">Common. All SPF TXT records start with this value</span></span>|<span data-ttu-id="ee68c-150">v=spf1</span><span class="sxs-lookup"><span data-stu-id="ee68c-150">v=spf1</span></span>|
   |<span data-ttu-id="ee68c-151">2</span><span class="sxs-lookup"><span data-stu-id="ee68c-151">2</span></span>|<span data-ttu-id="ee68c-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ee68c-152">Exchange Online</span></span>|<span data-ttu-id="ee68c-153">常见</span><span class="sxs-lookup"><span data-stu-id="ee68c-153">Common</span></span>|<span data-ttu-id="ee68c-154">include:spf.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ee68c-154">include:spf.protection.outlook.com</span></span>|
   |<span data-ttu-id="ee68c-155">3</span><span class="sxs-lookup"><span data-stu-id="ee68c-155">3</span></span>|<span data-ttu-id="ee68c-156">Exchange Online 专用</span><span class="sxs-lookup"><span data-stu-id="ee68c-156">Exchange Online dedicated only</span></span>|<span data-ttu-id="ee68c-157">不常见</span><span class="sxs-lookup"><span data-stu-id="ee68c-157">Not common</span></span>|<span data-ttu-id="ee68c-158">ip4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include:spf.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ee68c-158">ip4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include:spf.protection.outlook.com</span></span>|
   |<span data-ttu-id="ee68c-159">4</span><span class="sxs-lookup"><span data-stu-id="ee68c-159">4</span></span>|<span data-ttu-id="ee68c-160">仅 Office 365 Germany、Microsoft Cloud Germany</span><span class="sxs-lookup"><span data-stu-id="ee68c-160">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="ee68c-161">不常见</span><span class="sxs-lookup"><span data-stu-id="ee68c-161">Not common</span></span>|<span data-ttu-id="ee68c-162">include:spf.protection.outlook.de</span><span class="sxs-lookup"><span data-stu-id="ee68c-162">include:spf.protection.outlook.de</span></span>|
   |<span data-ttu-id="ee68c-163">5</span><span class="sxs-lookup"><span data-stu-id="ee68c-163">5</span></span>|<span data-ttu-id="ee68c-164">第三方电子邮件系统</span><span class="sxs-lookup"><span data-stu-id="ee68c-164">Third-party email system</span></span>|<span data-ttu-id="ee68c-165">不常见</span><span class="sxs-lookup"><span data-stu-id="ee68c-165">Not common</span></span>|<span data-ttu-id="ee68c-166">包括：\<domain name\></span><span class="sxs-lookup"><span data-stu-id="ee68c-166">include:\<domain name\></span></span>  <br/> <span data-ttu-id="ee68c-167">其中域名是第三方电子邮件系统的域名。</span><span class="sxs-lookup"><span data-stu-id="ee68c-167">Where domain name is the domain name of the third party email system.</span></span>|
   |<span data-ttu-id="ee68c-168">6</span><span class="sxs-lookup"><span data-stu-id="ee68c-168">6</span></span>|<span data-ttu-id="ee68c-p113">本地邮件系统。例如，Exchange Online Protection 和另一个邮件系统</span><span class="sxs-lookup"><span data-stu-id="ee68c-p113">On-premises mail system. For example, Exchange Online Protection plus another mail system</span></span>|<span data-ttu-id="ee68c-171">不常见</span><span class="sxs-lookup"><span data-stu-id="ee68c-171">Not common</span></span>| <span data-ttu-id="ee68c-172">为每个附加的邮件系统使用以下其中一个：</span><span class="sxs-lookup"><span data-stu-id="ee68c-172">Use one of these for each additional mail system:</span></span> <br> <span data-ttu-id="ee68c-173">ip4：\<_IP address_\></span><span class="sxs-lookup"><span data-stu-id="ee68c-173">ip4:\<_IP address_\></span></span>  <br/>  <span data-ttu-id="ee68c-174">ip6：\<_IP address_\></span><span class="sxs-lookup"><span data-stu-id="ee68c-174">ip6:\<_IP address_\></span></span>  <br/>  <span data-ttu-id="ee68c-175">包括：\<_domain name_\></span><span class="sxs-lookup"><span data-stu-id="ee68c-175">include:\<_domain name_\></span></span>  <br/>  <span data-ttu-id="ee68c-176">其中 \<_IP address_\> 的值是其他邮件系统的 IP 地址，\<_domain name_\> 是另一个代表您的域发送邮件的邮件系统的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ee68c-176">Where the value for \<_IP address_\> is the IP address of the other mail system and \<_domain name_\> is the domain name of the other mail system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="ee68c-177">7</span><span class="sxs-lookup"><span data-stu-id="ee68c-177">7</span></span>|<span data-ttu-id="ee68c-178">所有电子邮件系统（必需）</span><span class="sxs-lookup"><span data-stu-id="ee68c-178">Any email system (required)</span></span>|<span data-ttu-id="ee68c-p114">常见。所有 SPF TXT 记录都以此值结尾</span><span class="sxs-lookup"><span data-stu-id="ee68c-p114">Common. All SPF TXT records end with this value</span></span>|\<_enforcement rule_\>  <br/> <span data-ttu-id="ee68c-p115">这可以是多个值之一。我们建议您使用 **-all**。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p115">This can be one of several values. We recommend that you use **-all**.</span></span>|

2. <span data-ttu-id="ee68c-183">如果尚未创建 SPF TXT 记录，请使用该表中的语法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="ee68c-183">If you haven't already done so, form your SPF TXT record by using the syntax from the table:</span></span>

   <span data-ttu-id="ee68c-184">例如，如果完全托管在 Office 365 中（即没有本地邮件服务器），则 SPF TXT 记录包括行 1、2 和 7，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee68c-184">For example, if you are fully-hosted in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   `v=spf1 include:spf.protection.outlook.com -all`

   <span data-ttu-id="ee68c-185">这是最常见的 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="ee68c-185">This is the most common SPF TXT record.</span></span> <span data-ttu-id="ee68c-186">此记录几乎适用于每个人，无论你的 Microsoft 数据中心是位于美国还是欧洲（包括德国），亦或是位于其他地理位置。</span><span class="sxs-lookup"><span data-stu-id="ee68c-186">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="ee68c-p117">不过，如果已购买 Office 365 Germany（属于 Microsoft Cloud Germany），则应使用第 4 行（而不是第 2 行）的 include 语句。例如，如果完全托管在 Office 365 Germany中（即没有本地邮件服务器），则 SPF TXT 记录包括行 1、4 和 7，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee68c-p117">However, if you have purchased Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2. For example, if you are fully-hosted in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   `v=spf1 include:spf.protection.outlook.de -all`

   <span data-ttu-id="ee68c-189">如果你已在 Office 365 中进行部署并已为自定义域设置 SPF TXT 记录，而当前正在向 Office 365 Germany 迁移，则需要更新 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="ee68c-189">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="ee68c-190">为此，请将 include:spf.protection.outlook.com\*\*\*\* 更改为 include.spf.protection.outlook.de\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ee68c-190">To do this, change **include:spf.protection.outlook.com** to **include:spf.protection.outlook.de**.</span></span>

3. <span data-ttu-id="ee68c-191">一旦形成 SPF TXT 记录，则需要更新 DNS 中的记录。</span><span class="sxs-lookup"><span data-stu-id="ee68c-191">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="ee68c-192">只能为域使用一个 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="ee68c-192">You can only have one SPF TXT record for a domain.</span></span> <span data-ttu-id="ee68c-193">如果存在 SPF TXT 记录，则需要更新现有的记录，而不是添加新记录。</span><span class="sxs-lookup"><span data-stu-id="ee68c-193">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="ee68c-194">转到[为 Office 365 创建 DNS 记录](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)然后单击 DNS 主机的链接。</span><span class="sxs-lookup"><span data-stu-id="ee68c-194">Go to [Create DNS records for Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider), and then click the link for your DNS host.</span></span>

4. <span data-ttu-id="ee68c-195">测试 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="ee68c-195">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="ee68c-196">如何处理子域？</span><span class="sxs-lookup"><span data-stu-id="ee68c-196">How to handle subdomains?</span></span>

<span data-ttu-id="ee68c-197">请务必注意，您需要为每个子域创建单独的记录，因为子域不会继承其顶级域域的 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="ee68c-197">It is important to note that you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top level domain.</span></span>

<span data-ttu-id="ee68c-198">每个域和子域都需要一个额外的通配符SPF记录(`*.` )，以防止攻击者发送声称来自不存在的子域的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ee68c-198">An additional wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="ee68c-199">例如：</span><span class="sxs-lookup"><span data-stu-id="ee68c-199">For example:</span></span>

```console
*.subdomain.contoso.com. IN TXT "v=spf1 –all"
```

## <a name="more-information-about-spf"></a><span data-ttu-id="ee68c-200">有关 SPF 的详细信息</span><span class="sxs-lookup"><span data-stu-id="ee68c-200">More information about SPF</span></span>

<span data-ttu-id="ee68c-201">有关支持的 SPF 语法、欺骗、故障排除以及 Office 365 如何支持 SPF 的更加详细的探讨的高级示例，请参阅 [SPF 在 Office 365 中防止欺骗和钓鱼的工作原理](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。</span><span class="sxs-lookup"><span data-stu-id="ee68c-201">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="next-steps-after-you-set-up-spf-for-office-365"></a><span data-ttu-id="ee68c-202">后续步骤：为 Office 365 设置 SPF 之后</span><span class="sxs-lookup"><span data-stu-id="ee68c-202">Next steps: After you set up SPF for Office 365</span></span>

<span data-ttu-id="ee68c-p121">是否遇到与 SPF TXT 记录相关的问题？阅读[故障排除：Office 365 中 SPF 的最佳实践](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p121">Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

 <span data-ttu-id="ee68c-p122">SPF 旨在帮助防止欺骗，但还有 SPF 无法防止的欺骗技术。为了防止这些欺骗，在你设置 SPF 后，也应该为 Office 365 配置 DKIM 和 DMARC。请参阅 [使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)，了解入门知识。之后，请参阅[使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="ee68c-p122">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against. In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Office 365. To get started, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md). Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
