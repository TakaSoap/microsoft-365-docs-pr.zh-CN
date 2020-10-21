---
title: 使用域连接
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: 了解如何使用启用域连接的注册机构并将你的域添加到 Microsoft 365。
ms.openlocfilehash: e907317ec5b606c2fe73232a73c9abdfce26feea
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645343"
---
# <a name="using-domain-connect"></a>使用域连接

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。
  
启用[域连接](https://www.domainconnect.org/)的注册机构允许您将您的域添加到 Microsoft 365，这是一个需要几分钟时间的三步骤过程。 
  
在向导中，我们将只是确认你拥有域，然后自动设置你的域的记录，因此电子邮件将发送到 Microsoft 365 和其他 Microsoft 365 服务（如团队）使用你的域。
  
> [!NOTE]
> 在开始此设置向导前，请确保你已禁用浏览器中的任何弹出窗口阻止程序。
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>与 Microsoft 365 集成的域连接注册机构

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- 使用 SecureServer DNS 托管) 的 SecureServer 或 WildWestDomains (GoDaddy 经销商
    - [MadDog 域](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>我的电子邮件和网站会发生什么情况？

完成设置后，你的域的 MX 记录将更新为指向 Microsoft 365，并且你的域的所有电子邮件都将开始进入 Microsoft 365。 请确保您已为在您的域中收到电子邮件的每个人添加了用户并为其设置了 Microsoft 365 中的邮箱！
  
如果你有一个用于你的企业的网站，它将在其所在的位置保持工作。 域连接设置步骤不会影响您的网站。
