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
ms.openlocfilehash: 66f352b6c3a5d3b3beff3043a3f0d1a435d1e5d1
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560880"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a>使用 DKIM 验证从自定义域发送的出站电子邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 **摘要：** 本文介绍了如何结合使用域密钥识别邮件 (DKIM) 和 Microsoft 365，以确保目标电子邮件系统信任从自定义域发送的出站邮件。

除了使用 SPF 和 DMARC 之外，还应使用 DKIM 来帮助防止欺骗程序发送看上去发送自您的域的邮件。 可以使用 DKIM 将数字签名添加到出站电子邮件的邮件头中。 这听起来这很复杂，其实不然。 配置 DKIM 时，您将使用加密身份验证授权您的域关联到电子邮件或对电子邮件进行签名。 接收来自域的电子邮件的电子邮件系统可以使用此数字签名来帮助确定他们收到的传入电子邮件是否合法。

基本上，您可以使用私钥来加密域的传出电子邮件中的邮件头。 向域 DNS 记录发布公钥，然后接收服务器可用来解码签名。 它们使用公钥来确认邮件确实是你发送的，而不是其他人 *假冒* 你的域发送的。

Microsoft 365 自动为它的初始“onmicrosoft.com”域设置 DKIM。 这意味着无需执行任何操作，即可为任意初始域名（例如 litware.onmicrosoft.com）。 有关域的详细信息，请参阅[关于域的常见问题](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)。

你也可以选择对自己的自定义域不执行任何有关 DKIM 的操作。 如果你没有为自定义域设置 DKIM，Microsoft 365 会创建私钥和公钥对，启用 DKIM 签名，然后为自定义域配置 Microsoft 365 默认策略。 虽然这对于大多数客户来说已经足够了，但仍应在以下情况下为自定义域手动配置 DKIM：

- 在 Microsoft 365 中有多个自定义域

- 您同时要设置 DMARC（推荐）

- 您想要控制您的私钥

- 您要自定义 CNAME 记录

- 你想为源自第三方域的电子邮件设置 DKIM 密钥，例如，如果你使用第三方群发邮件程序。

本文内容：

