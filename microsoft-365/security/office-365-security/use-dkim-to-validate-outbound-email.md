---
title: 如何在自定义域中使用 DKIM 发送电子邮件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 了解如何结合使用域密钥识别邮件 (DKIM) 和 Microsoft 365，以确保目标电子邮件系统信任从自定义域发送的邮件。
ms.openlocfilehash: 0c77798f0bf4b5dedfa5023eaa0b4de4ab8c5b64
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870988"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="e3ff1-103">使用 DKIM 验证从自定义域发送的出站电子邮件</span><span class="sxs-lookup"><span data-stu-id="e3ff1-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="e3ff1-104">**摘要：** 本文介绍了如何结合使用域密钥识别邮件 (DKIM) 和 Microsoft 365，以确保目标电子邮件系统信任从自定义域发送的出站邮件。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="e3ff1-105">除了使用 SPF 和 DMARC 之外，还应使用 DKIM 来帮助防止欺骗程序发送看上去发送自您的域的邮件。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="e3ff1-106">可以使用 DKIM 将数字签名添加到出站电子邮件的邮件头中。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-106">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="e3ff1-107">这听起来这很复杂，其实不然。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-107">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="e3ff1-108">配置 DKIM 时，您将使用加密身份验证授权您的域关联到电子邮件或对电子邮件进行签名。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="e3ff1-109">接收来自域的电子邮件的电子邮件系统可以使用此数字签名来帮助确定他们收到的传入电子邮件是否合法。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>

<span data-ttu-id="e3ff1-110">基本上，您可以使用私钥来加密域的传出电子邮件中的邮件头。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="e3ff1-111">向域 DNS 记录发布公钥，然后接收服务器可用来解码签名。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="e3ff1-112">它们使用公钥来确认邮件确实是你发送的，而不是其他人 *假冒* 你的域发送的。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-112">They use the public key to verify that the messages are really coming from you and not coming from someone *spoofing* your domain.</span></span>

