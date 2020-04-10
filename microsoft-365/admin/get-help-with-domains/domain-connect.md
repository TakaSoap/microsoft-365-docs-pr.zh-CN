---
title: 使用域连接
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: 了解如何使用启用域连接的注册机构并将你的域添加到 Microsoft 365。
ms.openlocfilehash: 074ecc09323e09d3a668dd1c90f6034d8fce99eb
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210412"
---
# <a name="using-domain-connect"></a>使用域连接

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。
  
启用[域连接](https://www.domainconnect.org/)的注册机构允许您将您的域添加到 Microsoft 365，这是一个需要几分钟时间的三步骤过程。 
  
在向导中，我们将只是确认你拥有域，然后自动设置你的域的记录，因此电子邮件将发送到 Microsoft 365 和其他 Microsoft 365 服务（如团队）使用你的域。
  
> [!NOTE]
> 在开始此设置向导前，请确保你已禁用浏览器中的任何弹出窗口阻止程序。
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>与 Microsoft 365 集成的域连接注册机构

- [1&amp;1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer 或 WildWestDomains （使用 SecureServer DNS 托管的 GoDaddy 经销商）
    - [MadDog 域](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>我的电子邮件和网站会发生什么情况？

完成设置后，你的域的 MX 记录将更新为指向 Microsoft 365，并且你的域的所有电子邮件都将开始进入 Microsoft 365。 请确保你已在 Office 365 中添加用户并为每个在你的域中收到电子邮件的人设置邮箱！
  
如果你有一个用于你的企业的网站，它将在其所在的位置保持工作。 域连接设置步骤不会影响您的网站。