- [DKIM 如何能够比单独使用 SPF 更有效地防止恶意欺骗](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [手动将 1024 位密钥升级到 2048 位 DKIM 加密密钥](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [手动设置 DKIM 需要执行的步骤](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [为多个自定义域配置 DKIM 的具体步骤](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [为自定义域禁用 DKIM 签名策略](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [DKIM 和 Microsoft 365 的默认行为](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [设置 DKIM 以便第三方服务可以代表自定义域发送或假冒电子邮件](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [后续步骤：为 Microsoft 365 设置 DKIM 后](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a>DKIM 如何能够比单独使用 SPF 更有效地防止恶意欺骗
<a name="HowDKIMWorks"> </a>

虽然 SPF 将信息添加到邮件信封中，但实际上是 DKIM 在邮件头中加密签名。当你转发邮件时，转发服务器可能会截除邮件信封部分。由于数字签名作为电子邮件头的一部分与电子邮件同时存在，因此即使当邮件进行了转发，DKIM 也仍在运行，如以下示例所示。

![关系图显示转发邮件在 SPF 检查失败的情况下传递 DKIM 身份验证](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

在此示例中，如果您只发布了域的一条 SPF TXT 记录，收件人的邮件服务器可能已将您的电子邮件标记为垃圾邮件，并生成一个误报结果。在这种情况下，添加 DKIM 可以减少误报垃圾邮件报告。由于 DKIM 依赖于公钥加密（而不仅仅对 IP 地址加密）进行身份验证，DKIM 被认为是比 SPF 更强大的身份验证形式。建议在部署中同时使用 SPF、DKIM 以及 DMARC。

具体功能：DKIM 使用私钥将加密的签名插入邮件头。在邮件头中，将签名域或出站域作为 **d =** 字段中的值插入。然后，验证域或收件人的域使用 **d =** 字段从 DNS 中查找公钥，对邮件进行身份验证。如果邮件已经过验证，则 DKIM 检查通过。

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>手动将 1024 位密钥升级到 2048 位 DKIM 加密密钥
<a name="1024to2048DKIM"> </a>

由于 DKIM 密钥同时支持 1024 和 2048 位，因此这些说明将告诉你如何将 1024 位密钥升级到 2048 位。 以下步骤针对的是两种用例，请选择最适合你的配置的步骤。

1. 如果你 **已经配置了 DKIM**，请按如下所示轮换位数：

   1. [通过 PowerShell 连接到 Office 365 工作负载](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)。 （cmdlet 来自 Exchange Online。）
   1. 运行以下命令：

      ```powershell 
      Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
      ```

1. 或者，对于 **新实现的 DKIM**：

   1. [通过 PowerShell 连接到 Office 365 工作负载](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)。 （这是 Exchange Online cmdlet。）
   1. 运行以下命令：

      ```powershell
      New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True
      ```

与 Microsoft 365 保持连接，以 *验证* 配置。

1. 运行以下命令：

   ```powershell
   Get-DkimSigningConfig -Identity {Domain for which the configuration was set} | Format-List
   ```

> [!TIP]
> 这一新的 2048 位密钥将在 RotateOnDate 生效，在过渡期间则使用 1024 位密钥发送电子邮件。 四天后，可以使用 2048 位秘钥再次进行测试（即一旦轮换对第二个选择器生效）。

若要轮换到第二个选择器，可以采用下列方法：a) 让 Microsoft 365 服务轮换选择器，并在未来 6 个月内升级到 2048 位，或 b) 在确认使用 2048 位 4 天后，使用上面列出的相应 cmdlet 手动轮换第二个选择器密钥。

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a>手动设置 DKIM 需要执行的步骤
<a name="SetUpDKIMO365"> </a>

要配置 DKIM，您需要完成以下步骤：

- [在 DNS 中发布自定义域的两条 CNAME 记录](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [为自定义域启用 DKIM 签名](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>在 DNS 中发布自定义域的两条 CNAME 记录
<a name="Publish2CNAME"> </a>

对于您要为其在 DNS 中添加 DKIM 签名的每个域，您需要发布两条 CNAME 记录。

> [!NOTE]
> 如果你尚未阅读完整的文章，则可能错过了这个省时的 PowerShell 连接信息：[通过 PowerShell 连接到 Office365 工作负载。](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) （cmdlet 来自 Exchange Online。） 

运行以下命令以创建选择器目录：

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

如果在 Microsoft 365 中除了初始域外你还预配了自定义域，必须为每个附加域发布两条 CNAME 记录。 因此，如果你有两个域，就必须发布两条额外的 CNAME 记录，依此类推。

CNAME 记录使用以下格式。

> [!IMPORTANT]
> 如果你是我们的 GCC High 客户，我们会以不同方式计算 _domainGuid_！ 不是查找你的 _initialDomain_ 来计算 _domainGuid_，而是直接从自定义域计算。 例如，如果自定义域名为“contoso.com”，则 domainGuid 将变为“contoso-com”，任何句点都将替换为短划线。 因此，无论 initialDomain 指向什么 MX 记录，你都将始终使用上述方法来计算要在 CNAME 记录中使用的 domainGuid。

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

其中：

- 对于 Microsoft 365，选择器始终为“selector1”或“selector2”。

- _domainGUID_ 与显示在 mail.protection.outlook.com 前面的自定义域的自定义 MX 记录中的 _domainGUID_ 相同。 例如，在域 contoso.com 的以下 MX 记录中，_domainGUID_ 为 contoso com：

  > contoso.com。  3600  IN  MX   5 contoso-com.mail.protection.outlook.com

- _initialDomain_ 是你在注册 Microsoft 365 时所使用的域。 初始域始终以 onmicrosoft.com 结尾。 有关确定初始域的信息，请参阅[关于域的常见问题](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)。

例如，如果你有一个初始域 cohovineyardandwinery.onmicrosoft.com，以及两个自定义域 cohovineyard.com 和 cohowinery.com，那么你需要为额外配置的每个域设置两条 CNAME 记录，总共四条 CNAME 记录。

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
> 创建第二条记录非常重要，但创建时仅可使用其中一个选择器。 实际上，第二个选择器可能指向尚未创建的地址。 我们仍然建议创建第二条 CNAME 记录，因为你的密钥轮换是无缝的。


### <a name="enable-dkim-signing-for-your-custom-domain"></a>为自定义域启用 DKIM 签名
<a name="EnableDKIMinO365"> </a>

在 DNS 中发布 CNAME 记录后，就可以通过 Microsoft 365 启用 DKIM 签名了。 为此，可以使用 Microsoft 365 管理中心或 PowerShell。

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>使用管理中心为自定义域启用 DKIM 签名的具体步骤

1. 使用工作或学校帐户[登录 Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。

2. 选择左上角的应用启动器图标，然后选择“**管理员**”。

3. 在左下侧导航中，展开“管理”并选择“Exchange”。

4. 依次转到" **保护**"\>" **dkim**"。

5. 选择要对其启用 DKIM 的域，然后对“**对此域的邮件进行 DKIM 签名**”选择“**启用**”。为每个自定义域重复执行这一步。

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>使用 PowerShell 为自定义域启用 DKIM 签名

1. [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行以下命令：

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   其中，_domain_ 是要对其启用 DKIM 签名的自定义域名。

   例如，对于域 contoso.com：

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a>确认是否已为 Microsoft 365 正确配置 DKIM 签名的具体步骤

请等待几分钟，然后按以下步骤操作，确认是否已正确配置 DKIM。这样就有时间将域的 DKIM 信息分布到整个网络了。

- 从 Microsoft 365 中已启用 DKIM 的域内的帐户向其他电子邮件帐户（如 outlook.com 或 Hotmail.com）发送邮件。

- 不要将 aol.com 帐户用于测试目的。如果 SPF 检查通过，AOL 可能会跳过 DKIM 检查。这会使测试无效。

- 打开邮件，然后查看邮件头。查看邮件头的说明因邮件客户端而异。有关在 Outlook 中查看邮件头的说明，请参阅[在 Outlook 中查看电子邮件头](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)。

  进行了 DKIM 签名的邮件将包含主机名以及您在发布 CNAME 条目时定义的域。该邮件如下例所示：

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- 查找身份验证结果标头。尽管每个接收服务用于标记传入邮件的格式稍有不同，但结果应都包括以下类似内容：**DKIM=pass** 或 **DKIM=OK**

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a>为多个自定义域配置 DKIM 的具体步骤
<a name="DKIMMultiDomain"> </a>

如果你在将来决定添加其他自定义域，并且想要为新域启用 DKIM，必须为每个域完成本文中介绍的步骤。 具体而言，完成[手动设置 DKIM 需要执行的操作](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)中的所有步骤。

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a>为自定义域禁用 DKIM 签名策略 
<a name="DisableDKIMSigningPolicy"> </a>

禁用签名策略不会完全禁用 DKIM。 一段时间后，Microsoft 365 会自动为你的域应用默认策略。 有关详细信息，请参阅 [DKIM 和 Microsoft 365 的默认行为](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)。

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>使用 Windows PowerShell 禁用 DKIM 签名策略

1. [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

2. 为您要为其禁用 DKIM 签名的每个域运行以下命令之一。

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   例如：

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   或

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   其中， _number_ 是策略的索引。 例如：

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a>DKIM 和 Microsoft 365 的默认行为
<a name="DefaultDKIMbehavior"> </a>

如果你不启用 DKIM，Microsoft 365 会自动为你的默认域创建 1024 位 DKIM 公钥，以及我们存储在数据中心内部的关联私钥。 默认情况下，Microsoft 365 对没有适当策略的域使用默认签名配置。 也就是说，如果你自己没有设置 DKIM，Microsoft 365 会使用它的默认策略和它创建的密钥来为你的域启用 DKIM。

此外，如果你在启用 DKIM 签名后禁用它，一段时间后，Microsoft 365 会自动为你的域应用默认策略。

在以下示例中，假设 fabrikam.com 的 DKIM 是由 Microsoft 365（而不是域管理员）启用。 这表明所需的 CNAME 在 DNS 中不存在。 来自此域的电子邮件的 DKIM 签名如下所示：

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

在此示例中，主机名和域包含在 fabrikam.com 的 DKIM 签名由域管理员启用情况下 CNAME 将指向的值。 最终，每封发送自 Microsoft 365 的邮件都会进行 DKIM 签名。 如果您自行启用 DKIM，该域将与发件人地址（此例中为 fabrikam.com）中的域相同。 如果不自行启用，该域将不同于发件人地址中的域，而是会使用组织的初始域。 有关确定初始域的信息，请参阅[关于域的常见问题](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)。

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>设置 DKIM 以便第三方服务可以代表自定义域发送或假冒电子邮件
<a name="SetUp3rdPartyspoof"> </a>

一些批量电子邮件服务提供商或服务型软件提供商允许你为来自其服务的电子邮件设置 DKIM 密钥。 这需要你自己和第三方之间进行协调，从而设置必要的 DNS 记录。 一些第三方服务器可以有自己的、具有不同选择器的 CNAME 记录。 没有任何两个组织的操作过程是完全相同的。 而是，该过程完全取决于组织。

显示为 contoso.com 和 bulkemailprovider.com 正确配置了 DKIM 的示例邮件如下所示：

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

在此示例中，为了获得该结果：

1. 批量电子邮件提供商为 Contoso 提供一个 DKIM 公钥。

2. Contoso 将 DKIM 密钥发布到 DNS 记录。

3. 发送电子邮件时，批量电子邮件提供商使用相应的私钥对密钥进行签名。这样一来，批量电子邮件提供商可以将 DKIM 签名附加到邮件头中。

4. 接收电子邮件系统通过对 From 中的域进行 DKIM-Signature d=\<domain\> 值验证来执行 DKIM 检查：(5322.From) 邮件的地址。 在此示例中，值匹配：

   > sender@**contoso.com**

   > d=**contoso.com**
   
## <a name="identify-domains-that-do-not-send-email"></a>确定不发送电子邮件的域

组织应该通过在这些域的DKIM记录中明确说明 `v=DKIM1; p=`域是否不发送电子邮件。 这将告知接收邮件的服务器，该域没有有效的公共密钥，任何声称来自该域的邮件都应该被拒绝。 应该为每个域和子域使用通配符DKIM来执行此操作。

例如，DKIM 记录将如下所示：

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a>后续步骤：为 Microsoft 365 设置 DKIM 后
<a name="DKIMNextSteps"> </a>

尽管 DKIM 旨在帮助防止欺骗，但 DKIM 与 SPF 和 DMARC 协同工作效果更佳。 设置了 DKIM 后，如果你尚未设置 SPF，则应执行此操作。 若要了解 SPF 的快速简介及其快速配置方法，请参阅[在 Microsoft 365 中设置 SPF 以防欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 若要更深入地了解 Microsoft 365 如何使用 SPF，或要了解故障排除或非标准部署（如混合部署），请从 [Microsoft 365 如何使用发件人策略框架 (SPF) 以防欺骗](how-office-365-uses-spf-to-prevent-spoofing.md)入手。 接下来，请参阅[使用 DMARC 验证电子邮件](use-dmarc-to-validate-email.md)。 [反垃圾邮件邮件头](anti-spam-message-headers.md)包括 Microsoft 365 用来执行 DKIM 检查的语法和头字段。

## <a name="more-information"></a>更多信息

通过 PowerShell [Rotate DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig) 进行密钥轮换
