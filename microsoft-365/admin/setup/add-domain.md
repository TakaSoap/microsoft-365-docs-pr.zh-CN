---
title: 将域添加到 Office 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: 通过在 DNS 主机上添加 DNS 记录，将您的域添加到 Microsoft 365 管理中心中的 Office 365。 安装向导将引导您完成该过程。
ms.openlocfilehash: 336e6ee78d7020d73c7e00f639e8f1e1b20c62cd
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222335"
---
# <a name="add-a-domain-to-microsoft-365"></a>将域添加到 Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

 如果找不到要查找的内容，请**[查看域常见问题解答](domains-faq.md)**。 
  
 *若要添加、修改或删除域，您**必须**是[企业或企业计划](https://products.office.com/business/office)的**全局管理员**。这些更改会影响整个租户、*自定义管理员*或*常规用户*无法进行这些更改。*  

 按照以下步骤添加、设置或继续设置域。 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。

::: moniker-end
::: moniker range="o365-germany"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。

::: moniker-end

::: moniker range="o365-21vianet"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。

::: moniker-end
    
2. 转到 "**安装**  >  **域**" 页。 

3. 选择 "**添加域**"。
    
4. 输入要添加的域的名称，然后选择 "**下一步**"。
    
5. 选择要验证您是否拥有域的方式。
    
    1. 如果你的域是在 GoDaddy 或 1 &amp; 1 注册的**Sign in**，请选择 "  >  **下一步**"，Microsoft[将自动设置你的记录](../get-help-with-domains/domain-connect.md)。
    
    2. 可向域注册联系人发送包含验证码的电子邮件。 如果无法识别记录的电子邮件或对其具有访问权限，则可以使用第三个选项。
    
    3. 可使用 TXT 记录验证域。 选择此操作并选择 "**下一步**"，查看有关如何将此 DNS 记录添加到你的注册机构网站的说明。 在添加记录后，可能需要长达30分钟的时间来进行验证。 
    
6. 选择您希望如何对 Office 使用您的域所做的 DNS 更改。
    
    1. 如果您希望 Office 自动配置您的 DNS，请选择 **"为我添加 dns 记录"** 。 
    
  
    2. 如果你想要仅将特定的 Office 365 服务附加到你的域，或者你现在想要跳过此操作，请选择 **"我要在自己添加 DNS 记录"** 。 **如果确切了解执行内容，请选择此选项。**
    
7. 如果你选择*自己添加 DNS 记录*，请选择 "**下一步**"，你将看到一个页面，其中包含你需要将其添加到注册机构网站以设置你的域的所有记录。 
    
  
  
    如果门户无法识别你的注册机构，你可以[按照以下常规说明操作。](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    查看[主机特定说明](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)列表，以找到你的主机并按照步骤添加所需的全部记录。 
    
    如果不知道你的域的 DNS 托管提供商或域注册机构，请参阅[查找域注册机构或 DNS 托管提供商](../get-help-with-domains/find-your-domain-registrar.md)。
    
    如果要稍后等待，请滚动到底部，然后选择 "**跳过此步骤**"。
    
8. 选择 "**完成**"-完成！ 

## <a name="add-or-edit-custom-dns-records"></a>添加或编辑自定义 DNS 记录

按照以下步骤为网站或第三方服务添加自定义记录。

1. 在上登录到 Microsoft 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 转到 "**设置**   >  **域**" 页面。

3. 在" **域**"页面上选择域。 
    
4. 在 " **DNS 设置**" 下，选择 "**自定义记录**";然后选择 "**新建自定义记录**"。

5. 选择要添加的 DNS 记录的类型，然后键入新记录的信息。
    
6. 选择“保存”****。

## <a name="registrars-with-domain-connect"></a>具有域连接的注册机构

启用[域连接](https://www.domainconnect.org/)的注册机构允许您将您的域添加到 Microsoft 365，这是一个需要几分钟时间的三步骤过程。 
  
在向导中，我们将只是确认你拥有域，然后自动设置你的域的记录，因此电子邮件将发送到 Microsoft 365 和其他 Microsoft 365 服务（如团队）使用你的域。
  
> [!NOTE]
> 在开始此设置向导前，请确保你已禁用浏览器中的任何弹出窗口阻止程序。
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>与 Microsoft 365 集成的域连接注册机构

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer 或 WildWestDomains （使用 SecureServer DNS 托管的 GoDaddy 经销商）
    - [MadDog 域](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a>我的电子邮件和网站会发生什么情况？

完成设置后，你的域的 MX 记录将更新为指向 Microsoft 365，并且你的域的所有电子邮件都将开始进入 Microsoft 365。 请确保你已在 Office 365 中添加用户并为每个在你的域中收到电子邮件的人设置邮箱！
  
如果你有一个用于你的企业的网站，它将在其所在的位置保持工作。 域连接设置步骤不会影响您的网站。

## <a name="related-articles"></a>相关文章

[关于域的常见问题](domains-faq.md)

[什么是域？](../get-help-with-domains/what-is-a-domain.md)

[在 Office 365 中购买域名](../get-help-with-domains/buy-a-domain-name.md)

[设置域（主机特定的操作说明）](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[获取有关域的帮助](../get-help-with-domains/get-help-with-domains.md)
