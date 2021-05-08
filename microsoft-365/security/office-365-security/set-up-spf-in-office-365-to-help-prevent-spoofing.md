---
title: 设置 SPF 以防欺骗
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何更新域名服务 (DNS) 记录，以便可以在 Office 365 中使用发件人策略框架 (SPF) 和自定义域。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d200c4cf17a3d42ddafca301fecbf18c249ac37
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245680"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="a310a-103">设置 SPF 以防欺骗</span><span class="sxs-lookup"><span data-stu-id="a310a-103">Set up SPF to help prevent spoofing</span></span>

- [<span data-ttu-id="a310a-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="a310a-104">Prerequisites</span></span>](#prerequisites)
- [<span data-ttu-id="a310a-105">创建或更新你的 SPF TXT 记录</span><span class="sxs-lookup"><span data-stu-id="a310a-105">Create or update your SPF TXT record</span></span>](#create-or-update-your-spf-txt-record)
- [<span data-ttu-id="a310a-106">如何处理子域？</span><span class="sxs-lookup"><span data-stu-id="a310a-106">How to handle subdomains?</span></span>](#how-to-handle-subdomains)
- [<span data-ttu-id="a310a-107">SPF 疑难解答</span><span class="sxs-lookup"><span data-stu-id="a310a-107">Troubleshooting SPF</span></span>](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

<span data-ttu-id="a310a-108">本文介绍了如何更新域名服务 (DNS) 记录，以便可以在 Office 365 中结合使用发件人策略框架 (SPF) 电子邮件身份验证和自定义域。</span><span class="sxs-lookup"><span data-stu-id="a310a-108">This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF)  email authentication with your custom domain in Office 365.</span></span>

<span data-ttu-id="a310a-109">SPF 帮助 *验证* 从你的自定义域发送的出站电子邮件（是否来自所其显示地址）。</span><span class="sxs-lookup"><span data-stu-id="a310a-109">SPF helps *validate* outbound email sent from your custom domain (is coming from who it says it is).</span></span> <span data-ttu-id="a310a-110">这是建立完全推荐的 SPF、[DKIM](use-dkim-to-validate-outbound-email.md) 和 [DMARC](use-dmarc-to-validate-email.md) 电子邮件身份验证方法的第一步。</span><span class="sxs-lookup"><span data-stu-id="a310a-110">It's a first step in setting up the full recommended email authentication methods of SPF, [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a310a-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="a310a-111">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a310a-112">如果你是 **小型企业**，或是不熟悉 IP 地址或 DNS 配置，请致电你的Internet 域注册机构（例如，</span><span class="sxs-lookup"><span data-stu-id="a310a-112">If you are a **small business**, or are unfamiliar with IP addresses or DNS configuration, call your Internet domain registrar (ex.</span></span> <span data-ttu-id="a310a-113">GoDaddy、Bluehost、web.com）& 请求有关 *SPF 的 DNS 配置*（以及任何其他电子邮件身份验证方法）的帮助。</span><span class="sxs-lookup"><span data-stu-id="a310a-113">GoDaddy, Bluehost, web.com) & ask for help with *DNS configuration of SPF* (and any other email authentication method).</span></span> <p> <span data-ttu-id="a310a-114">**如果你不使用自定义 URL**（且用于 Office 365 的 URL 以 **onmicrosoft.com** 结尾），则系统已在 Office 365 服务中为你设置了 SPF。</span><span class="sxs-lookup"><span data-stu-id="a310a-114">**If you don't use a custom URL** (and the URL used for Office 365 ends in **onmicrosoft.com**), SPF has already been set up for you in the Office 365 service.</span></span>

<span data-ttu-id="a310a-115">让我们开始吧。</span><span class="sxs-lookup"><span data-stu-id="a310a-115">Let's get started.</span></span>

<span data-ttu-id="a310a-116">Office 365 的 SPF TXT 记录将在任何自定义域或子域的外部 DNS 中创建。</span><span class="sxs-lookup"><span data-stu-id="a310a-116">The SPF TXT record for Office 365 will be made in external DNS for any custom domains or subdomains.</span></span> <span data-ttu-id="a310a-117">需要一些信息以创建记录。</span><span class="sxs-lookup"><span data-stu-id="a310a-117">You need some information to make the record.</span></span> <span data-ttu-id="a310a-118">收集此信息：</span><span class="sxs-lookup"><span data-stu-id="a310a-118">Gather this information:</span></span>

- <span data-ttu-id="a310a-119">自定义域的 SPF TXT记录（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="a310a-119">The SPF TXT record for your custom domain, if one exists.</span></span> <span data-ttu-id="a310a-120">有关说明，请参阅[收集创建 Office 365 DNS 记录所需的信息](../../admin/get-help-with-domains/information-for-dns-records.md)。</span><span class="sxs-lookup"><span data-stu-id="a310a-120">For instructions, see [Gather the information you need to create Office 365 DNS records](../../admin/get-help-with-domains/information-for-dns-records.md).</span></span>

- <span data-ttu-id="a310a-121">转到消息服务器并查找外部 IP 地址（需要来自所有本地消息服务器）。</span><span class="sxs-lookup"><span data-stu-id="a310a-121">Go to your messaging server(s) and find out the External IP addresses (needed from all on-premises messaging servers).</span></span> <span data-ttu-id="a310a-122">例如，**131.107.2.200**。</span><span class="sxs-lookup"><span data-stu-id="a310a-122">For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="a310a-p106">用于需要包含在 SPF TXT 记录中的所有第三方域的域名。一些批量邮件提供商已设置供其客户使用的子域。例如，MailChimp 公司已经设置了 **servers.mcsv.net**。</span><span class="sxs-lookup"><span data-stu-id="a310a-p106">Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="a310a-126">确定要对 SPF TXT 记录使用的强制规则。</span><span class="sxs-lookup"><span data-stu-id="a310a-126">Figure out what enforcement rule you want to use for your SPF TXT record.</span></span> <span data-ttu-id="a310a-127">建议使用 **-all** 规则。</span><span class="sxs-lookup"><span data-stu-id="a310a-127">The **-all** rule is recommended.</span></span> <span data-ttu-id="a310a-128">有关其他语法选项的详细信息，请参阅 [Office 365 的 SPF TXT 记录语法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)。</span><span class="sxs-lookup"><span data-stu-id="a310a-128">For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a310a-129">若要使用自定义域，Office 365 要求你将发件人策略框架 (SPF) TXT 记录添加到 DNS 记录中，这样做有助于防止欺骗发生。</span><span class="sxs-lookup"><span data-stu-id="a310a-129">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing.</span></span>

## <a name="create-or-update-your-spf-txt-record"></a><span data-ttu-id="a310a-130">创建或更新你的 SPF TXT 记录</span><span class="sxs-lookup"><span data-stu-id="a310a-130">Create or update your SPF TXT record</span></span>

1. <span data-ttu-id="a310a-131">请务必熟悉下表中的 SPF 语法。</span><span class="sxs-lookup"><span data-stu-id="a310a-131">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ****

   |<span data-ttu-id="a310a-132">元素</span><span class="sxs-lookup"><span data-stu-id="a310a-132">Element</span></span>|<span data-ttu-id="a310a-133">如果您正在使用...</span><span class="sxs-lookup"><span data-stu-id="a310a-133">If you're using...</span></span>|<span data-ttu-id="a310a-134">对于客户而言很常见？</span><span class="sxs-lookup"><span data-stu-id="a310a-134">Common for customers?</span></span>|<span data-ttu-id="a310a-135">添加以下内容...</span><span class="sxs-lookup"><span data-stu-id="a310a-135">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="a310a-136">1</span><span class="sxs-lookup"><span data-stu-id="a310a-136">1</span></span>|<span data-ttu-id="a310a-137">所有电子邮件系统（必需）</span><span class="sxs-lookup"><span data-stu-id="a310a-137">Any email system (required)</span></span>|<span data-ttu-id="a310a-p108">常见。所有 SPF TXT 记录都以此值开头</span><span class="sxs-lookup"><span data-stu-id="a310a-p108">Common. All SPF TXT records start with this value</span></span>|`v=spf1`|
   |<span data-ttu-id="a310a-140">2</span><span class="sxs-lookup"><span data-stu-id="a310a-140">2</span></span>|<span data-ttu-id="a310a-141">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a310a-141">Exchange Online</span></span>|<span data-ttu-id="a310a-142">常见</span><span class="sxs-lookup"><span data-stu-id="a310a-142">Common</span></span>|`include:spf.protection.outlook.com`|
   |<span data-ttu-id="a310a-143">3</span><span class="sxs-lookup"><span data-stu-id="a310a-143">3</span></span>|<span data-ttu-id="a310a-144">Exchange Online 专用</span><span class="sxs-lookup"><span data-stu-id="a310a-144">Exchange Online dedicated only</span></span>|<span data-ttu-id="a310a-145">不常见</span><span class="sxs-lookup"><span data-stu-id="a310a-145">Not common</span></span>|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |<span data-ttu-id="a310a-146">4</span><span class="sxs-lookup"><span data-stu-id="a310a-146">4</span></span>|<span data-ttu-id="a310a-147">仅 Office 365 Germany、Microsoft Cloud Germany</span><span class="sxs-lookup"><span data-stu-id="a310a-147">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="a310a-148">不常见</span><span class="sxs-lookup"><span data-stu-id="a310a-148">Not common</span></span>|`include:spf.protection.outlook.de`|
   |<span data-ttu-id="a310a-149">5</span><span class="sxs-lookup"><span data-stu-id="a310a-149">5</span></span>|<span data-ttu-id="a310a-150">第三方电子邮件系统</span><span class="sxs-lookup"><span data-stu-id="a310a-150">Third-party email system</span></span>|<span data-ttu-id="a310a-151">不常见</span><span class="sxs-lookup"><span data-stu-id="a310a-151">Not common</span></span>|`include:<domain_name>` <p> <span data-ttu-id="a310a-152">\<domain_name\> 是第三方电子邮件系统的域。</span><span class="sxs-lookup"><span data-stu-id="a310a-152">\<domain_name\> is the domain of the third-party email system.</span></span>|
   |<span data-ttu-id="a310a-153">6</span><span class="sxs-lookup"><span data-stu-id="a310a-153">6</span></span>|<span data-ttu-id="a310a-p109">本地电子邮件系统。例如，Exchange Online Protection 和另一个电子邮件系统</span><span class="sxs-lookup"><span data-stu-id="a310a-p109">On-premises email system. For example, Exchange Online Protection plus another email system</span></span>|<span data-ttu-id="a310a-156">不常见</span><span class="sxs-lookup"><span data-stu-id="a310a-156">Not common</span></span>|<span data-ttu-id="a310a-157">为每个附加的邮件系统使用以下其中一个：</span><span class="sxs-lookup"><span data-stu-id="a310a-157">Use one of these for each additional mail system:</span></span> <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> <span data-ttu-id="a310a-158">\<IP_address\> 和 \<domain_name\> 是代表你的域发送邮件的其他电子邮件系统的 IP 地址和域。</span><span class="sxs-lookup"><span data-stu-id="a310a-158">\<IP_address\> and \<domain_name\> are the IP address and domain of the other email system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="a310a-159">7</span><span class="sxs-lookup"><span data-stu-id="a310a-159">7</span></span>|<span data-ttu-id="a310a-160">所有电子邮件系统（必需）</span><span class="sxs-lookup"><span data-stu-id="a310a-160">Any email system (required)</span></span>|<span data-ttu-id="a310a-p110">常见。所有 SPF TXT 记录都以此值结尾</span><span class="sxs-lookup"><span data-stu-id="a310a-p110">Common. All SPF TXT records end with this value</span></span>|`<enforcement rule>` <p> <span data-ttu-id="a310a-163">这可以是多个值之一。</span><span class="sxs-lookup"><span data-stu-id="a310a-163">This can be one of several values.</span></span> <span data-ttu-id="a310a-164">建议值 `-all`。</span><span class="sxs-lookup"><span data-stu-id="a310a-164">We recommend the value `-all`.</span></span>|
   |

2. <span data-ttu-id="a310a-165">如果尚未创建 SPF TXT 记录，请使用该表中的语法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a310a-165">If you haven't already done so, form your SPF TXT record by using the syntax from the table.</span></span>

   <span data-ttu-id="a310a-166">例如，如果完全托管在 Office 365 中（即没有本地邮件服务器），则 SPF TXT 记录包括行 1、2 和 7，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a310a-166">For example, if you are hosted entirely in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   <span data-ttu-id="a310a-167">**上述示例是最常见的 SPF TXT 记录**。</span><span class="sxs-lookup"><span data-stu-id="a310a-167">**The example above is the most common SPF TXT record**.</span></span> <span data-ttu-id="a310a-168">此记录几乎适用于每个人，无论你的 Microsoft 数据中心是位于美国还是欧洲（包括德国），亦或是位于其他地理位置。</span><span class="sxs-lookup"><span data-stu-id="a310a-168">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="a310a-p113">不过，如果购买了 Office 365 Germany（属于 Microsoft 云德国），则应使用第 4 行（而不是第 2 行）的 include 语句。例如，如果完全托管在 Office 365 Germany 中（即没有本地邮件服务器），则 SPF TXT 记录包括行 1、4 和 7，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a310a-p113">However, if you bought Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2. For example, if you are hosted entirely in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   <span data-ttu-id="a310a-171">如果你已在 Office 365 中进行部署并已为自定义域设置 SPF TXT 记录，而当前正在向 Office 365 Germany 迁移，则需要更新 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="a310a-171">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="a310a-172">若要执行此操作，请将 `include:spf.protection.outlook.com` 更改为 `include:spf.protection.outlook.de`。</span><span class="sxs-lookup"><span data-stu-id="a310a-172">To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.</span></span>

3. <span data-ttu-id="a310a-173">一旦形成 SPF TXT 记录，则需要更新 DNS 中的记录。</span><span class="sxs-lookup"><span data-stu-id="a310a-173">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="a310a-174">**只能为域使用一个 SPF TXT 记录。**</span><span class="sxs-lookup"><span data-stu-id="a310a-174">**You can only have one SPF TXT record for a domain.**</span></span> <span data-ttu-id="a310a-175">如果存在 SPF TXT 记录，则需要更新现有的记录，而不是添加新记录。</span><span class="sxs-lookup"><span data-stu-id="a310a-175">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="a310a-176">转到[为 Office 365 创建 DNS 记录](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)然后选择 DNS 主机的链接。</span><span class="sxs-lookup"><span data-stu-id="a310a-176">Go to [Create DNS records for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), and then select the link for your DNS host.</span></span>

4. <span data-ttu-id="a310a-177">测试 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="a310a-177">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="a310a-178">如何处理子域？</span><span class="sxs-lookup"><span data-stu-id="a310a-178">How to handle subdomains?</span></span>

<span data-ttu-id="a310a-179">请务必注意，*你需要为每个子域创建单独的记录，因为子域不会继承其顶级域的 SPF 记录*。</span><span class="sxs-lookup"><span data-stu-id="a310a-179">It's important to note that *you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top-level domain*.</span></span>

<span data-ttu-id="a310a-180">每个域和子域都需要的通配符 SPF 记录(`*.` )，以防止攻击者发送声称来自不存在的子域的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a310a-180">A wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="a310a-181">例如：</span><span class="sxs-lookup"><span data-stu-id="a310a-181">For example:</span></span>

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a><span data-ttu-id="a310a-182">SPF 疑难解答</span><span class="sxs-lookup"><span data-stu-id="a310a-182">Troubleshooting SPF</span></span>

<span data-ttu-id="a310a-p117">是否遇到与 SPF TXT 记录相关的问题？阅读[故障排除：Office 365 中 SPF 的最佳实践](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="a310a-p117">Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>


## <a name="what-does-spf-email-authentication-actually-do"></a><span data-ttu-id="a310a-185">SPF 电子邮件身份验证实际上做什么？</span><span class="sxs-lookup"><span data-stu-id="a310a-185">What does SPF email authentication actually do?</span></span>

<span data-ttu-id="a310a-p118">SPF 标识允许哪些邮件服务器代表你发送邮件。一般来说，SPF 以及 DKIM、DMARC 和 Office 365 支持的其他技术可有助于防止欺骗和钓鱼发生。以 TXT 记录的形式添加 SPF 后，DNS 可使用此记录来确定哪些邮件服务器可以代表你的自定义域发送邮件。收件人邮件系统可以参阅 SPF TXT 记录，从而确定从你的自定义域发送的邮件是否来自已获授权的邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="a310a-p118">SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="a310a-p119">例如，假设自定义域 contoso.com 使用 Office 365。你添加一个 SPF TXT 记录，将 Office 365 邮件服务器列为你的域的合法邮件服务器。当接收邮件服务器从 joe@contoso.com 收到一封邮件时，服务器会查找 contoso.com 的 SPF TXT 记录，并确定这封邮件是否有效。如果接收服务器确定这封邮件不是来自 SPF 记录中列出的 Office 365 邮件服务器，则可以选择将这封邮件作为垃圾邮件拒绝。</span><span class="sxs-lookup"><span data-stu-id="a310a-p119">For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="a310a-p120">另外，如果自定义域没有 SPF TXT 记录，某些接收服务器可能会彻底拒绝邮件。这是因为接收服务器无法验证邮件是否来自已获授权的邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="a310a-p120">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="a310a-p121">如果你已经为 Office 365 设置了邮件，则表明已经将 Microsoft 的邮件服务器作为 SPF TXT 记录添加在 DNS 中。不过，在某些情况下，可能需要在 DNS 中更新 SPF TXT 记录。例如：</span><span class="sxs-lookup"><span data-stu-id="a310a-p121">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:</span></span>

- <span data-ttu-id="a310a-p122">以前，如果要使用 SharePoint Online，必须向自定义域添加不同的 SPF TXT 记录。现在，不再需要这样做。此更改应该会降低 SharePoint Online 通知邮件最终被转入垃圾电子邮件文件夹的风险。如果即将达到查找限制 10 次，且看到"超出了查找限制"和"跃点过多"的错误消息，请更新 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="a310a-p122">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="a310a-203">如果您拥有安装了 Office 365 和本地 Exchange 的混合环境。</span><span class="sxs-lookup"><span data-stu-id="a310a-203">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="a310a-204">打算设置 DKIM 和 DMARC（推荐）。</span><span class="sxs-lookup"><span data-stu-id="a310a-204">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="more-information-about-spf"></a><span data-ttu-id="a310a-205">有关 SPF 的详细信息</span><span class="sxs-lookup"><span data-stu-id="a310a-205">More information about SPF</span></span>

<span data-ttu-id="a310a-206">有关支持的 SPF 语法、欺骗、故障排除以及 Office 365 如何支持 SPF 的更加详细的探讨的高级示例，请参阅 [SPF 在 Office 365 中防止欺骗和钓鱼的工作原理](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。</span><span class="sxs-lookup"><span data-stu-id="a310a-206">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="next-steps-dkim-and-dmarc"></a><span data-ttu-id="a310a-207">后续步骤：DKIM 和 DMARC</span><span class="sxs-lookup"><span data-stu-id="a310a-207">Next Steps: DKIM and DMARC</span></span>

 <span data-ttu-id="a310a-208">SPF 旨在帮助防骗，但有些骗术是 SPF 所无法防范的。</span><span class="sxs-lookup"><span data-stu-id="a310a-208">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF can't protect against.</span></span> <span data-ttu-id="a310a-209">为了防范这些诈骗技术，设置 SPF 后，就应该为 Office 365 配置 DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="a310a-209">To defend against these, once you've set up SPF, you should configure DKIM and DMARC for Office 365.</span></span>

<span data-ttu-id="a310a-210">[DKIM](use-dkim-to-validate-outbound-email.md) 电子邮件身份验证的目标是证明邮件的内容没有被篡改。</span><span class="sxs-lookup"><span data-stu-id="a310a-210">[DKIM](use-dkim-to-validate-outbound-email.md) email authentication's goal is to prove the contents of the mail haven't been tampered with.</span></span>

<span data-ttu-id="a310a-211">[DMARC](use-dmarc-to-validate-email.md) 电子邮件身份验证的目标是确保 SPF 和 DKIM 信息与发件人地址匹配。</span><span class="sxs-lookup"><span data-stu-id="a310a-211">[DMARC](use-dmarc-to-validate-email.md) email authentication's goal is to make sure that SPF and DKIM information matches the From address.</span></span>

 <span data-ttu-id="a310a-212">有关支持的 SPF 语法的更加详细的探讨的高级示例，请参阅 [SPF 在 Office 365 中防止欺骗和钓鱼的工作原理](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。</span><span class="sxs-lookup"><span data-stu-id="a310a-212">For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="a310a-213">*如对此文档有反馈，请在“反馈”下选择“此页”。*</span><span class="sxs-lookup"><span data-stu-id="a310a-213">*Select 'This page' under 'Feedback' if you have feedback on this documentation.*</span></span>
