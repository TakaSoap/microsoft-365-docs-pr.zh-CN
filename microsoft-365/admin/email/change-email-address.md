---
title: 将电子邮件地址更改为使用您的自定义域
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
- Adm_O365_Setup
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: '将初始电子邮件地址更改为友好电子邮件地址，如 tom@fourthcoffee.com。 为此，需要购买域名，并将其添加到 Microsoft 365。 '
ms.openlocfilehash: 10dff4e0523062ae763c08a972563dc8b5582038
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915922"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>将电子邮件地址更改为使用您的自定义域

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。

::: moniker-end

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
::: moniker range="o365-worldwide"

Microsoft 365 中的初始电子邮件地址包括 .onmicrosoft.com，tom@fourthcoffee.onmicrosoft.com。 您可以将其更改为更易于记忆的地址（如 tom@fourthcoffee.com）。 您首先需要您自己的域名，例如 fourthcoffee.com。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-germany"

Office 365 Germany 中的初始电子邮件地址包括 .onmicrosoft.de，tom@fourthcoffee.onmicrosoft.de。 你可以将地址更改为更友好的地址，tom@fourthcoffee.de。 你将需要自己的域名，如 fourthcoffee.de 域名。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-21vianet"

由世纪互联网运营的 Office 365 中的初始电子邮件地址包括 partner.onmschina.cn，tom@fourthcoffee.partner.onmschina.cn。 你可以将地址更改为更友好的地址，tom@fourthcoffee.cn。 你将需要你自己的域名，如 fourthcoffee.cn 域名。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

当你将域的电子邮件更改为发往 Microsoft 365 时，通过设置期间更新域的 MX 记录，发送到该域的所有电子邮件都将开始发往 Microsoft 365。 在更改 MX 记录之前，请确保你在 Microsoft 365 中为在你的域中拥有电子邮件的每个人添加了用户并创建了邮箱。 不想将域中每个人的电子邮件移动到 Microsoft 365？ 你可以采取一些措施，改为使用几个电子邮件地址来试用[Microsoft 365。](../misc/pilot-microsoft-365-from-my-custom-domain.md?view=o365-worldwide)
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心更改电子邮件地址以使用自定义域

必须具有全局管理员帐户才能执行这些步骤。 

::: moniker range="o365-worldwide"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. 转到 管理中心 。 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a> 

::: moniker-end 

2. 转到"**设置**  >  **域"** 页。 

3. 在“**域**”页面上，选择“**添加域**”。
    
4. 按照相应步骤确认您拥有自己的域和更改您的电子邮件地址。
    
将指导你在 Microsoft 365 中正确设置域的所有内容。

> [!NOTE]
> 如果未使用 Exchange 许可证，则不能使用域从 Microsoft 365 租户发送或接收电子邮件。
  
## <a name="related-articles"></a>相关文章

[使用 Microsoft 365 购买自定义域](../get-help-with-domains/buy-a-domain-name.md)
