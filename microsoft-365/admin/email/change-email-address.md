---
title: 将电子邮件地址更改为使用您的自定义域
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
description: '将初始电子邮件地址更改为友好电子邮件地址，如tom@fourthcoffee.com。 若要执行此操作，你需要购买域名，并将它添加到 Microsoft 365。 '
ms.openlocfilehash: dc6d418961fe29a363aa6a787d8c0bb2d11d7e97
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814476"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>将电子邮件地址更改为使用您的自定义域

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
::: moniker range="o365-worldwide"

Microsoft 365 中你的初始电子邮件地址包含 .onmicrosoft.com，例如 tom@fourthcoffee.onmicrosoft.com。 您可以将其更改为更易于记忆的地址（如 tom@fourthcoffee.com）。 您首先需要您自己的域名，例如 fourthcoffee.com。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-germany"

Office 365 Germany 中的初始电子邮件地址包括 .onmicrosoft.de，如tom@fourthcoffee.onmicrosoft.de。 您可以将其更改为更易于好友的地址，如tom@fourthcoffee.de。 你将需要自己的域名，例如fourthcoffee.de的名称。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-21vianet"

由世纪互联运营的 Office 365 中的初始电子邮件地址包括一partner.onmschina.cn，如tom@fourthcoffee.partner.onmschina.cn。 您可以将其更改为更友好地址，如tom@fourthcoffee.cn。 你将需要自己的域名，例如fourthcoffee.cn个域名。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

当你在安装期间通过更新域的 MX 记录将你的域的电子邮件更改为传送到 Microsoft 365 时，所有发送到该域的电子邮件都将开始传送到 Microsoft 365。 在更改 MX 记录前，请确保你已在 Microsoft 365 中添加用户并为每个在你的域中有电子邮件的人创建邮箱。 不想将你的域中每个人的电子邮件移到 Microsoft 365 中？ 你可以采取措数，[改为仅使用几个电子邮件地址试用 Microsoft 365。](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain?view=o365-worldwide)
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>通过 Microsoft 365 管理中心，将电子邮件地址更改为使用你的自定义域

必须拥有全局管理员帐户才能执行这些步骤。 

::: moniker range="o365-worldwide"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. 转到上的所有管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>。 

::: moniker-end 

2. 转到"设置**Setup**  >  **域"** 页面。 

3. 在“**域**”页面上，选择“**添加域**”。
    
4. 按照相应步骤确认您拥有自己的域和更改您的电子邮件地址。
    
系统将引导你在 Microsoft 365 中正确设置您的域。

> [!NOTE]
> 如果你没有使用 Exchange 许可证，则无法使用该域发送或接收来自 Microsoft 365 租户的电子邮件。
  
## <a name="related-articles"></a>相关文章

[使用 Microsoft 365 购买自定义域](../get-help-with-domains/buy-a-domain-name.md)
 
