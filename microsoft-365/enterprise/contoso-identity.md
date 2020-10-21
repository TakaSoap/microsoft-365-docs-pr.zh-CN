---
title: Contoso Corporation 的标识
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何利用标识即服务 (IDaaS)，并为其员工提供基于云的身份验证以及为其合作伙伴和客户提供联合身份验证。
ms.openlocfilehash: 10db0a35024595c4dba9a33ad83ae75bcad3870c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637243"
---
# <a name="identity-for-the-contoso-corporation"></a>Contoso Corporation 的标识

Microsoft 通过 Azure Active Directory (Azure AD) 将标识作为服务 (IDaaS) 通过其云产品提供。 若要采用 Microsoft 365 for enterprise，Contoso IDaaS 解决方案必须使用其内部部署标识提供程序，并将联合身份验证包括在其现有的受信任的第三方标识提供程序中。

## <a name="the-contoso-active-directory-domain-services-forest"></a>Contoso Active Directory 域服务林

Contoso 使用单个 Active Directory 域服务 (AD DS) 林，为 contoso \. com 提供七个子域，每个区域适用于世界的每个区域一个。 总部、区域中心办事处和分支办事处包含用于本地身份验证和授权的域控制器。

以下是包含区域中心的全球不同部分的带有地区性域的 Contoso 林。

![全球的 Contoso 林和域](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso 决定使用 contoso com 林中的帐户和组 \. 进行身份验证，并授权其 Microsoft 365 工作负载和服务。

## <a name="the-contoso-federated-authentication-infrastructure"></a>Contoso 联合身份验证基础结构

Contoso 允许：

- 客户使用其 Microsoft、Facebook 或 Google 邮件帐户登录到公司的公共网站。
- 供应商和合作伙伴使用其 LinkedIn、Salesforce 或 Google Mail 帐户登录到公司的合作伙伴 extranet。

以下是包含公共网站、合作伙伴 extranet 和一组 AD FS 服务器的 Contoso DMZ。 DMZ 连接到包含客户、合作伙伴和 internet 服务的 internet。

![Contoso 支持客户和合作伙伴的联合身份验证](../media/contoso-identity/contoso-identity-fig2.png)
 
DMZ 中的 AD FS 服务器通过其标识提供商访问公用网站的身份验证和合作伙伴凭据，从而简化了客户凭据的身份验证，以访问合作伙伴 extranet。

Contoso 决定保留此基础结构并将其专用于客户和合作伙伴身份验证。 Contoso 标识架构师正在研究如何将此基础结构转换为 Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) 和 [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) 解决方案。

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>通过混合标识和密码哈希同步实现基于云的身份验证

Contoso 想要使用其内部部署 AD DS 林进行身份验证，以进行 Microsoft 365 云资源的身份验证。 它决定使用密码哈希同步 (PHS) 。

PHS 将本地 AD DS 林与 Microsoft 365 for enterprise 订阅的 Azure AD 租户同步，复制用户和组帐户以及用户帐户密码的哈希版本。

为了执行目录同步，Contoso 在巴黎 datacenter 中的服务器上部署了 Azure AD Connect 工具。

以下是运行 Azure AD 的服务器连接轮询 Contoso AD DS 林以进行更改，然后将这些更改与 Azure AD 租户同步。

![Contoso PHS 目录同步基础结构](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>针对标识和设备访问的条件访问策略

Contoso 为以下三种保护级别创建了一组 Azure AD 和 Intune [条件访问策略](identity-access-policies.md)：

- *基准* 保护适用于所有用户帐户。
- *敏感* 保护适用于高级领导和执行人员。
- *高度管控* 保护适用于财务、法律和研究部门中有权访问高度管控数据的特定用户。

以下是 Contoso identity and device 条件访问策略的结果集。

![Contoso 的标识和设备条件访问策略](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>后续步骤

[了解](contoso-win10.md) Contoso 如何使用其 Microsoft 终结点配置管理器基础结构在其整个组织中部署和保留当前的 Windows 10 企业版。

## <a name="see-also"></a>另请参阅

[Microsoft 365 的识别指南](identity-roadmap-microsoft-365.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)
