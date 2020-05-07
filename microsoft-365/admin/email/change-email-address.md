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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: '将您的初始电子邮件地址更改为友好的电子邮件地址，如 tom@fourthcoffee.com。 若要执行此操作，您需要购买域名，并将其添加到 Microsoft 365。 '
ms.openlocfilehash: baa2e49d98ed1d7b3de9af78b84403d028b4c91d
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053820"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>将电子邮件地址更改为使用您的自定义域

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
::: moniker range="o365-worldwide"

Microsoft 365 中的初始电子邮件地址包括 onmicrosoft.com，如 tom@fourthcoffee.onmicrosoft.com。 您可以将其更改为更易于记忆的地址（如 tom@fourthcoffee.com）。 您首先需要您自己的域名，例如 fourthcoffee.com。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-germany"

Office 365 德国的初始电子邮件地址包括 onmicrosoft.de，如 tom@fourthcoffee.onmicrosoft.de。 您可以将其更改为更友好的地址，如 tom@fourthcoffee.de。 你将需要自己的域名，如 fourthcoffee.de。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-21vianet"

由世纪互联运营的 Office 365 中的初始电子邮件地址包括 partner.onmschina.cn，如 tom@fourthcoffee.partner.onmschina.cn。 您可以将其更改为更友好的地址，如 tom@fourthcoffee.cn。 你将需要自己的域名，如 fourthcoffee.cn。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

当您将您的域的电子邮件更改为 Microsoft 365 时，在安装过程中更新您的域的 MX 记录，发送到该域的所有电子邮件都将开始进入 Microsoft 365。 请确保您已在 Microsoft 365 中添加了用户并创建了邮箱，以便在更改 MX 记录之前在您的域中有电子邮件的所有人。 不想将你的域中每个人的电子邮件移至 Microsoft 365 吗？ 您可以采取步骤[仅使用几个电子邮件地址来试用 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)。
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心将您的电子邮件地址更改为使用您的自定义域

您必须具有全局管理员帐户才能执行这些步骤。 

::: moniker range="o365-worldwide"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 的管理中心。 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. 转到管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>。 

::: moniker-end 

2. 转到 "**安装** > **域**" 页。 

3. 在 "**域**" 页上，选择 "**添加域**"。
    
4. 按照相应步骤确认您拥有自己的域和更改您的电子邮件地址。
    
系统将指导你在 Microsoft 365 中使用你的域正确设置所有内容。

> [!NOTE]
> 如果未使用 Exchange 许可证，则不能使用域从 Microsoft 365 租户发送或接收电子邮件。
  
## <a name="related-articles"></a>相关文章

[使用 Microsoft 365 购买自定义域](../get-help-with-domains/buy-a-domain-name.md)
 
