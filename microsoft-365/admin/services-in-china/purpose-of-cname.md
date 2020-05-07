---
title: MSOID 的 Office 365 CNAME 记录有何用途？
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: 了解有关 Office 365 中的 "MSOID" CNAME 记录的详细信息，该记录将您定向到最佳服务器以进行身份验证过程，以便获取更快的响应。
monikerRange: o365-21vianet
ms.openlocfilehash: a7c59829419ac8e7db400b079681ccf5bff199d6
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053844"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>MSOID 的 Office 365 CNAME 记录有何用途？

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
> [!NOTE]
> 以下仅适用于由世纪互联运营的 * * Office 365。
  
你可能很想知道为什么需要在 Office 365 中添加"MSOID"CNAME 记录。 这是必须为所有自定义域添加的记录（无论你使用何种订阅）。 为什么需要它？ 这有一点技术上的原因，但本质上，这使你可定向到最好的服务器以进行某些身份验证过程，因此你可获得更快的响应。
  
技术详细信息：当你运行与 Office 365 配合使用的客户端应用程序时，例如 Skype for Business Online、Outlook、Windows PowerShell 或 Microsoft Azure Active Directory 同步工具，你的凭据必须经过身份验证。Office 365 使用 CNAME 记录指向你所在位置的正确身份验证终结点，从而确保快速身份验证响应时间。
  
如果你的域缺少此 CNAME 记录，这些应用程序将使用美国的默认身份验证终结点，这意味着身份验证可能较慢。如果未正确配置此 CNAME 记录，例如，如果在" **指向地址**"中输入有误，这些应用程序将无法进行身份验证。
  
 **如果 Office 365 管理您的域的 DNS 记录，** Office 365 为你设置此 CNAME 记录。 
  
 **如果要在 dns 主机上管理域的 dns 记录，请**按照[DNS 主机的说明](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)自己创建此记录。
  
如果您正在规划 Office 365 部署，并希望了解有关您可能需要添加或更新的所有 DNS 记录的详细信息，请阅读相关[内容： Office 365 的外部域名系统记录](https://go.microsoft.com/fwlink/?LinkId=579013)。
  

