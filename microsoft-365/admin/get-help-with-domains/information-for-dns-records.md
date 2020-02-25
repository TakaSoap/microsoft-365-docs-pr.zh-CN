---
title: 收集创建 Office 365 DNS 记录所需的信息
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: '了解如何查找创建适用于 Office 365 的 DNS 记录所需的值/信息。 '
ms.custom: okr_smb
ms.openlocfilehash: 7b995aedc21305367e4a6621781e138d0d60efd1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251141"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a>收集创建 Office 365 DNS 记录所需的信息

 如果找不到要查找的内容，请**[查看域常见问题解答](../setup/domains-faq.md)**。 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>步骤1：查找 TXT 记录值并验证

1. 在 Microsoft 365 管理中心，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。
    
    如果使用的是 Office 365 德国，请转到 "<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>" 页。 
    
    如果您正在使用由世纪互联运营的 Office 365，请转到此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>页面。
    
2. 在 "**域**" 页上，选择您的域，然后选择 "**启动安装程序**"。 你将返回域设置向导，查看需要添加的特定值。
    
3. 在 "**验证域**" 页上，选择 "**添加 TXT 记录**"，然后选择 "**下一步**"。
    
4. 复制所示的**TXT 值**。 其外观如下所示： **MS = msXXXXXXXX**。 
    
5. 转到 "[在任何 DNS 托管提供程序中创建 dns 记录](create-dns-records-at-any-dns-hosting-provider.md)"，然后从注册机构列表中选择您的 dns 主机，以查看分步说明。
    
6. 按照在 DNS 主机上创建 TXT 记录（或 MX 记录）的步骤操作，然后返回 Office 365 中验证域。

7. 在 Office 365 中验证域后，从 DNS 主机中删除 TXT 记录（或 MX 记录）。
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>步骤2：查找电子邮件和其他的 MX 记录值

1. 在 Microsoft 365 管理中心，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。
    
    如果使用的是 Office 365 德国，请转到 "<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">域</a>" 页。 
    
    如果您正在使用由世纪互联运营的 Office 365，请转到此<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">域</a>页面。
    
2. 在" **域**"页面上，选择你的域。 
    
3. " **所需的 DNS 设置**"下将显示要添加的 DNS 记录。
    
    更改 DNS 主机时，需要保持此信息可用，以便复制粘贴这些值。
    
    页面上列出的 DNS 记录组取决于" **域用途**"下列出的选项。
    
4. 转到 "[在任何 DNS 托管提供程序中创建 dns 记录](create-dns-records-at-any-dns-hosting-provider.md)"，然后从注册机构列表中选择您的 dns 主机，以查看有关在该 DNS 主机的网站上添加记录的分步说明。
    
5. 按照在您的 DNS 主机上创建记录的步骤执行操作。
