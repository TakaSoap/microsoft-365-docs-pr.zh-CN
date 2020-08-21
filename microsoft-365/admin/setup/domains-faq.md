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
description: 通过查找常见问题的答案来了解有关域的详细信息。
ms.openlocfilehash: fe602c45059be1b273b7ebe3a11cd91adf89a479
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845840"
---
# <a name="domains-faq"></a>关于域的常见问题解答

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

本文包含 Microsoft 365 中有关域的常见问题解答。

如果找不到你问题的答案，请留下评论告知我们，我们会将其添加到列表中。

本文内容

- [什么是 MX 优先级？](#what-is-mx-priority)
- [如何验证我的域的 SPF 记录？](#how-can-i-validate-spf-records-for-my-domain)
- [什么是域名？](#what-is-a-domain-name)
- [如果我的 DNS 提供程序不支持某些记录类型，会怎种情况？](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [如何在 Microsoft 365 中设置或更改默认域？](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [能否将自定义子域或多个域添加到 Microsoft 365 中？](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [如何将域从 Microsoft 365 转移到另一个主机？](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [我为什么我具有"onmicrosoft.com"域？](#why-do-i-have-an-onmicrosoftcom-domain)
- [Why do I have an "onmicrosoft.de" domain？](#why-do-i-have-an-onmicrosoftde-domain)
- [如何验证我的非盈利或教育状态？](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>什么是 MX 优先级？

邮件将传递到首选项编号 (最高) 的邮件交换服务器，因此用于邮件路由的 MX 记录应具有最低的首选项编号（一般为 0 或  *高*  优先级）。 
  
- 创建 MX 记录时，大多数 DNS 托管提供者都需要您设置首选项号码。
    
- 某些标签将框*首选项*及某些标签的*优先级。* 
    
- 一些需要一个数字，并且某些要求您选择 *"低"、**中型*或 *"高"。* 
    
- 如果您只有一条 MX 记录，则任何值都对优先级或首选项没有匹配。
    
- 如果有多个，请确保邮件路由的 MX 记录的优先级高于验证您拥有该域所使用的 MX 记录的优先级。
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>如何验证我的域的 SPF 记录？

为 SPF，拥有或只创建一  **个 TXT 记录，这一点很重要**。 如果已有 SPF 记录，应向其附加新的 Microsoft 365 值，而不是新建一个。 添加或更新 Microsoft 电子邮件的 SPF 记录后，应检查以确保语法正确的 Microsoft 电子邮件之一： 
  
- [SPF 记录测试工具](http://www.kitterman.com/spf/validate.html)
    
- [SPF 调查器](https://dmarcian.com/spf-survey/)
    
- [Dig Web 界面](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>什么是域名？

域是 **@** 注册电子邮件地址后和 Web 地址中 **www.** 后显示的唯一名称。 它通常采用用户所在组织的名称和标准 Internet 后缀，  *如yourbusiness.com*  Internet  *后缀stateuniversity.edu。* 
  
将** \@ "rob"contoso.com"中的**自定义域用于 Microsoft 365，可帮助打造品牌信的信制和识别。 
  
可以在 [Microsoft 365 中购买某个域，并自动设置该](../get-help-with-domains/buy-a-domain-name.md)域，或者可从域注册机构购买或显示已拥有的域。
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>如果我的 DNS 提供程序不支持某些记录类型，会怎种情况？

如果管理自己的 DNS 记录但 DNS 主机不支持 Microsoft 365 所需的所有 DNS 记录，一些 Microsoft 365 功能将无效。 我们建议将您的域转移至支持所有所需 DNS 记录的注册机构。
  
支持所有所需的 DNS 记录的提供程序：
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- 悬停
    
- MyHosting.com
    
- Name.com
    
- 一下.Free Speech
    
- Nettica
    
- 网络信息中心 (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>如何在 Microsoft 365 中设置或更改默认域？

必须先具有已添加到 Microsoft 365 的至少一个自定义域，然后才能选择默认域。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。

::: moniker-end
    
2. 在 **"域** "页面上，选择要设置为新电子邮件地址的默认域。 
    
3. 选择“**设为默认值**”。
    
::: moniker range="o365-worldwide"

不能更改初始  *.onmicrosoft.com*  的名称。 

::: moniker-end

::: moniker range="o365-germany"

不能更改初始  *.onmicrosoft.de 域*  的名称。 

::: moniker-end

::: moniker range="o365-21vianet"

不能更改初始  *.partner.onmschina.cn*  域的名称。 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>能否将自定义子域或多个域添加到 Microsoft 365 中？

::: moniker range="o365-worldwide"

是。 若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。 如果您允许 Microsoft 使用 NS 记录管理 DNS 设置，或者从 Microsoft 购买了域，则不能添加子域。

::: moniker-end

::: moniker range="o365-germany"

是的！ 若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。 如果您允许 Microsoft 使用 NS 记录管理 DNS 设置，或者从 Microsoft 购买了域，则不能添加子域。

::: moniker-end

::: moniker range="o365-21vianet"

是的！ 若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。 如果让世纪互联使用 NS 记录管理 DNS 设置，则无法添加子域。

::: moniker-end

通常，最多可以将 900 个域添加到 Microsoft 365 订阅中。
  
例如，可以添加域contoso.com和contosomarketing.com，然后添加子域www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com，等等。
  
添加子域后，系统会自动验证该子域，该子域将基于正在验证的父域进行验证。
  
当你将多个域添加到 Microsoft 365 时，可在已添加的任何 (托管任何服务，例如电子邮件) 。  *当将电子邮件更改为 Microsoft 365 时，发送至该域的所有电子邮件都将开始传送到 Microsoft 365。* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> 如果已将contoso.com域添加到 Microsoft 365 订阅，还可以将子域xyz.contoso.com添加到另一个 Microsoft 365 组织。 添加子域时，系统会提示您在 DNS 托管提供者中添加 TXT 记录。

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a>如何将域从 Microsoft 365 转移到另一个主机？

有关域传输的过程，请参阅将 [域从 Microsoft 转移至另一主机](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host)。

## <a name="pilot-microsoft-365-from-my-custom-domain"></a>从我的自定义域试点 Microsoft 365

有关从自定义域到 Microsoft 365 邮箱的试验 Microsoft 365 电子邮件功能的过程，请参阅["从我的自定义域试用 Microsoft 365"。](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain)

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>我为什么我具有"onmicrosoft.com"域？

Microsoft 365 会在你登录 *服务时contoso.onmicrosoft.com*为你创建一个域，例如有效。 注册时创建的用户 ID 包括域，如*alan@contoso.onmicrosoft.com。* 
  
 **如果想要让电子邮件看起来*像是 \@ contoso.com：***[购买](../get-help-with-domains/buy-a-domain-name.md)域，或按照先拥有将用户和[域添加到 Microsoft 365](add-domain.md)中的步骤进行操作。 
  
- **注册后，不可重命名 onmicrosoft 域。** 例如，如果选择的初始域是fourthcoffee.onmicrosoft.com的，则不能将其更改为fabrikam.onmicrosoft.com。 若要使用其他onmicrosoft.com Microsoft 365 的新订阅。 
    
- **无法重命名团队网站 URL。** 你的团队网站 URL 基于您的onmicrosoft.com域名。 遗遗弃的原因在于 SharePoint Online 体系结构的工作方式，你不能重命名团队网站。 
    
- **不能删除你的 onmicrosoft 域。** Microsoft 365 需要保留以防其周围，因为它在订阅后台使用。 但是，在添加自定义域之后，您不必自己使用此域。 
    
即使在添加域后onmicrosoft.com使用初始服务域。 它仍然适用于电子邮件和其他服务，因此您可以选择它。
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Why do I have an "onmicrosoft.de" domain？

Microsoft 365 在你注册服务 *时contoso.onmicrosoft.de*为你创建一个域，例如应用程序。 注册时创建的用户 ID 包括域，*如域alan@contoso.onmicrosoft.de。* 
  
 **如果想要让电子邮件看起来*alan@contoso.de：***[购买](../get-help-with-domains/buy-a-domain-name.md)域"，或按照"[将用户和域添加到 Microsoft 365"中](add-domain.md)步骤进行操作（如果你已拥有它）。 
  
- **注册后，不可重命名 onmicrosoft 域。** 例如，如果选择的初始域是fourthcoffee.onmicrosoft.de的，则不能将其更改为是你fabrikam.onmicrosoft.de。 若要使用其他onmicrosoft.de Microsoft 365 的新订阅。 
    
- **无法重命名团队网站 URL。** 您的团队网站 URL 基于您的onmicrosoft.de域名。遗遗弃的原因在于 SharePoint Online 体系结构的工作方式，你不能重命名团队网站。 
    
- **不能删除你的 onmicrosoft 域。** Microsoft 365 需要保留以防其周围，因为它在订阅后台使用。 但是，在添加自定义域之后，您不必自己使用此域。 
    
即使在添加域之后onmicrosoft.de开始使用初始服务。 它仍然适用于电子邮件和其他服务，因此您可以选择它。
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>如何验证我的非盈利或教育状态？

1. 在 **管理中心** 选择 ["设置"](https://docs.microsoft.com/microsoft-365/admin/admin-home) 启动向导。  (请务必先登录 Microsoft 365 )  
    
2. 若要成为学校管理员，请在 Microsoft 365  **中选择** "成为管理员"选项。 
    
3. 系统将提示你在 DNS 主机网站为你的域添加 TXT DNS 记录。 为什么？ 由于通过在 DNS 主机上登录并为你的域添加记录，就可以向 Microsoft 365 证明你拥有该域名。
    
4. 添加记录后，你将恢复 Microsoft 365 门户，并确认你已添加它，以便 Microsoft 365 进行检查。
    
有非营利组织建议，想要获取 Microsoft 365？ [请确保你的组织有限定](https://www.microsoft.com/en-us/nonprofits/eligibility) 并注册服务。 
  
想要详细了解你所在学校的管理员？ [全部了解](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。