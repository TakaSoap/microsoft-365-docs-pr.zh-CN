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
description: 了解如何使用启用域连接的注册机构，以及如何将域添加到 Microsoft 365。
ms.openlocfilehash: 109255d82100e636e3472242866a519ff64a9e54
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655608"
---
# <a name="using-domain-connect"></a>使用域连接

 如果找不到要查找的内容，请 **[查看域常见问题解答](../setup/domains-faq.yml)**。
  
[通过启用域 ](https://www.domainconnect.org/) 连接注册器，可以分三步将域添加到 Microsoft 365，此过程需要几分钟。 
  
在向导中，我们只需确认你拥有该域，然后自动设置域记录，这样电子邮件就会发送到 Microsoft 365 和其他 Microsoft 365 服务（如 Teams）处理你的域。
  
> [!NOTE]
> 在开始此设置向导前，请确保你已禁用浏览器中的任何弹出窗口阻止程序。
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>与 Microsoft 365 集成域连接注册机构

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer 或 WildWestDomains (使用 SecureServer DNS 托管服务访问 GoDaddy) 
    - [MadDog 域](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>我的电子邮件和网站会发生什么情况？

完成设置后，你的域的 MX 记录将更新为指向 Microsoft 365，并且你的域的所有电子邮件都将开始发送到 Microsoft 365。 确保你已添加用户，并针对在你的域中收到电子邮件的每个人在 Microsoft 365 中设置邮箱！
  
如果你有一个用于你的企业的网站，它将在其所在的位置保持工作。 域连接设置步骤不会影响您的网站。
