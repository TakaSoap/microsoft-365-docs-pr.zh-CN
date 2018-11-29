---
title: Contoso Corporation 的标识
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何利用标识即服务 (IDaaS)，并为其员工提供基于云的身份验证以及为其合作伙伴和客户提供联合身份验证。
ms.openlocfilehash: 7571aa455cac4da9e56d7d2001ae4421c3769c94
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865868"
---
# <a name="identity-for-the-contoso-corporation"></a>Contoso Corporation 的标识

**摘要：** Contoso 如何利用标识即服务 (IDaaS)，并为其员工提供基于云的身份验证以及为其合作伙伴和客户提供联合身份验证。

Microsoft 在其云产品中通过 Azure Active Directory (AD) 提供标识即服务 (IDaaS)。为了采用 Microsoft 365 企业版，Contoso 的 IDaaS 解决方案必须利用其本地标识提供程序，并仍然包括其现有受信任的第三方标识提供程序提供的联合身份验证。

## <a name="contosos-windows-server-ad-forest"></a>Contoso 的 Windows Server AD 林

Contoso 将单个 Windows Server Active Directory (AD) 林用于具有七个子域的 contoso.com，每个子域代表全球的一个区域。总部、区域中心办事处和分支办事处包含用于本地身份验证和授权的域控制器。

图 1 显示 Contoso 林和包含区域中心的全球各个区域的区域性域。

![](./media/contoso-identity/contoso-identity-fig1.png)
 
**图 1：全球的 Contoso 林和域**

Contoso 想要在 contoso.com 林中使用帐户和组来对其基于云的应用和工作负载进行身份验证和授权。

## <a name="contosos-federated-authentication-infrastructure"></a>Contoso 的联合身份验证基础结构

Contoso 允许：

- 客户使用 Microsoft、Facebook 或 Google Mail 帐户登录其公共网站。
- 供应商和合作伙伴使用他们的领英、Salesforce 或 Google Mail 帐户登录合作伙伴 Extranet。

图 2 显示包含一个公共网站、一个合作伙伴 Extranet 和一组 Active Directory 联合身份验证服务 (AD FS) 服务器的 Contoso DMZ。DMZ 已连接至包含客户、合作伙伴和 Internet 服务的 Internet。

![](./media/contoso-identity/contoso-identity-fig2.png)

**图 2：Contoso 对客户和合作伙伴的联合身份验证支持**
 
DMZ 中的 AD FS 服务器会对用以访问公共网站的客户凭据进行身份验证，并对用以访问合作伙伴 Extranet 的合作伙伴凭据进行身份验证。

Contoso 决定保留此基础结构，并将其用于客户和合作伙伴身份验证。Contoso 标识工程师正在调查如何将此基础结构转换为 Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) 和 [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) 解决方案。

## <a name="hybrid-identity-with-pass-through-authentication-for-cloud-based-authentication"></a>通过混合标识和传递身份验证实现基于云的身份验证

Contoso 想要利用其本地 Windows Server AD 林来进行针对 Microsoft 365 云资源的身份验证。它决定采用具有密码哈希同步 (PHS) 的传递身份验证 (PTA)。

### <a name="pta-authentication"></a>PTA 身份验证

Contoso 将使用 PTA 来对用户凭据进行身份验证。当 Contoso 用户访问基于云的资源时，Azure AD 会将他们发送的凭据传递到 Contoso 总部数据中心中运行身份验证代理的服务器上。其中一个身份验证代理服务器会代表 Azure AD 验证用户凭据。

图 3 显示 Contoso 总部中一组运行身份验证代理的服务器，这些服务器会处理 Azure AD 传递给它们的身份验证请求。 

![](./media/contoso-identity/contoso-identity-fig3.png)
 
**图 3：Contoso 的传递身份验证基础结构**

Contoso 选择使用 PTA 来满足其安全要求，即在评估任何身份验证尝试后迅速改变用户帐户状态、密码策略和在本地 Windows Server AD 林上的登录时间。

### <a name="phs"></a>PHS

PHS 将本地 Windows Server AD 林与 Microsoft 365 企业版订阅的 Azure AD 租户同步，同时复制用户和组帐户以及哈希版用户帐户密码。Contoso 已决定采用 PHS，从而在 PTA 不可用时提供直接向 Azure AD 租户验证的替代身份验证方法。

为了执行持续目录同步，Contoso 在其巴黎数据中心的服务器上部署了 Azure AD Connect 工具。图 4 显示运行 Azure AD Connect 的服务器，该服务器会轮询 Contoso Windows Server AD 林来查找更改，然后将这些更改与 Azure AD 租户同步。

![](./media/contoso-identity/contoso-identity-fig4.png)
 
**图 4：Contoso 的 PHS 目录同步基础结构**

## <a name="conditional-access-policies-for-identity"></a>针对标识的条件访问策略

Contoso 创建了一组 Azure AD [条件访问策略](identity-access-policies.md)，以确保在 Azure AD 确定某个身份验证请求存在登录风险时强制实施多重身份验证和密码更改。

图 5 显示他们最终得到的一组针对标识的条件访问策略。

![](./media/contoso-identity/contoso-identity-fig5.png)
 
**图 5：Contoso 的基于标识的条件访问策略**

## <a name="next-step"></a>后续步骤

[了解](contoso-win10.md) Contoso 如何利用其 System Center Configuration Manager 基础结构在组织中部署 Windows 10 企业版并使之保持最新。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版的标识](identity-infrastructure.md)

[部署指南](deploy-microsoft-365-enterprise.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)
