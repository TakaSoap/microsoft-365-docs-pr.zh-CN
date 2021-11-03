---
title: 企业版连续访问Microsoft 365 - Microsoft 365访问评估
description: 介绍用户和用户Microsoft 365条件Azure AD如何主动终止活动用户会话，并近实时强制执行租户策略更改。
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-overview
ms.technology: mdo
ms.openlocfilehash: 1625f266bff322bf77f6eeaeb0d0690853587dad
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661714"
---
# <a name="continuous-access-evaluation-for-microsoft-365"></a>连续访问评估Microsoft 365

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)

使用 OAuth 2.0 进行身份验证的新式云服务通常依赖访问令牌过期来撤销用户帐户的访问权限。 实际上，这意味着即使管理员吊销了用户帐户的访问权限，用户仍将具有访问权限，直到访问令牌过期（默认情况下，对于 Microsoft 365，在初始吊销事件发生后最多一小时）。  

Microsoft 365和 Azure Active Directory (Azure AD) 条件访问评估会主动终止活动用户会话，并几乎实时强制执行租户策略更改，而不是依赖访问令牌过期。 Azure AD用户帐户或租户更改需要重新计算用户帐户的身份验证状态的方式发生更改时， (会通知启用连续访问评估的 Microsoft 365 服务 (如 SharePoint、Teams 和 Exchange) 。 

当启用连续访问评估的客户端（Outlook尝试使用现有访问Exchange访问令牌）时，服务将拒绝该令牌，并提示新的Azure AD身份验证。 结果是几乎实时强制执行用户帐户和策略更改。  

下面是一些附加优势：

- 对于在组织外部复制和导出有效访问令牌的恶意预览体验成员，连续访问评估会阻止通过 AZURE AD IP 地址位置策略来Azure AD令牌。 通过持续访问评估，Azure AD将策略向下同步到受支持的 Microsoft 365 服务，因此当访问令牌尝试从策略的 IP 地址范围外访问该服务时，该服务将拒绝令牌。 

- 连续访问评估通过减少令牌刷新来改进恢复能力。 由于支持服务会收到有关需要重新身份验证的主动Azure AD，因此，例如，超过 1 小时，支持服务可以颁发长期令牌。 对于长期令牌，客户端不必经常从 Azure AD请求令牌刷新，因此用户体验更具弹性。

下面是连续访问评估可提高用户访问控制安全性的一些示例： 

- 用户帐户的密码已被泄露，因此管理员将使所有现有会话失效，并重置其密码，Microsoft 365 管理中心。 在近实时中，所有现有用户会话Microsoft 365服务无效。 

- 在 Word 中处理文档的用户将平板电脑放在管理员定义和批准的 IP 地址范围外的公共咖啡店中。 在咖啡店中，将立即阻止用户访问文档。 

例如Microsoft 365，当前支持连续访问评估：

- Exchange、SharePoint 和 Teams 服务。 
- Outlook、Teams、Office 和 OneDrive Web 浏览器以及 Win32、iOS、Android 和 Mac 客户端。 

Microsoft 正在努力开发其他 Microsoft 365 服务和客户端，以支持持续访问评估。 

连续访问评估将包含在 Office 365 和 Microsoft 365。 配置条件访问策略Azure AD Premium P1，该策略包含在所有 Microsoft 365 版本中。

>[!Note]
>有关 [连续](/azure/active-directory/conditional-access/concept-continuous-access-evaluation#limitations) 访问评估的限制，请参阅本文。
>

## <a name="scenarios-supported-by-microsoft-365"></a>支持的方案Microsoft 365 

连续访问评估支持两种类型的事件： 

- 关键事件是用户应失去访问权限的事件。 
- 当用户应基于管理员定义的策略失去对资源的访问权限时，将发生条件访问策略评估。  

关键事件包括： 

- 用户帐户已禁用 
- 更改密码 
- 用户会话被吊销 
- 为用户启用多重身份验证 
- 帐户风险根据对 Identity Protection 中访问[Azure AD增加](/azure/active-directory/identity-protection/overview-identity-protection)

当用户帐户不再从受信任的网络连接时，将发生条件访问策略评估。 

以下Microsoft 365服务当前通过侦听来自用户的事件来支持连续访问Azure AD。  

| 强制类型  | Exchange | SharePoint | Teams |
|:-------|:-----|:-------|:-------|
| **关键事件：** |  |  |  |
| 用户吊销 | 支持 | 支持 | 支持 |
| 用户风险 | 支持 | 不支持 | 不支持 |
| **条件访问策略评估：** |  |  |  |
| IP 地址位置策略 | 支持 | 支持* | 支持 |

* SharePoint Office Web 浏览器访问支持通过启用严格模式来实施即时 IP 策略。 如果没有严格模式，访问令牌生存期为 1 小时。   

若要详细了解如何设置条件访问策略，请参阅 [本文](/azure/active-directory/conditional-access/overview)。

## <a name="microsoft-365-clients-supporting-continuous-access-evaluation"></a>Microsoft 365连续访问评估的客户端 

当启用连续访问评估的 Microsoft 365 服务拒绝缓存的用户令牌时，Microsoft 365 的启用连续访问评估的客户端支持声明质询，即用户会话重定向到 Azure AD 进行重新身份验证。  

以下客户端支持 Web、Win32、iOS、Android 和 Mac 上的连续访问评估： 

- Outlook 
- Teams 
- Office*
- SharePoint 
- OneDrive 

* 声明质询在 Web Office上不受支持。

对于不支持连续访问评估的客户端，默认Microsoft 365访问令牌生存期保留为 1 小时。    

## <a name="see-also"></a>另请参阅

- [连续访问评估](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)
- [条件访问文档](/azure/active-directory/conditional-access/overview)
- [Azure ADIdentity Protection 文档](/azure/active-directory/identity-protection/overview-identity-protection)
