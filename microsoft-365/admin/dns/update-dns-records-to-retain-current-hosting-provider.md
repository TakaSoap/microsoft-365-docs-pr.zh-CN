---
title: 更新 DNS 记录以便利用当前的托管提供商继续托管网站
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: 了解如何将流量路由到 Microsoft 外部托管的现有公共网站（如果将 Microsoft 设置为管理自定义域的 DNS 记录）。
ms.openlocfilehash: 9a7090eef3ce7d1c67839e7320f31d7bd32aa6a7
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814394"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>更新 DNS 记录以便利用当前的托管提供商继续托管网站

 **如果在 DNS 托管提供商处管理域的 Microsoft 记录，** 您不必担心本主题中的步骤。 您的网站将保留在原处，供用户继续正常访问。 
  
 **如果 Microsoft 管理 DNS 记录，则**将流量路由到 Microsoft 外部托管的现有公共网站，则将域添加到 Microsoft 后，执行以下操作： 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心中更新 DNS 记录
1. 在管理中心，转到“**设置**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>”页面。

2. 在'**域**'页面上，选择域，然后选择 **'DNS 记录'。**

3. 在 **"DNS 设置"** 下，选择 **"自定义记录"。**

4. 选择" **+ 新增自定义记录** "，然后输入以下信息： 
    
   - 对于" **DNS 类型** "，请输入： **A (地址)**
    
   - 对于" **主机名或别名** "，请键入： **@**
    
   - 对于" **IP 地址** "，请键入网站当前托管位置的静态 IP 地址（例如 172.16.140.1）。 
    
   必须是该网站的 *静态*  IP 地址，不能是  *动态*  IP 地址。 请与您的网站的托管网站核实，确保可以获得您的公共网站的静态 IP 地址。 
    
5. 选择" **保存** "。 
    
此外，您可以创建 CNAME 记录以帮助客户找到您的网站。
  
1. 选择" **+ 新增自定义记录** "，然后输入以下信息： 
    
   - 对于" **DNS 类型** "，请输入： **CNAME (别名)**
    
   - 对于" **主机名或别名** "，请键入： **www**
    
   - 对于" **指向地址** "，请键入网站的完全限定域名 (FQDN)，例如 contoso.com。 
    
2. 选择" **保存** "。 
    
最后，请执行下列操作：
  
[将你的域的 NS 记录更新](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) 为指向 Microsoft。 
  
当这些 NS 记录更新为指向 Microsoft 时，您的域即已设置成功。 电子邮件将路由至 Microsoft，到您的网站地址的流量将继续转到您的当前网站主机。
 
