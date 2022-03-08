---
title: 将电子邮件地址更改为使用您的自定义域
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- adminvideo
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 将电子邮件地址更改为友好电子邮件地址，tom@fourthcoffee.com 购买域名并添加到电子邮件地址Microsoft 365。
ms.openlocfilehash: 4630b3df4719611440e92801235fde20d7bd95f4
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316417"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a>将电子邮件地址更改为使用您的自定义域

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。 
  
::: moniker range="o365-worldwide"

您Microsoft 365中的初始电子邮件地址 onmicrosoft.com .tom@fourthcoffee.onmicrosoft.com。 您可以将其更改为更易于记忆的地址（如 tom@fourthcoffee.com）。 您首先需要您自己的域名，例如 fourthcoffee.com。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

::: moniker range="o365-21vianet"

由世纪Office 365中的初始电子邮件地址包括 partner.onmschina.cn，tom@fourthcoffee.partner.onmschina.cn。 你可以将地址更改为更友好的地址，tom@fourthcoffee.cn。 你将需要你自己的域名，如 fourthcoffee.cn 域名。 如果您已有一个，太好了！ 如果没有，您可以了解如何[从域注册机构购买](../get-help-with-domains/buy-a-domain-name.md)。

::: moniker-end

当您在设置期间通过更新域的 MX 记录将域的电子邮件更改为Microsoft 365，发送到该域的所有电子邮件都将开始Microsoft 365。 在更改 MX 记录之前，请确保Microsoft 365域中拥有电子邮件的所有人添加用户并创建邮箱。 不想将域中的每个人的电子邮件移动到Microsoft 365？ 你可以采取一些[步骤来Microsoft 365几个电子邮件地址进行试点](../misc/pilot-microsoft-365-from-my-custom-domain.md)。
  
## <a name="set-up-business-email-with-a-new-domain"></a>使用新域设置业务电子邮件

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyVVA?autoplay=false]

购买电子邮件地址的新域名，并设置电子邮件地址Microsoft 365。

1. 通过提供新域名的联系人信息、选择付款方式，然后下订单，为电子邮件地址购买新域名。
1. 将地址的第一部分 (@ 符号) 或保留为 。 
1. 注销Microsoft 365，然后使用新的电子邮件地址重新登录。 使用新域更新员工电子邮件地址。 

## <a name="set-up-business-email-with-an-existing-domain"></a>设置具有现有域的业务电子邮件

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxApu?autoplay=false]

无论将域名用于网站地址还是其他提供商的电子邮件地址，请使用已拥有的域名。

1. 登录到托管您的域的网站。 单击按钮以手动验证或更新域。 
1. 自定义电子邮件地址或保留其为 。
1. 注销Microsoft 365，然后使用新的电子邮件地址重新登录。 使用新域更新员工电子邮件地址。

## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a>将电子邮件地址更改为使用自定义域Microsoft 365 管理中心

必须是 全局管理员 才能执行这些步骤。

::: moniker range="o365-worldwide"

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 的管理中心。

::: moniker-end

::: moniker range="o365-21vianet"

1. 转到 管理中心 。<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>

::: moniker-end

2. 转到 **SetupDomains**  >  页面。

3. 在“**域**”页面上，选择“**添加域**”。

4. 按照步骤确认你拥有你的域。 将指导你正确设置域中所有Microsoft 365。

5. 转到" **用户"** > **"活动用户"**。

6. 选择用户以编辑其用户名，并更改为你刚刚添加的域。

> [!NOTE]
> 如果未使用 Exchange许可证，则不能使用域从 Microsoft 365 租户发送或接收电子邮件。
  
## <a name="related-content"></a>相关内容

[使用自定义域Microsoft 365 (](../get-help-with-domains/buy-a-domain-name.md)购买) \
[管理域](/admin) (链接页) \
[域常见问题](../setup/domains-faq.yml) （文章）