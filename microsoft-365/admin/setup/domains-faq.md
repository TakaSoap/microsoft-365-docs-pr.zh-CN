---
title: 常见的域常见问题
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
- seo-marvel-may2020
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: 通过在 FAQ 中查找问题的答案，了解有关域 (.onmicrosoft 域和传输域) 的详细信息。
ms.openlocfilehash: 8d504711f46383000697736d6825a813f01fbe69
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906473"
---
# <a name="domains-faq"></a>关于域的常见问题解答

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview)。

::: moniker-end

本文包含有关 Microsoft 365 中的域的常见问题的解答。

如果找不到你问题的答案，请留下评论告知我们，我们会将其添加到列表中。

本文内容

- [什么是 MX 优先级？](#what-is-mx-priority)
- [如何验证我的域的 SPF 记录？](#how-can-i-validate-spf-records-for-my-domain)
- [什么是域名？](#what-is-a-domain-name)
- [如果我的 DNS 提供商不支持某些记录类型，会发生什么情况？](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [如何在 Microsoft 365 中设置或更改默认域？](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [是否可以将自定义子域或多个域添加到 Microsoft 365？](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [如何将域从 Microsoft 365 传输到另一台主机？](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [为什么我有 "onmicrosoft.com" 域？](#why-do-i-have-an-onmicrosoftcom-domain)
- [为什么我有 "onmicrosoft.de" 域？](#why-do-i-have-an-onmicrosoftde-domain)
- [如何验证我的非盈利或教育状态？](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>什么是 MX 优先级？

邮件传递到最低首选项编号 (最高优先级) 的邮件 exchange 服务器，因此用于邮件路由的 MX 记录应具有最低的首选数量（通常为0或  *高*  优先级）。 
  
- 创建 MX 记录时，大多数 DNS 承载提供程序都要求您设置首选项号码。
    
- 部分标签 "box"  *首选项*  ，并为其添加标签  *优先级*  。 
    
- 有些用户需要一个数字，有些要求您选择 "  *低*  "、"  *中*  " 或 "  *高*  "。 
    
- 如果您只有一个 MX 记录，则优先级或首选项的任何值都是很好的。
    
- 如果您有多个，请确保邮件路由的 MX 记录的优先级高于用于验证您拥有该域的用户的路径。
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>如何验证我的域的 SPF 记录？

必须具有或  **仅为 SPF 创建一个 TXT 记录** ，这一点非常重要。 如果已有 SPF 记录，则应向其追加新的 Microsoft 365 值，而不是创建一个新的。 在添加或更新了 Microsoft 电子邮件的 SPF 记录后，应进行检查以确保使用以下工具之一时的语法正确： 
  
- [SPF 记录测试工具](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- ["挖出 web 界面"](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>什么是域名？

域是 **@** 注册电子邮件地址后和 Web 地址中 **www.** 后显示的唯一名称。 它通常采用您组织的名称和标准 Internet 后缀的形式，如  *yourbusiness.com*  或  *stateuniversity.edu。* 
  
将自定义域（如 " **\@ contoso.com** "）与 Microsoft 365 结合使用，可以帮助为你的品牌建立可信度和认可。 
  
你可以 [在 Microsoft 365 中购买域，我们将自动对其进行设置](../get-help-with-domains/buy-a-domain-name.md)，也可以从域注册机构购买或将已有的域引入。
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>如果我的 DNS 提供商不支持某些记录类型，会发生什么情况？

如果您管理自己的 DNS 记录，并且 DNS 主机不支持 Microsoft 365 需要的所有 DNS 记录，则某些 Microsoft 365 功能将不起作用。 我们建议您将您的域转移到支持所有必需的 DNS 记录的注册器。
  
支持所有必需的 DNS 记录的提供程序：
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- 悬停
    
- MyHosting.com
    
- Name.com
    
- 几乎免费的语音
    
- Nettica
    
- 网络信息中心 (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>如何在 Microsoft 365 中设置或更改默认域？

您必须至少有一个添加到 Microsoft 365 的自定义域，然后才能选择默认域。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“ **设置** ”\>“ <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“ **设置** ”>“ <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“ **设置** ”>“ <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。

::: moniker-end
    
2. 在 " **域** " 页上，选择要将其设置为新电子邮件地址的默认域的域。 
    
3. 选择“ **设为默认值** ”。
    
::: moniker range="o365-worldwide"

您不能更改  *onmicrosoft.com*  域的名称。 

::: moniker-end

::: moniker range="o365-germany"

您不能更改  *onmicrosoft.de*  域的名称。 

::: moniker-end

::: moniker range="o365-21vianet"

您不能更改  *partner.onmschina.cn*  域的名称。 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>是否可以将自定义子域或多个域添加到 Microsoft 365？

::: moniker range="o365-worldwide"

是。 若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。 如果要让 Microsoft 管理具有 NS 记录的 DNS 设置，或者如果您从 Microsoft 购买了域，则无法添加子域。

::: moniker-end

::: moniker range="o365-germany"

是的！ 若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。 如果要让 Microsoft 管理具有 NS 记录的 DNS 设置，或者如果您从 Microsoft 购买了域，则无法添加子域。

::: moniker-end

::: moniker range="o365-21vianet"

是的！ 若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。 如果您正在让世纪管理具有 NS 记录的 DNS 设置，则不能添加子域。

::: moniker-end

通常情况下，最多可以向 Microsoft 365 订阅添加900个域。
  
例如，可以添加域 contoso.com 和 contosomarketing.com，然后添加子域 www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com 等等。
  
添加子域时，将根据正在验证的父域自动对其进行验证。
  
将多个域添加到 Microsoft 365 时，可以在添加的任何域中承载电子邮件)  (之类的任何服务。  *当您将电子邮件更改为 Microsoft 365 时，通过更新域的 MX 记录，发送到该域的所有电子邮件都将开始进入 Microsoft 365。* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> 如果向 Microsoft 365 订阅添加了 contoso.com 域，您还可以将子域 xyz.contoso.com 添加到另一个 Microsoft 365 组织。 添加子域时，系统会提示您在 DNS 托管提供程序中添加 TXT 记录。

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a>如何将域从 Microsoft 365 传输到另一台主机？

有关转移域的过程，请参阅将 [域从 Microsoft 转移到另一台主机](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host)。

## <a name="pilot-microsoft-365-from-my-custom-domain"></a>从我的自定义域试点 Microsoft 365

有关从自定义域到 Microsoft 365 邮箱的试点 Microsoft 365 电子邮件功能的过程，请参阅 [试点 microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain)。

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>为什么我有 "onmicrosoft.com" 域？

当您注册服务时，Microsoft 365 将为您创建一个域，如 *contoso.onmicrosoft.com* 。 注册时创建的用户 ID 包括域，如 *alan@contoso.onmicrosoft.com* 。 
  
 **如果您想让您的电子邮件看起来像 *alan \@ contoso.com* ：** [购买域](../get-help-with-domains/buy-a-domain-name.md) ，或者只需按照 " [将用户和域添加到 Microsoft 365](add-domain.md) " 中的步骤（如果已将其拥有）。 
  
- **注册后，不能重命名 .onmicrosoft 域。** 例如，如果您选择的初始域是 "fourthcoffee.onmicrosoft.com"，则不能将其更改为 "fabrikam.onmicrosoft.com"。 若要使用不同的 onmicrosoft.com 域，您必须启动一个使用 Microsoft 365 的新订阅。 
    
- **您不能重命名团队网站 URL。** 您的团队网站 URL 基于您的 onmicrosoft.com 域名。 遗憾的是，由于 SharePoint Online 体系结构的工作方式，无法重命名团队网站。 
    
- **您不能删除您的 .onmicrosoft 域。** Microsoft 365 需要将其保留，因为它在你的订阅的幕后使用。 但在添加自定义域之后，您无需自己使用域。 
    
即使在添加了域之后，也可以继续使用初始 onmicrosoft.com 域。 它仍适用于电子邮件和其他服务，因此是你的选择。
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>为什么我有 "onmicrosoft.de" 域？

当您注册服务时，Microsoft 365 将为您创建一个域，如 *contoso.onmicrosoft.de* 。 注册时创建的用户 ID 包括域，如 *alan@contoso.onmicrosoft.de* 。 
  
 **如果您想让您的电子邮件看起来像 *alan@contoso.de* ：** [购买域](../get-help-with-domains/buy-a-domain-name.md) ，或者只需按照 " [将用户和域添加到 Microsoft 365](add-domain.md) 中的步骤" 中的步骤。如果你已拥有它。 
  
- **注册后，不能重命名 .onmicrosoft 域。** 例如，如果您选择的初始域是 "fourthcoffee.onmicrosoft.de"，则不能将其更改为 "fabrikam.onmicrosoft.de"。 若要使用不同的 onmicrosoft.de 域，您必须启动一个使用 Microsoft 365 的新订阅。 
    
- **您不能重命名团队网站 URL。** 您的团队网站 URL 基于您的 onmicrosoft.de 域名。遗憾的是，由于 SharePoint Online 体系结构的工作方式，无法重命名团队网站。 
    
- **您不能删除您的 .onmicrosoft 域。** Microsoft 365 需要将其保留，因为它在你的订阅的幕后使用。 但在添加自定义域之后，您无需自己使用域。 
    
即使在添加了域之后，也可以继续使用初始 onmicrosoft.de 域。 它仍适用于电子邮件和其他服务，因此是你的选择。
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>如何验证我的非盈利或教育状态？

1. 在 [管理中心](https://docs.microsoft.com/microsoft-365/admin/admin-home)中选择 " **设置** " 以启动向导。  (务必先登录到 Microsoft 365。 )  
    
2. 若要成为你的学校的管理员，请选择 "在 Microsoft 365 中  **成为管理员** " 选项。 
    
3. 系统将提示你在你的域的 DNS 主机网站上添加 TXT DNS 记录。 为什么？ 由于通过在 DNS 主机上登录并为你的域添加记录，你可以向 Microsoft 365 证明你拥有此域名。
    
4. 添加记录后，您将返回到 Microsoft 365 门户，并确认您已添加它，以便 Microsoft 365 可以进行检查。
    
是否有非盈利的，想要获取 Microsoft 365？ [请确保您的组织符合](https://www.microsoft.com/en-us/nonprofits/eligibility) 条件，然后注册服务。 
  
想要了解有关成为你的学校的管理员的详细信息吗？ [了解相关信息](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。
