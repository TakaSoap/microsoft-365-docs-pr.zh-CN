---
title: Microsoft 365客户端和服务应用支持
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 本文查找有关客户端Microsoft 365服务应用支持的详细信息。
ms.openlocfilehash: 4ae294865bb506ae9e8a25e8f5ab28fff967171e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173320"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Microsoft 365客户端和服务应用支持

Microsoft 支持多种安全、身份验证和合规性功能，以确保客户数据安全，并允许 IT 管理员在其用户Microsoft 365 管理中心自定义策略。 以下功能只是许多企业功能的子集，您可以根据你的企业Microsoft 365配置。

## <a name="client-and-service-support"></a>客户端和服务支持

### <a name="continuous-access-evaluation-preview"></a>连续访问评估 (预览) 

连续访问评估通过启用服务（如 Exchange Online、SharePoint Online 和 Teams）来订阅 Azure Active Directory 中的关键事件，以便几乎可以实时地评估和强制执行这些事件。 关键事件评估不依赖于条件访问策略，因此可在任何租户中使用。

当前评估以下事件：

- 删除或禁用用户帐户
- 更改或重置用户的密码
- 为用户启用多重身份验证
- 管理员显式撤消用户的所有刷新令牌
- Azure AD Identity Protection 检测到的提升的用户风险

有关客户端和服务应用支持的连续访问评估的详细信息，请参阅连续访问评估 ([预览) 。 ](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)

## <a name="client-support"></a>客户端支持

### <a name="certificate-based-authentication"></a>基于证书的身份验证

CBA (基于证书) 是使用数字证书在授予对资源、网络、应用程序或服务的访问权限之前标识用户、计算机或设备。 在用户身份验证中，它通常与用户名和密码等传统方法协调部署。

某些传统解决方案仅适用于用户，例如生物识别以及 OTP (一) 。 使用基于证书的身份验证，可针对所有终结点使用相同的解决方案;用户、设备和不断增多的物联网 (IoT) 。

有关客户端和服务应用支持的基于证书的身份验证Microsoft 365请参阅客户端[应用支持：基于证书的身份验证](microsoft-365-client-support-certificate-based-authentication.md)。

### <a name="conditional-access"></a>条件访问

条件访问是组织用来将信号Azure Active Directory、做出决策以及强制执行组织访问策略的工具。 条件访问是新的标识驱动控件模型的核心。

条件访问策略是 if-then 语句，用于授予对资源的访问权限。 如果用户希望访问资源，则用户必须完成一个操作。 条件访问在做出策略访问决策时可以使用的常见信号包括：

- 用户或组成员身份
- IP 位置信息
- 设备信息
- 应用程序信息
- 实时和计算的风险检测
- Microsoft Cloud App Security (MCAS)

做出这些访问决策时，策略可以采取不同的操作：

- 策略可以阻止访问：此配置是最严格的操作，可阻止用户访问资源。
- 策略可以授予访问权限：此配置是限制较少的决策，可能仍然需要以下一个或多个选项：

    - 多重身份验证
    - 要标记为合规的设备
    - 设备已加入混合 Azure AD
    - 已批准的客户端应用程序
    - 在预览版中配置 (保护) 

有关客户端和服务应用支持的条件访问详细信息，请参阅：

