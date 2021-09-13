---
title: 更新 DNS 记录以便利用当前的托管提供商继续托管网站
f1.keywords:
- NOCSH
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
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: 了解如何将流量路由到 Microsoft 外部托管的现有公共网站（如果已设置 Microsoft 管理自定义域的 DNS 记录）。
ms.openlocfilehash: d54aa4583862ce19907a3b8494a333bbb925e436
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59169817"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>更新 DNS 记录以便利用当前的托管提供商继续托管网站

 **如果在 DNS** 托管提供商中管理域的 Microsoft 记录，则无需担心本主题中的步骤。 您的网站将保留在原处，供用户继续正常访问。 
  
 **如果 Microsoft 管理 DNS 记录**，若要将流量路由到在 Microsoft 外部托管的现有公共网站，在将域添加到 Microsoft 后，请执行下列操作： 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>更新 DNS 记录Microsoft 365 管理中心
1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

1. 在"**域**"页面上，选择域，然后选择 **"DNS 记录"。**

1. 选择 **+ 添加记录** ，然后输入以下内容： 
    
   - 对于 **类型** 输入 **：A (Address)**
    
   - 对于" **主机名或别名** "，请键入： **@**
    
   - 对于" **IP 地址** "，请键入网站当前托管位置的静态 IP 地址（例如 172.16.140.1）。 
    
   必须是该网站的 *静态*  IP 地址，不能是  *动态*  IP 地址。 请与您的网站的托管网站核实，确保可以获得您的公共网站的静态 IP 地址。 
    
1. 选择" **保存** "。 
    
此外，您可以创建 CNAME 记录以帮助客户找到您的网站。
  
1. 选择 **+ 添加记录** ，然后输入以下内容： 
    
   - 对于 **类型** 输入 **：CNAME (别名)**
    
   - 对于" **主机名或别名** "，请键入： **www**
    
   - 对于" **指向地址** "，请键入网站的完全限定域名 (FQDN)，例如 contoso.com。 
    
2. 选择" **保存** "。 
    
最后，请执行下列操作：
  
[将域的 NS 记录更新](../setup/add-domain.md) 为指向 Microsoft。 
  
当 NS 记录更新为指向 Microsoft 时，域已全部设置。 电子邮件将路由到 Microsoft，并且发送到你的网站地址的流量将继续转到你的当前网站主机。
