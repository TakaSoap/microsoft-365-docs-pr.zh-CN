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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 通过购买域名并添加到 tom@fourthcoffee.com，将电子邮件地址更改为友好电子邮件地址，Microsoft 365。
ms.openlocfilehash: 71269513bce69ec81cf6e4a3030fb3327c32c88d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165132"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>将电子邮件地址更改为使用您的自定义域

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
::: moniker range="o365-worldwide"

您Microsoft 365中的初始电子邮件地址 onmicrosoft.com .tom@fourthcoffee.onmicrosoft.com。 您可以将其更改为更易于记忆的地址（如 tom@fourthcoffee.com）。 您首先需要您自己的域名，例如 fourthcoffee.com。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-germany"

你在德国的初始电子邮件地址Office 365 .onmicrosoft.de，如 tom@fourthcoffee.onmicrosoft.de。 你可以将地址更改为更友好的地址，tom@fourthcoffee.de。 你将需要自己的域名，如 fourthcoffee.de 域名。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-21vianet"

由世纪Office 365运营的 partner.onmschina.cn 中的初始电子邮件地址 tom@fourthcoffee.partner.onmschina.cn。 你可以将地址更改为更友好的地址，tom@fourthcoffee.cn。 你将需要自己的域名，如 fourthcoffee.cn 域名。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

当您将域的电子邮件更改为发送到 Microsoft 365，在设置期间更新域的 MX 记录时，发送到该域的所有电子邮件都将开始Microsoft 365。 在更改 MX 记录之前，请确保Microsoft 365域中拥有电子邮件的每个人添加用户并创建邮箱。 不想将域中的每个人的电子邮件移动到Microsoft 365？ 你可以采取一些[步骤来Microsoft 365一些电子邮件地址进行试点](../misc/pilot-microsoft-365-from-my-custom-domain.md)。
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>将电子邮件地址更改为使用自定义域Microsoft 365 管理中心

必须是 全局管理员 才能执行这些步骤。

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

4. 按照步骤确认你拥有你的域。 将指导你正确设置域中所有Microsoft 365。

5. 转到"**用户**  >  **""活动用户"。**

6. 选择用户以编辑其用户名，并更改为你刚刚添加的域。

> [!NOTE]
> 如果未使用 Exchange许可证，则不能使用域从 Microsoft 365 租户发送或接收电子邮件。
  
## <a name="related-content"></a>相关内容

[使用自定义域Microsoft 365 (](../get-help-with-domains/buy-a-domain-name.md)购买) \
[管理域 (](/admin) 链接页面) \
[域常见问题](../setup/domains-faq.yml) （文章）