<span data-ttu-id="e3ff1-113">Microsoft 365 自动为它的初始“onmicrosoft.com”域设置 DKIM。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-113">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="e3ff1-114">这意味着无需执行任何操作，即可为任意初始域名（例如 litware.onmicrosoft.com）。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-114">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="e3ff1-115">有关域的详细信息，请参阅[关于域的常见问题](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-115">For more information about domains, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="e3ff1-116">你也可以选择对自己的自定义域不执行任何有关 DKIM 的操作。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-116">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="e3ff1-117">如果你没有为自定义域设置 DKIM，Microsoft 365 会创建私钥和公钥对，启用 DKIM 签名，然后为自定义域配置 Microsoft 365 默认策略。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-117">If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span> <span data-ttu-id="e3ff1-118">虽然这对于大多数客户来说已经足够了，但仍应在以下情况下为自定义域手动配置 DKIM：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-118">While this is sufficient coverage for most customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="e3ff1-119">在 Microsoft 365 中有多个自定义域</span><span class="sxs-lookup"><span data-stu-id="e3ff1-119">You have more than one custom domain in Microsoft 365</span></span>

- <span data-ttu-id="e3ff1-120">您同时要设置 DMARC（推荐）</span><span class="sxs-lookup"><span data-stu-id="e3ff1-120">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="e3ff1-121">您想要控制您的私钥</span><span class="sxs-lookup"><span data-stu-id="e3ff1-121">You want control over your private key</span></span>

- <span data-ttu-id="e3ff1-122">您要自定义 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="e3ff1-122">You want to customize your CNAME records</span></span>

- <span data-ttu-id="e3ff1-123">你想为源自第三方域的电子邮件设置 DKIM 密钥，例如，如果你使用第三方群发邮件程序。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-123">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="e3ff1-124">本文内容：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-124">In this article:</span></span>

- [<span data-ttu-id="e3ff1-125">DKIM 如何能够比单独使用 SPF 更有效地防止恶意欺骗</span><span class="sxs-lookup"><span data-stu-id="e3ff1-125">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="e3ff1-126">手动将 1024 位密钥升级到 2048 位 DKIM 加密密钥</span><span class="sxs-lookup"><span data-stu-id="e3ff1-126">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="e3ff1-127">手动设置 DKIM 需要执行的步骤</span><span class="sxs-lookup"><span data-stu-id="e3ff1-127">Steps you need to do to manually set up DKIM</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="e3ff1-128">为多个自定义域配置 DKIM 的具体步骤</span><span class="sxs-lookup"><span data-stu-id="e3ff1-128">To configure DKIM for more than one custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="e3ff1-129">为自定义域禁用 DKIM 签名策略</span><span class="sxs-lookup"><span data-stu-id="e3ff1-129">Disabling the DKIM signing policy for a custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="e3ff1-130">DKIM 和 Microsoft 365 的默认行为</span><span class="sxs-lookup"><span data-stu-id="e3ff1-130">Default behavior for DKIM and Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="e3ff1-131">设置 DKIM 以便第三方服务可以代表自定义域发送或假冒电子邮件</span><span class="sxs-lookup"><span data-stu-id="e3ff1-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="e3ff1-132">后续步骤：为 Microsoft 365 设置 DKIM 后</span><span class="sxs-lookup"><span data-stu-id="e3ff1-132">Next steps: After you set up DKIM for Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="e3ff1-133">DKIM 如何能够比单独使用 SPF 更有效地防止恶意欺骗</span><span class="sxs-lookup"><span data-stu-id="e3ff1-133">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="e3ff1-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ff1-134"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="e3ff1-p105">虽然 SPF 将信息添加到邮件信封中，但实际上是 DKIM 在邮件头中加密签名。当你转发邮件时，转发服务器可能会截除邮件信封部分。由于数字签名作为电子邮件头的一部分与电子邮件同时存在，因此即使当邮件进行了转发，DKIM 也仍在运行，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-p105">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![关系图显示转发邮件在 SPF 检查失败的情况下传递 DKIM 身份验证](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="e3ff1-p106">在此示例中，如果您只发布了域的一条 SPF TXT 记录，收件人的邮件服务器可能已将您的电子邮件标记为垃圾邮件，并生成一个误报结果。在这种情况下，添加 DKIM 可以减少误报垃圾邮件报告。由于 DKIM 依赖于公钥加密（而不仅仅对 IP 地址加密）进行身份验证，DKIM 被认为是比 SPF 更强大的身份验证形式。建议在部署中同时使用 SPF、DKIM 以及 DMARC。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-p106">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. The addition of DKIM in this scenario reduces false positive spam reporting. Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

<span data-ttu-id="e3ff1-p107">具体功能：DKIM 使用私钥将加密的签名插入邮件头。在邮件头中，将签名域或出站域作为 **d =** 字段中的值插入。然后，验证域或收件人的域使用 **d =** 字段从 DNS 中查找公钥，对邮件进行身份验证。如果邮件已经过验证，则 DKIM 检查通过。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-p107">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message. If the message is verified, the DKIM check passes.</span></span>

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="e3ff1-147">手动将 1024 位密钥升级到 2048 位 DKIM 加密密钥</span><span class="sxs-lookup"><span data-stu-id="e3ff1-147">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="e3ff1-148"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ff1-148"><a name="1024to2048DKIM"> </a></span></span>

<span data-ttu-id="e3ff1-149">由于 DKIM 密钥同时支持 1024 和 2048 位，因此这些说明将告诉你如何将 1024 位密钥升级到 2048 位。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-149">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048.</span></span> <span data-ttu-id="e3ff1-150">以下步骤针对的是两种用例，请选择最适合你的配置的步骤。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-150">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

1. <span data-ttu-id="e3ff1-151">如果你 **已经配置了 DKIM**，请按如下所示轮换位数：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-151">When you **already have DKIM configured**, you rotate bitness as follows:</span></span>

   1. <span data-ttu-id="e3ff1-152">[通过 PowerShell 连接到 Office 365 工作负载](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-152">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="e3ff1-153">（cmdlet 来自 Exchange Online。）</span><span class="sxs-lookup"><span data-stu-id="e3ff1-153">(The cmdlet comes from Exchange Online.)</span></span>
   1. <span data-ttu-id="e3ff1-154">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-154">Run the following command:</span></span>

      ```powershell
      Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
      ```

1. <span data-ttu-id="e3ff1-155">或者，对于 **新实现的 DKIM**：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-155">Or for a **new implementation of DKIM**:</span></span>

   1. <span data-ttu-id="e3ff1-156">[通过 PowerShell 连接到 Office 365 工作负载](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-156">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="e3ff1-157">（这是 Exchange Online cmdlet。）</span><span class="sxs-lookup"><span data-stu-id="e3ff1-157">(This is an Exchange Online cmdlet.)</span></span>
   1. <span data-ttu-id="e3ff1-158">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-158">Run the following command:</span></span>

      ```powershell
      New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True
      ```

<span data-ttu-id="e3ff1-159">与 Microsoft 365 保持连接，以 *验证* 配置。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-159">Stay connected to Microsoft 365 to *verify* the configuration.</span></span>

1. <span data-ttu-id="e3ff1-160">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-160">Run the following command:</span></span>

   ```powershell
   Get-DkimSigningConfig -Identity {Domain for which the configuration was set} | Format-List
   ```

> [!TIP]
> <span data-ttu-id="e3ff1-161">这一新的 2048 位密钥将在 RotateOnDate 生效，在过渡期间则使用 1024 位密钥发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-161">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="e3ff1-162">四天后，可以使用 2048 位秘钥再次进行测试（即一旦轮换对第二个选择器生效）。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-162">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="e3ff1-163">若要轮换到第二个选择器，可以采用下列方法：a) 让 Microsoft 365 服务轮换选择器，并在未来 6 个月内升级到 2048 位，或 b) 在确认使用 2048 位 4 天后，使用上面列出的相应 cmdlet 手动轮换第二个选择器密钥。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-163">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a><span data-ttu-id="e3ff1-164">手动设置 DKIM 需要执行的步骤</span><span class="sxs-lookup"><span data-stu-id="e3ff1-164">Steps you need to do to manually set up DKIM</span></span>
<span data-ttu-id="e3ff1-165"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ff1-165"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="e3ff1-166">要配置 DKIM，您需要完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-166">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="e3ff1-167">在 DNS 中发布自定义域的两条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="e3ff1-167">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="e3ff1-168">为自定义域启用 DKIM 签名</span><span class="sxs-lookup"><span data-stu-id="e3ff1-168">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="e3ff1-169">在 DNS 中发布自定义域的两条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="e3ff1-169">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="e3ff1-170"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ff1-170"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="e3ff1-171">对于您要为其在 DNS 中添加 DKIM 签名的每个域，您需要发布两条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-171">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

> [!NOTE]
> <span data-ttu-id="e3ff1-172">如果你尚未阅读完整的文章，则可能错过了这个省时的 PowerShell 连接信息：[通过 PowerShell 连接到 Office365 工作负载。](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)</span><span class="sxs-lookup"><span data-stu-id="e3ff1-172">If you haven't read the full article, you may have missed this time-saving PowerShell connection information: [Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="e3ff1-173">（cmdlet 来自 Exchange Online。）</span><span class="sxs-lookup"><span data-stu-id="e3ff1-173">(The cmdlet comes from Exchange Online.)</span></span>

<span data-ttu-id="e3ff1-174">运行以下命令以创建选择器目录：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-174">Run the following commands to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="e3ff1-175">如果在 Microsoft 365 中除了初始域外你还预配了自定义域，必须为每个附加域发布两条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-175">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="e3ff1-176">因此，如果你有两个域，就必须发布两条额外的 CNAME 记录，依此类推。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-176">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="e3ff1-177">CNAME 记录使用以下格式。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-177">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3ff1-178">如果你是我们的 GCC High 客户，我们会以不同方式计算 _domainGuid_！</span><span class="sxs-lookup"><span data-stu-id="e3ff1-178">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="e3ff1-179">不是查找你的 _initialDomain_ 来计算 _domainGuid_，而是直接从自定义域计算。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-179">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="e3ff1-180">例如，如果自定义域名为“contoso.com”，则 domainGuid 将变为“contoso-com”，任何句点都将替换为短划线。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-180">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="e3ff1-181">因此，无论 initialDomain 指向什么 MX 记录，你都将始终使用上述方法来计算要在 CNAME 记录中使用的 domainGuid。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-181">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="e3ff1-182">其中：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-182">Where:</span></span>

- <span data-ttu-id="e3ff1-183">对于 Microsoft 365，选择器始终为“selector1”或“selector2”。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-183">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="e3ff1-184">_domainGUID_ 与显示在 mail.protection.outlook.com 前面的自定义域的自定义 MX 记录中的 _domainGUID_ 相同。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-184">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="e3ff1-185">例如，在域 contoso.com 的以下 MX 记录中，_domainGUID_ 为 contoso com：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-185">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="e3ff1-186">contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-186">contoso.com.</span></span>  <span data-ttu-id="e3ff1-187">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="e3ff1-187">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="e3ff1-188">_initialDomain_ 是你在注册 Microsoft 365 时所使用的域。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-188">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="e3ff1-189">初始域始终以 onmicrosoft.com 结尾。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-189">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="e3ff1-190">有关确定初始域的信息，请参阅[关于域的常见问题](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-190">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="e3ff1-191">例如，如果你有一个初始域 cohovineyardandwinery.onmicrosoft.com，以及两个自定义域 cohovineyard.com 和 cohowinery.com，那么你需要为额外配置的每个域设置两条 CNAME 记录，总共四条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-191">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> <span data-ttu-id="e3ff1-192">创建第二条记录非常重要，但创建时仅可使用其中一个选择器。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-192">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="e3ff1-193">实际上，第二个选择器可能指向尚未创建的地址。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-193">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="e3ff1-194">我们仍然建议创建第二条 CNAME 记录，因为你的密钥轮换是无缝的。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-194">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>


### <a name="enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="e3ff1-195">为自定义域启用 DKIM 签名</span><span class="sxs-lookup"><span data-stu-id="e3ff1-195">Enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="e3ff1-196"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ff1-196"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="e3ff1-197">在 DNS 中发布 CNAME 记录后，就可以通过 Microsoft 365 启用 DKIM 签名了。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-197">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365.</span></span> <span data-ttu-id="e3ff1-198">为此，可以使用 Microsoft 365 管理中心或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-198">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="e3ff1-199">使用管理中心为自定义域启用 DKIM 签名的具体步骤</span><span class="sxs-lookup"><span data-stu-id="e3ff1-199">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="e3ff1-200">使用工作或学校帐户[登录 Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-200">[Sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="e3ff1-201">选择左上角的应用启动器图标，然后选择“**管理员**”。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-201">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="e3ff1-202">在左下侧导航中，展开“管理”并选择“Exchange”。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-202">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>

4. <span data-ttu-id="e3ff1-203">依次转到" **保护**"\>" **dkim**"。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-203">Go to **Protection** \> **dkim**.</span></span>

5. <span data-ttu-id="e3ff1-p120">选择要对其启用 DKIM 的域，然后对“**对此域的邮件进行 DKIM 签名**”选择“**启用**”。为每个自定义域重复执行这一步。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-p120">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="e3ff1-206">使用 PowerShell 为自定义域启用 DKIM 签名</span><span class="sxs-lookup"><span data-stu-id="e3ff1-206">To enable DKIM signing for your custom domain by using PowerShell</span></span>

> [!IMPORTANT]
>:::image type="content" source="../../media/DKIMNoKeysSavedForThisDomain.PNG" alt-text="“此域未保存 DKIM 密钥。”错误。":::
> <span data-ttu-id="e3ff1-208">如果你首次配置 DKIM，并看到错误“此域未保存 DKIM 密钥。”</span><span class="sxs-lookup"><span data-stu-id="e3ff1-208">If you are configuring DKIM for the first time and see the error 'No DKIM keys saved for this domain.'</span></span> <span data-ttu-id="e3ff1-209">请完成下面步骤 2 中的命令（例如，*Set-DkimSigningConfig -Identity contoso.com -Enabled $true*），以查看密钥。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-209">complete the command in step 2, below (for example, *Set-DkimSigningConfig -Identity contoso.com -Enabled $true*) to see the key.</span></span>

1. <span data-ttu-id="e3ff1-210">[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-210">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e3ff1-211">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-211">Run the following command:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   <span data-ttu-id="e3ff1-212">其中，_domain_ 是要对其启用 DKIM 签名的自定义域名。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-212">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="e3ff1-213">例如，对于域 contoso.com：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-213">For example, for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="e3ff1-214">确认是否已为 Microsoft 365 正确配置 DKIM 签名的具体步骤</span><span class="sxs-lookup"><span data-stu-id="e3ff1-214">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="e3ff1-p122">请等待几分钟，然后按以下步骤操作，确认是否已正确配置 DKIM。这样就有时间将域的 DKIM 信息分布到整个网络了。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-p122">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="e3ff1-217">从 Microsoft 365 中已启用 DKIM 的域内的帐户向其他电子邮件帐户（如 outlook.com 或 Hotmail.com）发送邮件。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-217">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="e3ff1-p123">不要将 aol.com 帐户用于测试目的。如果 SPF 检查通过，AOL 可能会跳过 DKIM 检查。这会使测试无效。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-p123">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>

- <span data-ttu-id="e3ff1-p124">打开邮件，然后查看邮件头。查看邮件头的说明因邮件客户端而异。有关在 Outlook 中查看邮件头的说明，请参阅[在 Outlook 中查看电子邮件头](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-p124">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="e3ff1-p125">进行了 DKIM 签名的邮件将包含主机名以及您在发布 CNAME 条目时定义的域。该邮件如下例所示：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-p125">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="e3ff1-p126">查找身份验证结果标头。尽管每个接收服务用于标记传入邮件的格式稍有不同，但结果应都包括以下类似内容：**DKIM=pass** 或 **DKIM=OK**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-p126">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="e3ff1-228">为多个自定义域配置 DKIM 的具体步骤</span><span class="sxs-lookup"><span data-stu-id="e3ff1-228">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="e3ff1-229"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ff1-229"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="e3ff1-230">如果你在将来决定添加其他自定义域，并且想要为新域启用 DKIM，必须为每个域完成本文中介绍的步骤。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-230">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="e3ff1-231">具体而言，完成[手动设置 DKIM 需要执行的操作](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)中的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-231">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="e3ff1-232">为自定义域禁用 DKIM 签名策略</span><span class="sxs-lookup"><span data-stu-id="e3ff1-232">Disabling the DKIM signing policy for a custom domain</span></span>
<span data-ttu-id="e3ff1-233"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ff1-233"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="e3ff1-234">禁用签名策略不会完全禁用 DKIM。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-234">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="e3ff1-235">一段时间后，Microsoft 365 会自动为你的域应用默认策略。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-235">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="e3ff1-236">有关详细信息，请参阅 [DKIM 和 Microsoft 365 的默认行为](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-236">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="e3ff1-237">使用 Windows PowerShell 禁用 DKIM 签名策略</span><span class="sxs-lookup"><span data-stu-id="e3ff1-237">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="e3ff1-238">[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-238">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e3ff1-239">为您要为其禁用 DKIM 签名的每个域运行以下命令之一。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-239">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="e3ff1-240">例如：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-240">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="e3ff1-241">或</span><span class="sxs-lookup"><span data-stu-id="e3ff1-241">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="e3ff1-242">其中， _number_ 是策略的索引。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-242">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="e3ff1-243">例如：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-243">For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="e3ff1-244">DKIM 和 Microsoft 365 的默认行为</span><span class="sxs-lookup"><span data-stu-id="e3ff1-244">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="e3ff1-245"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ff1-245"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="e3ff1-246">如果你不启用 DKIM，Microsoft 365 会自动为你的默认域创建 1024 位 DKIM 公钥，以及我们存储在数据中心内部的关联私钥。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-246">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="e3ff1-247">默认情况下，Microsoft 365 对没有适当策略的域使用默认签名配置。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-247">By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="e3ff1-248">也就是说，如果你自己没有设置 DKIM，Microsoft 365 会使用它的默认策略和它创建的密钥来为你的域启用 DKIM。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-248">This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="e3ff1-249">此外，如果你在启用 DKIM 签名后禁用它，一段时间后，Microsoft 365 会自动为你的域应用默认策略。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-249">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="e3ff1-250">在以下示例中，假设 fabrikam.com 的 DKIM 是由 Microsoft 365（而不是域管理员）启用。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-250">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain.</span></span> <span data-ttu-id="e3ff1-251">这表明所需的 CNAME 在 DNS 中不存在。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-251">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="e3ff1-252">来自此域的电子邮件的 DKIM 签名如下所示：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-252">DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="e3ff1-253">在此示例中，主机名和域包含在 fabrikam.com 的 DKIM 签名由域管理员启用情况下 CNAME 将指向的值。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-253">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="e3ff1-254">最终，每封发送自 Microsoft 365 的邮件都会进行 DKIM 签名。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-254">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="e3ff1-255">如果您自行启用 DKIM，该域将与发件人地址（此例中为 fabrikam.com）中的域相同。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-255">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="e3ff1-256">如果不自行启用，该域将不同于发件人地址中的域，而是会使用组织的初始域。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-256">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="e3ff1-257">有关确定初始域的信息，请参阅[关于域的常见问题](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-257">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="e3ff1-258">设置 DKIM 以便第三方服务可以代表自定义域发送或假冒电子邮件</span><span class="sxs-lookup"><span data-stu-id="e3ff1-258">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="e3ff1-259"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ff1-259"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="e3ff1-260">一些批量电子邮件服务提供商或服务型软件提供商允许你为来自其服务的电子邮件设置 DKIM 密钥。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-260">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span></span> <span data-ttu-id="e3ff1-261">这需要你自己和第三方之间进行协调，从而设置必要的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-261">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span></span> <span data-ttu-id="e3ff1-262">一些第三方服务器可以有自己的、具有不同选择器的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-262">Some third-party servers can have their own CNAME records with different selectors.</span></span> <span data-ttu-id="e3ff1-263">没有任何两个组织的操作过程是完全相同的。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-263">No two organizations do it exactly the same way.</span></span> <span data-ttu-id="e3ff1-264">而是，该过程完全取决于组织。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-264">Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="e3ff1-265">显示为 contoso.com 和 bulkemailprovider.com 正确配置了 DKIM 的示例邮件如下所示：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-265">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="e3ff1-266">在此示例中，为了获得该结果：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-266">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="e3ff1-267">批量电子邮件提供商为 Contoso 提供一个 DKIM 公钥。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-267">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="e3ff1-268">Contoso 将 DKIM 密钥发布到 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-268">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="e3ff1-p134">发送电子邮件时，批量电子邮件提供商使用相应的私钥对密钥进行签名。这样一来，批量电子邮件提供商可以将 DKIM 签名附加到邮件头中。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-p134">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="e3ff1-271">接收电子邮件系统通过对 From 中的域进行 DKIM-Signature d=\<domain\> 值验证来执行 DKIM 检查：(5322.From) 邮件的地址。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-271">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="e3ff1-272">在此示例中，值匹配：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-272">In this example, the values match:</span></span>

   > <span data-ttu-id="e3ff1-273">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-273">sender@**contoso.com**</span></span>

   > <span data-ttu-id="e3ff1-274">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="e3ff1-274">d=**contoso.com**</span></span>

## <a name="identify-domains-that-do-not-send-email"></a><span data-ttu-id="e3ff1-275">确定不发送电子邮件的域</span><span class="sxs-lookup"><span data-stu-id="e3ff1-275">Identify domains that do not send email</span></span>

<span data-ttu-id="e3ff1-276">组织应该通过在这些域的DKIM记录中明确说明 `v=DKIM1; p=`域是否不发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-276">Organizations should explicitly state if a domain does not send email by specifying `v=DKIM1; p=` in the DKIM record for those domains.</span></span> <span data-ttu-id="e3ff1-277">这将告知接收邮件的服务器，该域没有有效的公共密钥，任何声称来自该域的邮件都应该被拒绝。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-277">This advises receiving email servers that there are no valid public keys for the domain, and any email claiming to be from that domain should be rejected.</span></span> <span data-ttu-id="e3ff1-278">应该为每个域和子域使用通配符DKIM来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-278">You should do this for each domain and subdomain using a wildcard DKIM.</span></span>

<span data-ttu-id="e3ff1-279">例如，DKIM 记录将如下所示：</span><span class="sxs-lookup"><span data-stu-id="e3ff1-279">For example, the DKIM record would look like this:</span></span>

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="e3ff1-280">后续步骤：为 Microsoft 365 设置 DKIM 后</span><span class="sxs-lookup"><span data-stu-id="e3ff1-280">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="e3ff1-281"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="e3ff1-281"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="e3ff1-282">尽管 DKIM 旨在帮助防止欺骗，但 DKIM 与 SPF 和 DMARC 协同工作效果更佳。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-282">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="e3ff1-283">设置了 DKIM 后，如果你尚未设置 SPF，则应执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-283">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="e3ff1-284">若要了解 SPF 的快速简介及其快速配置方法，请参阅[在 Microsoft 365 中设置 SPF 以防欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-284">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="e3ff1-285">若要更深入地了解 Microsoft 365 如何使用 SPF，或要了解故障排除或非标准部署（如混合部署），请从 [Microsoft 365 如何使用发件人策略框架 (SPF) 以防欺骗](how-office-365-uses-spf-to-prevent-spoofing.md)入手。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-285">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="e3ff1-286">接下来，请参阅[使用 DMARC 验证电子邮件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-286">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="e3ff1-287">[反垃圾邮件邮件头](anti-spam-message-headers.md)包括 Microsoft 365 用来执行 DKIM 检查的语法和头字段。</span><span class="sxs-lookup"><span data-stu-id="e3ff1-287">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>

## <a name="more-information"></a><span data-ttu-id="e3ff1-288">更多信息</span><span class="sxs-lookup"><span data-stu-id="e3ff1-288">More information</span></span>

<span data-ttu-id="e3ff1-289">通过 PowerShell [Rotate DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig) 进行密钥轮换</span><span class="sxs-lookup"><span data-stu-id="e3ff1-289">Key rotation via PowerShell [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig)</span></span>
