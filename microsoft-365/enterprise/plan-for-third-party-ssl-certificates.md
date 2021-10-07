---
title: 规划 Microsoft 365 的第三方 SSL 证书
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: b48cdf63-07e0-4cda-8c12-4871590f59ce
description: 摘要：介绍了本地和混合Exchange SSO、使用 AD FS 的 SSO、Exchange Online 服务和 Exchange 所需的 SSL 证书。
ms.openlocfilehash: 8c0bf69090abb87e71f2d51b73405ccf4e54d4bb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202831"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>规划 Microsoft 365 的第三方 SSL 证书

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

若要加密客户端和 Microsoft 365 环境之间的通信，必须在基础结构服务器上安装第三 (SSL) 证书。

本文是 Network [planning and performance tuning for Microsoft 365 的一Microsoft 365。](./network-planning-and-performance.md)
   
以下组件需要证书Microsoft 365组件：
  
- 本地 Exchange
    
- Active Directory (联合身份验证服务 (AD FS) 联合服务器和 AD FS 联合服务器代理)  (单一登录) 
    
- Exchange Online服务，例如自动发现、Outlook Anywhere 和 Exchange Web 服务
    
- Exchange混合服务器
    
## <a name="certificates-for-exchange-on-premises"></a>本地Exchange证书

有关如何使用数字证书确保内部部署组织与 Exchange 之间的通信安全的Exchange Online，请参阅 TechNet 文章[了解证书要求](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141))。
  
## <a name="certificates-for-single-sign-on"></a>单一登录的证书

若要为用户提供包含强大安全性的简化单一登录体验，在联合服务器或联合服务器代理上需要下表中所示的证书。 下表重点介绍 Active Directory 联合身份验证服务 (AD FS) ，我们还提供有关使用第三方标识提供程序 [的详细信息](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)。
  
| 证书类型 | 说明 | 部署之前需要知道哪些内容 |
|:-----|:-----|:-----|
|**SSL 证书 (也称为服务器身份验证证书)** <br/> |这是一个标准 SSL 证书，用于保护联合服务器、客户端和联合服务器代理服务器之间的通信安全。  <br/> |AD FS 需要 SSL 证书。 默认情况下，AD FS 使用为 IIS 服务中的默认网站Internet Information Services (SSL) 。  <br/> 此 SSL 证书的主题名称用于确定您部署的每个 AD FS (FS) 联合身份验证服务名称。 请考虑为 CA 颁发的证书 (新证书颁发机构选择) 名称，该证书最好表示要注册的公司或组织Microsoft 365。 此名称必须可 Internet 路由。  <br/>**警告：** AD FS 要求此 SSL 证书在主题名称 (短) 无点。          <br/> **建议：** 由于 AD FS 的客户端必须信任此证书，因此建议使用由公共 (第三方) CA 或附属于公共受信任根的 CA 颁发的 SSL 证书;例如，VeriSign 或 Thawte。  <br/> |
|**令牌签名证书** <br/> |这是一个标准 X.509 证书，用于对联合服务器颁发的所有令牌进行安全签名，Microsoft 365验证。  <br/> |令牌签名证书必须包含一个私钥，该私钥与 FS 中的受信任根进行链连接。 默认情况下，AD FS 创建自签名证书。 但是，根据组织的需要，您可以使用 AD FS 管理单元，将此证书更改为 CA 颁发的证书。  <br/>**警告：** 令牌签名证书对 FS 的稳定性至关重要。 如果证书发生更改，则必须Microsoft 365更改通知用户。 如果未提供通知，则用户无法登录其Microsoft 365服务产品。<br/>**建议：** 建议使用 AD FS 生成的自签名令牌签名证书。 通过执行此操作，它默认为您管理此证书。 例如，当此证书即将过期时，AD FS 将生成一个新的自签名证书。  <br/> |
   
联合服务器代理需要下表中描述的证书。
  
| 证书类型 | 说明 | 部署之前需要知道哪些内容 |
|:-----|:-----|:-----|
|SSL 证书  <br/> |这是一个标准 SSL 证书，用于保护联合服务器、联合服务器代理和 Internet 客户端计算机之间的通信。  <br/> |必须先将此 SSL 证书绑定到 IIS 中的默认网站，然后才能成功运行 AD FS 联合服务器代理配置向导。  <br/> 此证书的主题名称必须与在企业网络中联合服务器上配置的 SSL 证书相同。  <br/> **建议：** 建议您使用此联合服务器代理连接到的联盟服务器上配置的相同服务器身份验证证书。  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>用于自动发现、Outlook位置和 Active Directory 同步的证书

面向外部的 Exchange 2013、Exchange 2010、Exchange 2007 和 Exchange 2003 客户端访问服务器 (CAS) 需要第三方 SSL 证书，用于自动发现、Outlook Anywhere 和 Active Directory 同步服务的安全连接。 您可能已经在本地环境中安装了此证书。
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>混合服务器的Exchange证书

面向外部的Exchange混合服务器需要第三方 SSL 证书，以确保与 Exchange Online 服务的安全连接。 您需要从第三方 SSL 提供程序获取此证书。
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365证书链

本文介绍了在基础结构上可能需要安装的证书。 有关安装在我们的证书链服务器上Microsoft 365，请参阅Microsoft 365[链。](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb)
  
## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版概述](microsoft-365-overview.md)