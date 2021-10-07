---
title: 使用 DAP 合作伙伴的 Windows PowerShell将域添加到客户端租赁
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: 摘要：使用 PowerShell Microsoft 365向现有客户租户添加备用域名。
ms.openlocfilehash: 1a121407ebe242747a693084289e972e56e1cbee
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170519"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>使用 Windows PowerShell 为委派访问权限 (DAP) 合作伙伴将域添加到客户端租赁

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

您可以使用 PowerShell 创建新域并将其与客户租赁关联，Microsoft 365比使用 Microsoft 365 管理中心。

委派访问权限 (DAP) 合作伙伴是联合和云解决方案提供商 (CSP) 合作伙伴。 他们通常是面向其他公司的网络或电信提供商。 他们Microsoft 365订阅捆绑到他们的服务产品/服务中。 当他们销售 Microsoft 365 订阅时，他们将自动获得代表 (AOBO) 管理客户租赁的权限，以便可以管理和报告客户租赁。
## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

本主题中的过程需要您连接到 连接[Microsoft 365 PowerShell](connect-to-microsoft-365-powershell.md)进行连接。

您也需要您的合作伙伴租户管理员凭据。

您也需要以下信息：

- 您需要客户所需的完全限定的域名 (FQDN)。

- 您需要客户的 **TenantId** 。

- FQDN 必须在 Internet 域名服务 (DNS) 注册机构（如 GoDaddy）中注册。有关如何公开注册域名的详细信息，请参阅[如何购买域名](../admin/get-help-with-domains/buy-a-domain-name.md)。

- 您需要了解如何为您的 DNS 注册机构的注册 DNS 区域添加 TXT 记录。 若要详细了解如何添加 TXT 记录，请参阅添加 [DNS 记录以连接域](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。 如果这些步骤对您不适用，您需要查找适用于您的 DNS 注册机构的过程。

## <a name="create-domains"></a>创建域

 您的客户可能会要求您创建与其租赁关联的其他域，因为他们不想让默认的\<domain>.onmicrosoft.com域成为向全世界展示其公司标识的主要域。此步骤将引导您创建与您的客户租赁相关联的新域。

> [!NOTE]
> 若要执行其中一些操作，对于"向支持的公司分配管理访问权限"设置，登录时使用的合作伙伴管理员帐户必须设置为"完全管理"，此设置位于 Microsoft 365 管理中心 中管理员<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">帐户的详细信息</a>中。 有关管理合作伙伴管理员角色的信息，请参阅合作伙伴 [：提供委派管理](https://go.microsoft.com/fwlink/p/?LinkId=532435)。

### <a name="create-the-domain-in-azure-active-directory"></a>在 Azure Active Directory 中创建域

此命令在 Azure Active Directory 中创建域，但不会将其与公开注册的域相关联。 当你向适用于企业的 Microsoft 网站证明你拥有公开注册的Microsoft 365时，这一点将出现。

```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

> [!NOTE]
> PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。 若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>获取 DNS TXT 验证记录的数据

 Microsoft 365将生成需要放入 DNS TXT 验证记录中的特定数据。 要获取数据，请运行以下命令。

```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

你将获得如下所示的输出：

 `Label: domainname.com`

 `Text: MS=ms########`

 `Ttl: 3600`

> [!NOTE]
> 你将需要此文本以在公开注册的 DNS 区域中创建 TXT 记录。 请确保将其复制并保存。

### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>在公开注册的 DNS 区域中添加 TXT 记录

在Microsoft 365接受定向到公开注册域名的流量之前，您必须证明您拥有该域并拥有该域的管理员权限。 您可通过在域中创建 TXT 记录来证明您拥有该域。 TXT 记录不会在您的域中执行任何操作，并且可以在建立您对域的所有权后删除。 若要创建 TXT 记录，请按照添加 [DNS 记录中的过程连接域](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。 如果这些步骤对您不适用，您需要查找适用于您的 DNS 注册机构的过程。

通过 nslookup 确认已成功创建 TXT 记录。遵循下面的语法。

```console
nslookup -type=TXT <FQDN of registered domain>
```

您将获得如下所示的输出：

 `Non-authoritative answer:`

 `FQDN of the registered domain`

 `text=MS=ms########`

### <a name="validate-domain-ownership-in-microsoft-365"></a>验证域中的域Microsoft 365

最后一步，验证Microsoft 365注册的域。 执行此步骤后，Microsoft 365将开始接受路由到新域名的流量。 若要完成域创建和注册过程，请运行此命令。

```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

此命令不会返回任何输出，因此要确认其有效，请运行此命令。

```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

这将返回如下所示的内容

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

## <a name="see-also"></a>另请参阅

[适用于合作伙伴的帮助](https://go.microsoft.com/fwlink/p/?LinkID=533477)
