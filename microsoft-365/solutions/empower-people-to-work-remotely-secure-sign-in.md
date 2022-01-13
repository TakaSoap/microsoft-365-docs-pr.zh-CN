---
title: 步骤 1 为使用 MFA 的混合工作者提高登录安全性
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: 要求混合工作者使用多重身份验证 (MFA) 登录。
ms.openlocfilehash: dfcda3eb0f79003a3e09bbda9d3c53dff6ae2f8f
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61934821"
---
# <a name="step-1-increase-sign-in-security-for-hybrid-workers-with-mfa"></a>步骤 1 为使用 MFA 的混合工作者提高登录安全性

要提高远程工作者的登录安全性，请使用多重身份验证 (MFA)。 MFA 要求用户登录受用户帐户密码之外的其他验证约束。 即使恶意用户确定了用户帐户密码，还必须能够响应其他验证（如发送到智能手机的短信）才能获得访问权限。

![正确的密码和其他验证会导致登录成功。](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

对于所有用户（包括远程工作者，特别是管理员），Microsoft 强烈建议实施 MFA。

根据 Microsoft 365 套餐，可通过三种方式要求你的用户使用 MFA。

|套餐  |建议  |
|---------|---------|
|所有 Microsoft 365 套餐（无 Azure AD Premium P1 或 P2 许可证）     |[在 Azure AD 中启用安全性默认值](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD 中的安全性默认值于用户和管理员的 MFA。   |
|Microsoft 365 E3 （包括 Azure AD Premium P1 许可证）     | 使用[常用条件访问策略](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)配置以下策略： <br>- [要求对管理员执行 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [要求对所有用户执行 MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [阻止传统身份验证](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 （包括 Azure AD Premium P2 许可证）     | 借助 Azure AD 标识保护，创建以下策略来开始实施 Microsoft [推荐的一组条件访问和相关策略](../security/office-365-security/identity-access-policies.md)：<br> - [要求在登录风险为“中等”或“高”时执行 MFA](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [阻止不支持新式身份验证的客户端](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br>- [高风险用户必须更改密码](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>安全性默认值

安全性默认值是在 2019 年 10 月 21 日之后创建的 Microsoft 365 和 Office 365 付费或试用版订阅的一项新功能。 这些订阅启用了安全性默认值，这 ***要求所有用户将 MFA 与 Microsoft Authenticator 应用配合使用***。
 
用户有 14 天的时间从其智能手机中通过 Microsoft Authenticator 应用登录 MFA，自启用安全性默认值后首次登录起计。 14 天后，除非 MFA 注册完成，否则用户将无法登录。

安全性默认值可确保所有组织均对默认启用的用户登录具有基本的安全级别。 可使用条件访问策略或针对个别帐户禁用安全性默认值，以支持 MFA。

有关详细信息，请参阅此[安全性默认值概述](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。

## <a name="conditional-access-policies"></a>条件访问策略

条件访问策略是一组规则，指定评估和允许登录的条件。 例如，你可以创建一个条件访问策略，指明：

- 如果用户帐户名是分配了 Exchange、用户、密码、安全性、SharePoint 或全局管理员角色的用户组的成员，则需要先进行 MFA，然后才能允许访问。

通过此策略，当为用户分配或取消分配了上述管理员角色时，你可以根据其组成员身份要求进行 MFA，而不是针对单个用户帐户进行 MFA 配置。

你还可以使用条件访问策略来实现更高级的功能，例如要求从合规设备（例如运行 Windows 11 或 10 的电脑）完成登录。

条件访问需要 Microsoft 365 E3 和 E5 随附的 Azure AD Premium P1 许可证。

有关详细信息，请参阅此[条件访问概述](/azure/active-directory/conditional-access/overview)。

## <a name="azure-ad-identity-protection-support"></a>Azure AD 标识保护支持

借助 Azure AD 标识保护，你可以创建其他条件访问策略，该策略规定：

- 如果登录风险确定为中等或高风险，则必须进行 MFA。

Azure AD 标识保护需要 Microsoft 365 E5 随附的 Azure AD Premium P2 许可证。

有关详细信息，请参阅[基于风险的条件访问](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users)。

借助 Azure Active Directory 标识保护，你还可创建一个策略来要求用户注册 MFA。 有关详细信息，请参阅[配置 Azure 多重身份验证注册策略](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)


## <a name="using-these-methods-together"></a>结合使用这些方法

请注意以下几点：

- 如果启用了任何条件访问策略，则无法启用安全性默认值。
- 如果启用了安全性默认值，则无法启用任何条件访问策略。

如果启用了安全性默认值，系统将提示所有新用户进行 MFA 注册并使用 Microsoft Authenticator 应用。 

下表显示了通过安全性默认值和条件访问策略启用 MFA 的结果。

| 方法 | 已启用 | 禁用 | 其他身份验证方法 |
|:-------|:-----|:-------|:-------|
| **安全性默认值**  | 无法使用条件访问策略 | 可以使用条件访问策略 | Microsoft Authenticator 应用 |
| **条件访问策略** | 如果已启用任何条件访问策略，则无法启用安全性默认值 | 如果已禁用所有条件访问策略，则可以启用安全性默认值  | 由用户在 MFA 注册期间指定  |
||||

## <a name="let-your-users-reset-their-own-passwords"></a>允许用户重置自己的密码

自助密码重置 (SSPR) 使用户可以重置自己的密码，而不会影响 IT 人员。 用户可随时随地快速重置其密码。 有关详细信息，请查阅[计划 Azure AD 自助服务密码重置部署](/azure/active-directory/authentication/howto-sspr-deployment)。

## <a name="sign-in-to-saas-apps-with-azure-ad"></a>使用 Azure AD 登录 SaaS 应用

除了为用户提供云身份验证之外，Azure AD 还可以是保护所有应用（无论是本地、Microsoft 云中还是其他云中的应用）的主要方法。 通过[将应用集成到 Azure AD 中](/azure/active-directory/manage-apps/plan-an-application-integration)，你可以轻松地帮助远程工作者发现他们所需的应用程序并进行安全登录。

## <a name="admin-technical-resources-for-mfa-and-identity"></a>用于 MFA 和身份验证的管理员技术资源

- [Azure AD 帮助你实现远程工作的 5 大方法](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Microsoft 365 的识别指南](../enterprise/identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD 培训视频](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)

## <a name="results-of-step-1"></a>步骤 1 的结果

部署 MFA 之后，用户：

- 需要使用 MFA 进行登录。
- 已完成 MFA 注册流程，并将使用 MFA 进行所有登录。
- 可以使用 SSPR 重置他们自己的密码。

## <a name="next-step"></a>后续步骤

[![步骤 2：提供对本地应用和服务的远程访问权限。](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)

继续执行[步骤 2](empower-people-to-work-remotely-remote-access.md)，提供对本地应用和服务的远程访问权限。