---
title: 管理 DNS 记录时为 Office 365 创建 DNS 记录
f1.keywords:
- CSH
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: '了解如何在管理 DNS 记录时为由世纪网运营的 Office 365 创建 DNS 记录。 '
monikerRange: o365-21vianet
ms.openlocfilehash: 8cd021c204424910d88133076ce0ce7af9a240952d116dbf9e9f4d4562fe41ec
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53822423"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a>管理 DNS 记录时为 Office 365 创建 DNS 记录

有关如何为由世纪互联运营的 Office 365 创建 DNS 记录的详细说明，包括邮件路由所需的 MX 记录，请参阅 [在任何 DNS 托管提供者处为 Office 365 创建 DNS 记录](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。 
  
  
更多选项以及应了解的一些事项：
      
-  如果不知道你的域的 DNS 托管提供商或域注册机构，请参阅[查找域注册机构或 DNS 托管提供商](../get-help-with-domains/find-your-domain-registrar.md)。 有关 DNS 记录功能的说明，请参阅 [DNS 基础知识](../get-help-with-domains/dns-basics.md)。
    
-  一些 DNS 托管提供商不允许您创建所有必需的记录类型，这会导致 [托管提供商不支持 SRV、CNAME、TXT 或重定向时出现](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)。 如果你的提供商不支持 SRV、TXT 或 CNAME 记录，我们建议你 [将你的域](../get-help-with-domains/buy-a-domain-name.md) 转移到支持所有必需的记录类型的 [提供商](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)。 
    
- 要查看哪些 DNS 记录是必需的，并查找要为每条记录使用的值，包括用于电子邮件的 MX 记录，请参阅[收集创建 Office 365 DNS 记录所需的信息](../get-help-with-domains/information-for-dns-records.md)。有关 DNS 记录的功能说明，请参阅 [DNS 基础知识](../get-help-with-domains/dns-basics.md)。
