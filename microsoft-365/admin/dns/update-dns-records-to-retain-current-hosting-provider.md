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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: 了解如何将流量路由到在 Office 365 外部托管的现有公共网站（如果已将 Office 365 设置为管理自定义域的 DNS 记录）。
ms.openlocfilehash: 3e71925f9b50e5520bd383aa5318db513202f6ec
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142535"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>更新 DNS 记录以便利用当前的托管提供商继续托管网站

 **如果由您在 DNS 托管提供商处管理您的域的 Office 365 记录** ，您不必担心本主题中的步骤。您的网站将保留在原处，供用户继续正常访问。 
  
 **如果由 Office 365 管理 DNS 记录** ，那么要若将流量路由至在 Office 365 外部托管的现有公共网站，请在将域添加到 Office 365 后，执行下列操作： 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>更新 Microsoft 365 管理中心中的 DNS 记录
1. 在管理中心中，转到 "**安装** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">域</a>" 页。

2. 在" **域** "页面上的域列表中，选择要用于你的网站的域，然后在管理窗格中选择" **DNS 设置** "。 
    
3. 选择" **+ 新增自定义记录** "，然后输入以下信息： 
    
  - 对于" **DNS 类型** "，请输入： **A (地址)**
    
  - 对于" **主机名或别名** "，请键入： **@**
    
  - 对于" **IP 地址** "，请键入网站当前托管位置的静态 IP 地址（例如 172.16.140.1）。 
    
    必须是该网站的 *静态*  IP 地址，不能是  *动态*  IP 地址。 请与您的网站的托管网站核实，确保可以获得您的公共网站的静态 IP 地址。 
    
3. 选择" **保存** "。 
    
此外，您可以创建 CNAME 记录以帮助客户找到您的网站。
  
1. 选择" **+ 新增自定义记录** "，然后输入以下信息： 
    
  - 对于" **DNS 类型** "，请输入： **CNAME (别名)**
    
  - 对于" **主机名或别名** "，请键入： **www**
    
  - 对于" **指向地址** "，请键入网站的完全限定域名 (FQDN)，例如 contoso.com。 
    
2. 选择" **保存** "。 
    
最后，请执行下列操作：
  
[将您的域的 NS 记录更新为](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx)指向 Office 365。 
  
当这些 NS 记录更新为指向 Office 365 时，您的域即已设置成功。电子邮件将路由至 Office 365，到您的网站地址的流量将继续转到您的当前网站主机。
 
