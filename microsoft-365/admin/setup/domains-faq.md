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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: 通过在 FAQ 中查找问题的答案，了解有关域的详细信息。
ms.custom: okr_smb
ms.openlocfilehash: 09e811b64def4d507a9d825f95b9d22f910669bb
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140745"
---
# <a name="domains-faq"></a>关于域的常见问题解答

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理员中心正在更改。 如果你的体验与此处提供的详细信息不匹配，请参阅[关于新的 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

本文包含有关 Office 365 中的域的常见问题的解答。

如果找不到你问题的答案，请留下评论告知我们，我们会将其添加到列表中。
    
## <a name="what-is-mx-priority"></a>什么是 MX 优先级？

邮件传递到具有最低首选项号码（最高优先级）的邮件 exchange 服务器，因此用于邮件路由的 MX 记录的首选项数量（通常为0或*高*优先级）应最低。 
  
- 创建 MX 记录时，大多数 DNS 承载提供程序都要求您设置首选项号码。
    
- 部分标签 "box"*首选项*，并为其添加标签*优先级*。 
    
- 有些用户需要一个数字，有些要求您选择 "*低*"、"*中*" 或 "*高*"。 
    
- 如果您只有一个 MX 记录，则优先级或首选项的任何值都是很好的。
    
- 如果您有多个，请确保邮件路由的 MX 记录的优先级高于用于验证您拥有该域的用户的路径。
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>如何验证我的域的 SPF 记录？

必须具有或**仅为 SPF 创建一个 TXT 记录**，这一点非常重要。 如果已有 SPF 记录，则应向其追加新的 Office 365 值，而不是创建一个新的。 在添加或更新了 Microsoft 电子邮件的 SPF 记录后，应进行检查以确保使用以下工具之一时的语法正确： 
  
- [SPF 记录测试工具](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- ["挖出 web 界面"](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>Office 365 如何管理我的 DNS 记录？

有两个选项可用于使用 Office 365 的 DNS 管理：
  
1. 您可以更改您的名称服务器（NS）记录，然后 Microsoft 会处理所有服务特定的记录，如设置电子邮件的 MX 记录。 **适合**
    
2. 您可以在 DNS 主机上添加电子邮件和其他 Office 365 服务的 DNS 记录。 **（仅限专家）**
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>Office 365 创建并托管 DNS 记录 
**优点** 
- 您无需担心在为 Office 365 服务的 DNS 记录输入的值中出现错误。  
- 您选择的域注册机构和 DNS 主机具有更大的灵活性。 
- 只要提供程序不支持所有必需的记录类型，任何允许您更改你的名称服务器记录的提供程序都能正常工作。   
- 如果 Office 365 添加了新的 DNS 记录，则无需进行更新。  

#### <a name="disadvantages"></a>缺点 
- 您不能将 DNS 记录更改为托管在 Office 365 之外的电子邮件。 
- 如果您已将公共网站与您的域一起使用，如 www.fourthcoffee.com，则必须将用户重定向到 Office 365 中的该地址。 
- 设置重定向需要静态 IP 地址，这对公共网站来说并不总是很容易使用。 -如果当前的域注册机构不允许更改域的名称服务器记录，则必须切换到不同的注册器，才能使用此 DNS 管理选项。  

 ### <a name="you-manage-the-dns-records-yourself"></a>您自己管理 DNS 记录 
 #### <a name="advantages"></a>优点
- 您可以控制 Office 365 服务的 DNS 记录。   
- 如果您有一个包含域的公共网站（如 www.fourthcoffee.com），则无需担心如何使用重定向来确保用户在 Office 365 中设置域后仍可访问您的网站。    
- 您可以灵活地将电子邮件托管在其他位置，如本地 Exchange 服务器。  
 
#### <a name="disadvantages"></a>缺点
您必须自己设置适用于 Office 365 服务的 DNS 记录（除非您有 GoDaddy 域）。 
-  如果当前 DNS 主机不支持 Microsoft 365 的所有必需的记录类型，则某些功能将不可用，您可能需要切换到其他 DNS 主机。 
- 当 Office 365 更改 DNS 记录的要求或添加新服务时，您必须在 DNS 主机上自己进行更新。 
   
## <a name="what-is-a-domain-name"></a>什么是域名？


域是 **@** 注册电子邮件地址后和 Web 地址中 **www.** 后显示的唯一名称。 它通常采用您组织的名称和标准 Internet 后缀的形式，如*yourbusiness.com*或*stateuniversity.edu。* 
  
将自定义域（**如 "\@contoso.com"）** 与 Office 365 结合使用，可以帮助为你的品牌建立可信度和认可。 
  
你可以[在 Office 365 中购买域，我们将自动对其进行设置](../get-help-with-domains/buy-a-domain-name.md)，也可以从域注册机构购买或将已有的域引入。
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>是否可以将从 Microsoft 那里购买的域转移到另一个提供商？

可以，但在购买 Office 365 后的60天后，不能将 Office 365 域传输到另一个注册机构。

请注意， *Whois*查询会将作为通配符的 Office 365 购买的域注册器显示为 "中西部域" LLC。 但是，应仅与 Office 365 购买域联系，以了解有关 office 365 的事宜。
  
按照以下步骤获取 Office 365 中的代码，然后转到其他域注册机构的网站以设置将您的域名转移到该注册器。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在 "管理中心" 中，转到 "**设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">许可证</a>" 页。

::: moniker-end
    
2. 在 "**域**" 页上，选择要转移到其他域注册机构的 Office 365 域，然后选择 "**域传输** > **启用域传输**"。
       
4. 按照准备转移您的域的步骤进行操作。
    
5. 在获取代码之后，转到域注册机构的网站，您想要提前管理您的域名，并按照其传输域的指导进行操作（在其网站上搜索帮助）。
    
6. 如果需要再次查看该代码，请在 Office 365 中的 "**域设置**" 页上，选择 "**查看域传输的授权代码**"。
    
7. 传输完成后，你将在新域注册机构中续订你的域。
    
8. 若要完成此过程，请返回到管理中心**域**页面，并选择 "**完成域传输**"。 

*注意：请注意，Office 365 购买的域不符合名称服务器更改或在 Office 365 租户之间传输域的情况。 如果需要其中任一项，则需要将域注册转移到其他注册器。*
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a>如何更改我的 DNS 记录在 Office 365 中的管理方式？

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a>将 DNS 管理更改为 Office 365 之外的 DNS 主机
   
1. 登录到您的域的域注册机构。
    
2. 在注册器网站上查找您更新 nameserver 记录的区域，并更新名称服务器以指向您的域的 DNS 主机。 （DNS 主机通常是域注册机构。）
    
3. 按照链接转到域安装向导：

::: moniker range="o365-worldwide"

4. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

4. 在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

4. 在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。

::: moniker-end
    
5. 在 "**域**" 页上，选择要切换的域，然后选择 " **DNS 管理**"。
    
6. 在 "域安装向导" 的 "**设置联机服务**" 页上，选择 "**我将管理自己的 DNS 记录**"，然后选择 "**下一步**"。
    
7. 将向导建议的 DNS 记录添加到你的注册机构网站的 "**更新 DNS 设置**" 页上。 
    
8. 添加记录后，返回到 Office 365 并选择 "**验证**"。
    

### <a name="change-dns-management-to-office-365"></a>将 DNS 管理更改为 Office 365

::: moniker range="o365-worldwide"

1. 在管理中心中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。

::: moniker-end
    
2. 在 "**域**" 页上，选择要切换的域，然后选择 " **DNS 管理**"。
    
3. 在 "域设置向导" 的 "**设置联机服务**" 页上，选择 "**设置我的联机服务"。（推荐）**，然后选择 "**下一步**"。
    
4. 如果尚未验证域，请按照第一步操作。
    
5. 在 "**更新 DNS 设置**" 页上，列出了 Office 365 的名称服务器。 转到域的域注册机构，并将名称服务器更新为 Office 365 名称服务器。 
    
4. 更新名称服务器后，请**至少等待一小时**。 然后，返回到 Office 365 中的向导，选择 "**验证**"。
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>如果我的 DNS 提供商不支持某些记录类型，会发生什么情况？

如果您管理自己的 DNS 记录，并且 DNS 主机不支持 Office 365 所需的所有 DNS 记录，则某些 Office 365 功能将不起作用。 我们建议您将您的域转移到支持所有必需的 DNS 记录的注册器。
  
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
    
 **如果不支持 SRV 记录**，以下 Office 365 功能将不可用： 
  
- Skype for business Online IM 和状态与 Outlook Web App 的集成
    
- 其他组织中与 Skype for Business Online 用户的外部通信（联合）。
    
- 使用 Microsoft 帐户（以前称为 Windows Live ID）登录的 Skype for Business Online 用户的公共 Internet 连接（PIC）。
    
 **如果不支持多个 CNAME 记录，** 则必须在 Skype For business Online 的以下功能之间进行选择： 
  
- 电子邮件桌面客户端和移动客户端可以使用自动发现自动查找 Exchange Online 服务，以便用户无需输入服务器名称即可登录。
    
- Skype for Business Online 桌面客户端可以使用自动发现自动查找 Skype for Business Online 服务，以便用户无需输入服务器名称即可登录。
    
- Skype for Business Online 移动客户端可以使用自动发现来自动查找 Skype for Business Online 服务，以便用户无需输入服务器名称即可登录。
    
 **如果 SPF/TXT 记录不受支持，则**其他人可能可以使用您的域发送垃圾邮件或其他恶意电子邮件。 SPF 记录通过识别授权从您的域发送电子邮件的服务器来发挥作用。 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a>如何设置或更改 Office 365 中的默认域？

您必须至少有一个添加到 Office 365 的自定义域，然后才能选择默认域。

::: moniker range="o365-worldwide"

1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-germany"

1. 在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>”页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在管理中心，转到“**设置**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>”页面。

::: moniker-end
    
2. 在 "**域**" 页上，选择要将其设置为新电子邮件地址的默认域的域。 
    
3. 选择“**设为默认值**”。
    
::: moniker range="o365-worldwide"

您不能更改*onmicrosoft.com*域的名称。 

::: moniker-end

::: moniker range="o365-germany"

您不能更改*onmicrosoft.de*域的名称。 

::: moniker-end

::: moniker range="o365-21vianet"

您不能更改*partner.onmschina.cn*域的名称。 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a>我可以将自定义子域或多个域添加到 Office 365 吗？

::: moniker range="o365-worldwide"

是的！ 若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。 如果要让 Microsoft 管理具有 NS 记录的 DNS 设置，或者如果您从 Microsoft 购买了域，则无法添加子域。

::: moniker-end

::: moniker range="o365-germany"

是的！ 若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。 如果要让 Microsoft 管理具有 NS 记录的 DNS 设置，或者如果您从 Microsoft 购买了域，则无法添加子域。

::: moniker-end

::: moniker range="o365-21vianet"

是的！ 若要添加子域，必须在注册机构的网站上管理自己的 DNS 设置。 如果您正在让世纪管理具有 NS 记录的 DNS 设置，则不能添加子域。

::: moniker-end

通常情况下，最多可以向 Office 365 订阅添加900个域。
  
例如，可以添加域 contoso.com 和 contosomarketing.com，然后添加子域 www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com 等等。
  
添加子域时，将根据正在验证的父域自动对其进行验证。
  
将多个域添加到 Office 365 时，可以在已添加的任何域中承载任何服务（如电子邮件）。  *当您将电子邮件更改为 Office 365 时，通过更新域的 MX 记录，发送到该域的所有电子邮件都将开始进入 Office 365。* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> 如果您已向 Office 365 租户添加了 contoso.com 域，您还可以将子域 xyz.contoso.com 添加到另一个 Office 365 租户。 添加子域时，系统将提示您在 DNS 托管提供程序中添加 TXT 记录。

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>为什么我有 "onmicrosoft.com" 域？

当您注册服务时，Office 365 将为您创建一个域，如*contoso.onmicrosoft.com*。 注册时创建的用户 ID 包括域，如*alan@contoso.onmicrosoft.com*。 
  
 **如果您想让您的电子邮件看起来像*alan\@contoso.com*：** [购买域](../get-help-with-domains/buy-a-domain-name.md)，或者只需按照 "[将用户和域添加到 Office 365](add-domain.md)中的步骤" 中的步骤，如果您已拥有它。 
  
- **注册后，不能重命名 .onmicrosoft 域。** 例如，如果您选择的初始域是 "fourthcoffee.onmicrosoft.com"，则不能将其更改为 "fabrikam.onmicrosoft.com"。 若要使用不同的 onmicrosoft.com 域，必须启动一个使用 Office 365 的新订阅。 
    
- **您不能重命名团队网站 URL。** 您的团队网站 URL 基于您的 onmicrosoft.com 域名。 遗憾的是，由于 SharePoint Online 体系结构的工作方式，无法重命名团队网站。 
    
- **您不能删除您的 .onmicrosoft 域。** Office 365 需要将其保留，因为它在你的订阅的幕后使用。 但在添加自定义域之后，您无需自己使用域。 
    
即使在添加了域之后，也可以继续使用初始 onmicrosoft.com 域。 它仍适用于电子邮件和其他服务，因此是你的选择。
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>为什么我有 "onmicrosoft.de" 域？

当您注册服务时，Office 365 将为您创建一个域，如*contoso.onmicrosoft.de*。 注册时创建的用户 ID 包括域，如*alan@contoso.onmicrosoft.de*。 
  
 **如果您想让您的电子邮件看起来像*alan@contoso.de*：** [购买域](../get-help-with-domains/buy-a-domain-name.md)，或者只需按照[将用户和域添加到 Office 365](add-domain.md)中的步骤（如果您已拥有它）。 
  
- **注册后，不能重命名 .onmicrosoft 域。** 例如，如果您选择的初始域是 "fourthcoffee.onmicrosoft.de"，则不能将其更改为 "fabrikam.onmicrosoft.de"。 若要使用不同的 onmicrosoft.de 域，必须启动一个使用 Office 365 的新订阅。 
    
- **您不能重命名团队网站 URL。** 您的团队网站 URL 基于您的 onmicrosoft.de 域名。遗憾的是，由于 SharePoint Online 体系结构的工作方式，无法重命名团队网站。 
    
- **您不能删除您的 .onmicrosoft 域。** Office 365 需要将其保留，因为它在你的订阅的幕后使用。 但在添加自定义域之后，您无需自己使用域。 
    
即使在添加了域之后，也可以继续使用初始 onmicrosoft.de 域。 它仍适用于电子邮件和其他服务，因此是你的选择。
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>如何验证我的非盈利或教育状态？

1. 在[管理中心](https://docs.microsoft.com/microsoft-365/admin/admin-home)中选择 "**设置**" 以启动向导。 （请务必先登录到 Office 365。） 
    
2. 若要成为你的学校的管理员，请选择 "在 Office 365 中**成为管理员**" 选项。 
    
3. 系统将提示你在你的域的 DNS 主机网站上添加 TXT DNS 记录。 为什么？ 由于通过在 DNS 主机上登录并为您的域添加记录，因此您可以向 Office 365 证明您拥有此域名。
    
4. 添加记录后，您将返回到 Office 365 门户，并确认您已添加它，以便 Office 365 可以进行检查。
    
是否有非盈利的，希望获取 Office 365？ [请确保您的组织符合](https://www.microsoft.com/en-us/nonprofits/eligibility)条件，然后注册服务。 
  
想要了解有关成为你的学校的管理员的详细信息吗？ [了解相关信息](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>是否可以使用自定义域中的几个电子邮件地址来试点生产 Office 365？

您可以，但有一些限制：
  
- 您当前的电子邮件提供商必须提供电子邮件转发。
    
- 您需要在 DNS 托管提供商处管理与 Office 365 相关的 DNS 记录，而不是让 Office 365 为您管理这些记录。 若要了解这需要什么，请参阅当你想要管理自己的 DNS 记录时，将你的域添加到 Office 365。
    
- 某些 Office 365 功能将不可用：
- 用户将无法查看其他电子邮件提供商的用户的忙/闲信息。
- 管理员将无法从一个位置管理每个人的帐户。
- 用户可能无法使用 Office 365 垃圾邮件筛选

### <a name="how-to-set-up-an-office-365-pilot"></a>如何设置 Office 365 试点
    
1. 登录到 Microsoft 365 管理中心
    
    1. 使用工作或学校帐户登录 Office 365。
        
    2. 转到 "**设置** \> **域**"。 
    
2. 验证您是否拥有要使用的域
    
    1. 在 "**域**" 页上，选择 "**添加域**"。 
        
    2. 在面板中，键入域（在此示例中为 cohowinery.com），然后选择 "**下一步**"。 
        
    3. 在 "**验证**域" 页上，按照分步说明操作。 
        
    4. 在下拉列表中，选择您的 DNS 托管提供商，然后按照说明操作以表明您拥有该域。
        
    5. 选择 "**验证**"。 要使 DNS 更改生效，需要几分钟和72小时的时间。 
        
    6. 验证成功后，系统将要求你修改 DNS 记录。
    
3. 将域标记为在 Exchange Online 中共享
    
    1. 转到**Exchange 管理中心**（EAC）。 
        
    2. 在 "**邮件流**" 部分，选择 "**接受域**"。 
        
    3. 双击要修改的域。
        
    4. 在打开的窗口中，选择 "**内部中继**"。 
        
    5. 选择“保存”****。 此设置可能需要几分钟时间才能生效。 
    
4. （可选）取消阻止现有的电子邮件服务器
    
    1. Office 365 使用 Exchange Online Protection （EOP）进行垃圾邮件保护。 如果 EOP 检测到当前邮件服务器要转发的大量垃圾邮件，则可能会阻止邮件，从而阻止转发工作。 如果你确信其他电子邮件提供商使用的垃圾邮件保护，则可以在 Office 365 中对其服务器进行白名单。 但是，这还将允许通过原始服务器到达的所有垃圾邮件进入 Office 365 邮箱，并且您无法评估 Office 365 如何防止垃圾邮件。
    
    2. 转到 Exchange 管理中心（EAC）。
        
    3. 在 EAC 中，选择 "**保护**"，然后选择 "**连接筛选器**"。 
        
    4. 在 " **IP 允许" 列表**中**+**，选择 ""，然后添加可以从当前电子邮件提供商获取的邮件服务器 IP 地址。 
    
5. 创建用户帐户并设置主（答复）地址
    
    1. 转到 Microsoft 365 管理中心。
        
    2. 在左侧导航栏上，选择 "**用户** \> **活动用户**"。 
        
    3. 创建用户帐户。
        
    4. 对于每个帐户，请选择 " **+ （新建）**"，然后填写所需的信息。 
        
    5. 若要使用户的电子邮件与当前的电子邮件相同，**用户名**字段应与用户现有的电子邮件地址完全相同。 
        
    6. 在 "用户名" 旁边的下拉列表中，选择您的自定义域名称。
        
    7. 选择 "**创建** \> **关闭**"。 
        
6. 在 DNS 托管提供程序中更新 DNS 记录
    
    1. 登录到您的 DNS 托管提供商的网站，并在[任何 dns 托管提供商处遵循适用于 Office 365 步骤的 CREATE DNS 记录](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。 **请进行以下异常：**
    
        1. 不要创建新的 MX 记录或更改现有的 MX 记录。
            
        2. 如果您以前的电子邮件提供商已经有一个发件人策略框架（SPF）记录，而不是为 Exchange Online 创建新的 SPF （TXT）记录，则只需将 "include include spf.protection.outlook.com" 添加到当前的 TXT 记录。 例如，"v = spf1 mx 包括:adatum，其中包括 include spf.protection.outlook.com ~ all"。
            
        3. 如果您尚未安装 SPF 记录，请修改 Office 365 建议的项，以包含当前电子邮件提供程序的域以及 spf.protection.outlook.com。 这将从这两个电子邮件系统中授权出传出邮件。
            
7. 在当前提供商处设置电子邮件转发
    
    1. 在当前电子邮件提供商处，为您的用户电子邮件帐户设置到您的 onmicrosoft.com 域的转发：
        
    2. 用户 A 的邮箱应转发到 usera@yourcompany.onmicrosoft.com
        
    3. 用户 B 的邮箱应转发到 userb@yourcompany.onmicrosoft.com
        
    4. 完成此步骤时：
        
    5. 发送到 usera@yourcompany.com 和 userb@yourcompany.com 的所有邮件将在 Office 365 中提供。
    
    6. 注意：
        
        - 有关设置转发的确切步骤，请与当前的电子邮件提供商联系。
            
        - 您无需在当前电子邮件提供程序中保留邮件的副本。
            
        - 大多数提供程序将转发电子邮件，使发件人的答复地址保持不变，以便回复转到原始发件人。
    
8. 测试邮件流
    
    1. 使用用户 A 的凭据登录到 Outlook Web App。
        
    2. 执行以下测试：
        
    3. 测试本地 Microsoft 电子邮件。 例如，向用户 B 发送电子邮件。应立即传递此电子邮件。 在这种情况下，将不会将邮件路由到原始服务器上的用户 B 的邮箱，因为 Office 365 将该邮箱视为本地邮箱。
        
    4. 将电子邮件测试给其他电子邮件系统上的人。 例如，将电子邮件发送到用户 C。应将此电子邮件传递到原始邮件服务器上的用户 C 邮箱。
        
    5. 从外部帐户或从其他电子邮件系统上的员工电子邮件帐户中，验证是否在其他电子邮件系统上正确设置了转发。 例如，在用户 C 的原始服务器帐户或 Hotmail 帐户中，向用户发送一封电子邮件，并验证它是否到达用户 A 的 Office 365 邮箱。
        
9. 移动邮箱内容
    
    1. 由于只有两个用户需要移动，并且由于用户 A 和用户 B 都使用 Outlook，因此可以通过打开旧电子邮件移动电子邮件。PST 文件，然后复制邮件、日历项目、联系人等内容，如 Outlook 数据文件（.pst）中的 "导入 Outlook 项目" 中所示。 在 Office 365 邮箱中的正确位置进行组织后，可以从任何位置通过任何设备访问这些项目。
        
    2. 当涉及更多邮箱或员工尚未使用 Outlook 时，您可以使用 Exchange 管理中心提供的迁移工具。 若要开始，请转到 Exchange 管理中心，并按照将电子邮件从 IMAP 服务器迁移到 Exchange Online 邮箱中的说明进行操作。
    
