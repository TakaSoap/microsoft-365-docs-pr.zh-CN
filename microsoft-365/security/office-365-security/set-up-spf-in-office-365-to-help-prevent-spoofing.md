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
ms.openlocfilehash: 93356799967932813252e7db27e7ac796e46cbc6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936933"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>设置 SPF 以防欺骗

 **Summary:** This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF) with your custom domain in Office 365. Using SPF helps to validate outbound email sent from your custom domain.

In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing. SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.

For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.

Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.

If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:

- Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".

- 如果您拥有安装了 Office 365 和本地 Exchange 的混合环境。

- 打算设置 DKIM 和 DMARC（推荐）。

## <a name="updating-your-spf-txt-record-for-office-365"></a>为 Office 365 更新您的 SPF TXT 记录

Before you update the TXT record in DNS, you need to gather some information and determine the format of the record. This will help prevent you from generating DNS errors. For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

收集此信息：

- The current SPF TXT record for your custom domain. For instructions, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).

- External IP addresses of all on-premises messaging servers. For example, **131.107.2.200**.

- Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.

- Determine what enforcement rule you want to use for your SPF TXT record. We recommend **-all**. For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

### <a name="to-add-or-update-your-spf-txt-record"></a>添加或更新您的 SPF TXT 记录

1. 请务必熟悉下表中的 SPF 语法。

   ||**如果您使用的是...**|**对于客户而言很常见？**|**添加以下内容...**|
   |:-----|:-----|:-----|:-----|
   |1|所有电子邮件系统（必需）|Common. All SPF TXT records start with this value|v=spf1|
   |2|Exchange Online|常见|include:spf.protection.outlook.com|
   |3|Exchange Online 专用|不常见|ip4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include:spf.protection.outlook.com|
   |4|仅 Office 365 Germany、Microsoft Cloud Germany|不常见|include:spf.protection.outlook.de|
   |5|第三方电子邮件系统|不常见|包括：\<domain name\>  <br/> 其中域名是第三方电子邮件系统的域名。|
   |6|On-premises mail system. For example, Exchange Online Protection plus another mail system|不常见| 为每个附加的邮件系统使用以下其中一个： <br> ip4：\<_IP address_\>  <br/>  ip6：\<_IP address_\>  <br/>  包括：\<_domain name_\>  <br/>  其中 \<_IP address_\> 的值是其他邮件系统的 IP 地址，\<_domain name_\> 是另一个代表您的域发送邮件的邮件系统的 IP 地址。|
   |7|所有电子邮件系统（必需）|Common. All SPF TXT records end with this value|\<_enforcement rule_\>  <br/> This can be one of several values. We recommend that you use **-all**.|

2. 如果尚未创建 SPF TXT 记录，请使用该表中的语法执行此操作：

   例如，如果完全托管在 Office 365 中（即没有本地邮件服务器），则 SPF TXT 记录包括行 1、2 和 7，如下所示：

   `v=spf1 include:spf.protection.outlook.com -all`

   这是最常见的 SPF TXT 记录。 此记录几乎适用于每个人，无论你的 Microsoft 数据中心是位于美国还是欧洲（包括德国），亦或是位于其他地理位置。

   However, if you have purchased Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2. For example, if you are fully-hosted in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:

   `v=spf1 include:spf.protection.outlook.de -all`

   如果你已在 Office 365 中进行部署并已为自定义域设置 SPF TXT 记录，而当前正在向 Office 365 Germany 迁移，则需要更新 SPF TXT 记录。 为此，请将 include:spf.protection.outlook.com**** 更改为 include.spf.protection.outlook.de****。

3. 一旦形成 SPF TXT 记录，则需要更新 DNS 中的记录。 只能为域使用一个 SPF TXT 记录。 如果存在 SPF TXT 记录，则需要更新现有的记录，而不是添加新记录。 转到[为 Office 365 创建 DNS 记录](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)然后单击 DNS 主机的链接。

4. 测试 SPF TXT 记录。

## <a name="more-information-about-spf"></a>有关 SPF 的详细信息

有关支持的 SPF 语法、欺骗、故障排除以及 Office 365 如何支持 SPF 的更加详细的探讨的高级示例，请参阅 [SPF 在 Office 365 中防止欺骗和钓鱼的工作原理](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。

## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>后续步骤：为 Office 365 设置 SPF 之后

Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

 SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against. In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Office 365. To get started, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md). Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).