- [Microsoft 365客户端应用支持：基于设备的条件访问](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>移动应用管理

用户通常从同一移动设备访问组织和个人文档、电子邮件和数据。 这些设备通常归个人所有，应配置为保护组织数据和用户的个人隐私。

用户访问组织数据时，组织必须确保应用组织策略（如配置策略和保护策略）以帮助保护设备上的组织数据。 此外，用户设备上的个人内容应保持在组织控制之外。

对于组织管理的内容，您可以应用应用程序管理策略，以控制如何使用 Microsoft Intune 访问、共享和使用数据。 例如，支持以下操作：

- 远程擦除托管组织 (也称为组织数据) 
- 防止将组织内容粘贴到非组织位置
- 需要 PIN 来访问组织内容
- 阻止托管应用在已越狱或获得 root 权限的设备上运行
- 阻止将组织内容保存到未经批准的云存储提供程序
- 阻止将未经批准的内容传输到托管应用程序中
- 仅在应用了策略后，才允许访问组织内容
- 提供应用程序配置以管理应用程序的行为和设置
- 通过禁用多标识功能或个人用法，将托管应用程序限制为定义的标识

有关使用应用程序管理移动应用程序Microsoft Intune，请参阅什么是Microsoft Intune[应用程序管理？](/mem/intune/apps/app-management)

### <a name="multi-factor-authentication"></a>多重身份验证

[MFA (多重身份验证) 是计算机访问控制的一种方法，在该方法中，只有在向身份验证机制成功呈现多个单独证据后，用户才被授予访问权限。 此方法通常至少使用下列两种类别：

- 知识 (他们了解) 
- 拥有 (他们拥有) 
- 不一 (它们) 

有关客户端和服务应用支持的多重身份验证详细信息，请参阅Microsoft 365[客户端应用支持：多重身份验证](microsoft-365-client-support-multi-factor-authentication.md)。

### <a name="single-sign-on"></a>单一登录

SSO (单一登录) 当用户登录到 SSO 中的应用程序时，可添加安全性和Azure Active Directory。 借助单一登录，用户可以使用一个帐户登录一次，以访问本地 Active Directory 域服务 (AD DS) 已加入域的设备、软件即服务 (SaaS) 应用程序和您组织的 Web 应用程序。

有关客户端和服务应用支持的单一登录信息，请参阅Microsoft 365[客户端应用支持：单一登录。](microsoft-365-client-support-single-sign-on.md)

## <a name="services-support"></a>服务支持

### <a name="modern-authentication"></a>新式验证

新式身份验证使客户能够针对 Office 365 进行身份验证的新方案，以及租户管理员在整个租户Office 365特定的身份验证要求，例如：

- 对与租赁和服务的管理交互以及最终用户与应用程序及其数据的交互的多重身份验证支持
- 条件访问
- 基于 SAML 的第三方标识提供程序登录
- 个人计算机上的智能卡日志
- 移动设备上基于证书的身份验证
- 不再需要通过基本身份验证传输凭据。

有关新式身份验证服务支持的信息，请参阅身份验证 [与授权](/azure/active-directory/develop/authentication-vs-authorization)。

### <a name="azure-active-directory-conditional-access"></a>Azure Active Directory 条件访问

Azure Active Directory (Azure AD) 条件访问规则允许客户根据设备合规性或网络位置等属性控制对联机服务的访问。 可能会使用下列解决方案：

- 基于 Azure AD 多重身份验证的条件访问
- 基于 Azure AD 位置的条件访问
- 基于 Azure AD 设备的条件访问

Azure AD 条件访问规则适用于每个应用程序，客户可以使用这些规则根据不同的条件控制访问。 使用[移动设备管理 (MDM) 或 Intune，](/mem/intune/fundamentals/what-is-device-management)客户必须能够将 Microsoft 365 的访问权限限制为仅针对使用组织设备或已注册其个人设备进行管理的用户。 例如，客户可以配置条件访问规则以强制执行如下控件：

- 仅允许从已加入域或符合域的设备访问
- 强制对服务的所有访问进行多重Exchange Online身份验证

有关条件访问Azure Active Directory，请参阅[什么是条件访问？](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>TLS 1.2 支持

为了为客户提供一流的加密，Microsoft 计划停止支持 Office 365 和 Office 365 GCC 中的传输层安全性 (TLS) 版本 1.0 和 1.1。

我们知道您的数据的安全性非常重要，并且我们承诺对可能影响使用 TLS 服务的更改保持透明公开。 我们建议所有客户端-服务器和浏览器-服务器组合使用 TLS 1.2 (或更高版本) 来维护与 Office 365 服务的连接。 你可能必须更新某些客户端-服务器和浏览器-服务器组合。

有关 TLS 1.2 支持和服务支持的信息，请参阅 Office 365 和 Office 365 GCC 中的准备[TLS 1.2。](../compliance/prepare-tls-1.2-in-office-365.md)