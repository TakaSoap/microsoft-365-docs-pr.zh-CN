---
title: 企业版持续Microsoft 365 - Microsoft 365访问评估
description: 介绍如何对用户和Microsoft 365条件Azure AD主动终止活动用户会话，并近实时强制执行租户策略更改。
ms.author: dansimp
author: dansimp
manager: dansimp
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: e265fd09fa7442b24868ad7f001701ef567e32bd
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681559"
---
# <a name="continuous-access-evaluation-for-microsoft-365"></a>连续访问评估Microsoft 365

使用 OAuth 2.0 进行身份验证的新式云服务通常依赖访问令牌过期来撤销用户帐户的访问权限。 实际上，这意味着即使管理员吊销了用户帐户的访问权限，用户仍将具有访问权限，直到访问令牌过期（默认情况下，对于 Microsoft 365，在初始吊销事件发生后最多一小时）。

Microsoft 365和 Azure Active Directory (Azure AD) 条件访问评估会主动终止活动用户会话，并几乎实时强制执行租户策略更改，而不是依赖访问令牌过期。 Azure AD当用户帐户或租户更改了需要重新计算用户帐户的身份验证状态的方式更改时，Microsoft 365 服务 (（如 SharePoint、Teams 和 Exchange) ）通知连续访问评估。

当启用连续访问评估的客户端Outlook现有访问令牌Exchange访问令牌时，服务将拒绝该令牌，并提示Azure AD身份验证。 结果是几乎实时强制执行用户帐户和策略更改。

下面是一些附加优势：

- 对于在组织外部复制和导出有效访问令牌的恶意内部人员，连续访问评估会阻止通过 Azure AD IP 地址位置策略来使用此令牌。 通过持续访问评估，Azure AD将策略向下同步到受支持的 Microsoft 365 服务，因此当访问令牌尝试从策略的 IP 地址范围外访问该服务时，该服务将拒绝令牌。

- 连续访问评估通过减少令牌刷新来改进恢复能力。 由于支持服务会收到有关需要重新身份验证的主动Azure AD，因此，例如，超过 1 小时，支持服务可以颁发长期令牌。 使用长期令牌，客户端不必经常从 Azure AD请求令牌刷新，因此用户体验更具弹性。

下面是连续访问评估可提高用户访问控制安全性的一些示例：

- 用户帐户的密码已被泄露，因此管理员将使所有现有会话失效，并重置其密码，Microsoft 365 管理中心。 在近实时中，所有使用现有服务的现有Microsoft 365都失效。

- 在 Word 中处理文档的用户将平板电脑放在管理员定义和批准的 IP 地址范围外的公共咖啡店中。 在咖啡店中，将立即阻止用户访问文档。

例如Microsoft 365，当前支持连续访问评估：

- Exchange、SharePoint 和 Teams 服务。
- Outlook、Teams、Office 和 OneDrive Web 浏览器以及 Win32、iOS、Android 和 Mac 客户端访问。

Microsoft 正在努力开发其他 Microsoft 365 服务和客户端，以支持持续访问评估。

连续访问评估将包含在 Office 365 和 Microsoft 365。 配置条件访问策略Azure AD Premium P1，该策略包含在所有 Microsoft 365 版本中。

> [!NOTE]
> 有关 [连续](/azure/active-directory/conditional-access/concept-continuous-access-evaluation#limitations) 访问评估的限制，请参阅本文。

## <a name="scenarios-supported-by-microsoft-365"></a>支持的方案Microsoft 365

连续访问评估支持两种类型的事件：

- 关键事件是用户应失去访问权限的事件。
- 当用户应基于管理员定义的策略失去对资源的访问权限时，将发生条件访问策略评估。

关键事件包括：

- 用户帐户已禁用
- 更改密码
- 用户会话被吊销
- 为用户启用多重身份验证
- 帐户风险根据对 Identity Protection 中访问Azure AD[增加](/azure/active-directory/identity-protection/overview-identity-protection)

当用户帐户不再从受信任的网络连接时，将发生条件访问策略评估。

以下Microsoft 365服务当前通过侦听来自用户的事件来支持连续访问Azure AD。

|强制类型|Exchange|SharePoint|Teams|
|---|---|---|---|
|**关键事件：**||||
|用户吊销|支持|支持|支持|
|用户风险|支持|不支持|不支持|
|**条件访问策略评估：**||||
|IP 地址位置策略|受支持|支持\*|受支持|

\*SharePoint Office Web 浏览器访问支持通过启用严格模式来实施即时 IP 策略。 如果没有严格模式，访问令牌生存期为 1 小时。

若要详细了解如何设置条件访问策略，请参阅 [本文](/azure/active-directory/conditional-access/overview)。

## <a name="microsoft-365-clients-supporting-continuous-access-evaluation"></a>Microsoft 365连续访问评估的客户端

Microsoft 365 的启用连续访问评估的客户端支持声明质询，当启用连续访问评估的 Microsoft 365 服务拒绝缓存的用户令牌时，声明质询会将用户会话重定向到 Azure AD 以用于重新身份验证。

以下客户端支持 Web、Win32、iOS、Android 和 Mac 上的连续访问评估：

- Outlook
- Teams
- 办公室\*
- SharePoint
- OneDrive

\*声明质询在 Web Office上不受支持。

对于不支持连续访问评估的客户端，默认Microsoft 365访问令牌生存期保留为 1 小时。

## <a name="see-also"></a>另请参阅

- [连续访问评估](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)
- [条件访问文档](/azure/active-directory/conditional-access/overview)
- [Azure AD Identity Protection 文档](/azure/active-directory/identity-protection/overview-identity-protection)
