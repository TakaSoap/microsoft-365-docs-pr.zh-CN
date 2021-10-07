---
title: 将域添加到 Microsoft 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: 使用设置向导，通过添加 DNS Microsoft 365 DNS Microsoft 365 管理中心将域添加到域中。
ms.openlocfilehash: 29d8471726649a96c2015d3d1ae492ae9f93c392
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195109"
---
# <a name="add-a-domain-to-microsoft-365"></a>将域添加到 Microsoft 365

 如果找不到要查找的内容，请 **[查看域常见问题解答](domains-faq.yml)**。 
  
 *若要添加、修改或删除域，**你必须** 是企业 **或** 企业计划的 [全局管理员](https://products.office.com/business/office)。这些更改会影响整个 *租户，自定义* 管理员或常规用户将无法进行这些更改。*  

 ## <a name="add-a-domain"></a>添加域

按照以下步骤添加、设置或继续设置域。 

::: moniker range="o365-worldwide"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。

::: moniker-end
::: moniker range="o365-germany"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。

::: moniker-end

::: moniker range="o365-21vianet"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 的管理中心。

::: moniker-end
    
2. 转到 **"设置**  >  **域"** 页面。 

3. 选择 “**添加域**”。
    
4. 输入要添加的域的名称，然后选择"下一步 **"。**
    
5. 选择您希望如何验证您是否拥有该域。
    
    1. 如果域[注册机构使用](#domain-connect-registrars-integrating-with-microsoft-365)域连接，Microsoft 会通过[](../get-help-with-domains/domain-connect.md)登录注册机构并确认与注册机构的连接来自动Microsoft 365。 你将返回到管理中心，然后 Microsoft 将自动验证你的域。
    2. 可使用 TXT 记录验证域。 选择此选项并选择" **下一** 步"以查看有关如何将此 DNS 记录添加到注册机构网站的说明。 添加记录后，最多可能需要 30 分钟进行验证。 
    3. 你可以将文本文件添加到你的域的网站。 从安装向导.txt下载文件，然后将该文件上载到网站的顶级文件夹。 文件的路径应类似于 `http://mydomain.com/ms39978200.txt` ：。 我们将通过在网站上查找文件来确认你拥有该域。
    
6. 选择希望 Microsoft 使用域所需的 DNS 更改。
    
    1. 如果你 **的** 注册机构支持域 [连接，](#domain-connect-registrars-integrating-with-microsoft-365)请选择"为我添加 DNS 记录"，Microsoft [](../get-help-with-domains/domain-connect.md)会通过登录注册机构并确认与注册机构的连接来自动Microsoft 365。
    2. Choose **I'll add the DNS records自己** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later. **如果确切了解执行内容，请选择此选项。**

7. 如果选择自己添加 *DNS* 记录，请选择"下一步"，你将看到一个包含要添加到注册机构网站以设置域的所有记录的页面。 

    如果门户无法识别你的注册机构，你可以[按照以下常规说明操作。](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    如果不知道你的域的 DNS 托管提供商或域注册机构，请参阅[查找域注册机构或 DNS 托管提供商](../get-help-with-domains/find-your-domain-registrar.md)。
    
    如果要等待以后，请取消选择所有服务并单击"继续"，或在上一个域连接步骤中选择"更多选项"并选择"立即跳过 **此"。**
    
8. 选择 **完成** - 你已完成！

## <a name="add-or-edit-custom-dns-records"></a>添加或编辑自定义 DNS 记录

按照以下步骤为网站或第三方服务添加自定义记录。

1. 在 登录 Microsoft 管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 转到 **"设置**   >  **域"** 页面。

3. 在" **域**"页面上选择域。 
    
4. 在 **"DNS 设置"** 下，选择 **"自定义记录";** 然后选择"**新建自定义记录"。**

5. 选择要添加的 DNS 记录类型，然后键入新记录的信息。
    
6. 选择“**保存**”。

## <a name="registrars-with-domain-connect"></a>具有域注册机构的连接

[通过连接](https://www.domainconnect.org/)域注册机构，你可以将域添加到Microsoft 365只需几分钟即可完成一个三步过程。 
  
在向导中，我们将仅确认您拥有该域，然后自动设置您的域记录，因此电子邮件会发送到 Microsoft 365 和其他 Microsoft 365 服务（如 Teams）处理您的域。
  
> [!NOTE]
> 在开始此设置向导前，请确保你已禁用浏览器中的任何弹出窗口阻止程序。
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>与连接的域注册机构Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer 或 WildWestDomains (SecureServer DNS 托管服务与 GoDaddy 经销商) 
    - 示例：
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>我的电子邮件和网站会发生什么情况？

完成设置后，你的域的 MX 记录将更新为指向Microsoft 365并且你的域的所有电子邮件都将开始Microsoft 365。 确保你已添加用户，并针对域中收到电子邮件的Microsoft 365设置邮箱！
  
如果你有一个用于你的企业的网站，它将在其所在的位置保持工作。 域连接设置步骤不会影响您的网站。

## <a name="related-content"></a>相关内容

[域常见问题解答](domains-faq.yml)（文章）\
[什么是域？](../get-help-with-domains/what-is-a-domain.md) （文章）\
[购买域名，Microsoft 365 (](../get-help-with-domains/buy-a-domain-name.md)文章) \