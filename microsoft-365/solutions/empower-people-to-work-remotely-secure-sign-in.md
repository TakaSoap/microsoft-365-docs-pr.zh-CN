---
title: 步骤 1. 通过 MFA 提高远程工作者的登录安全性
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: 要求远程工作者通过多重身份验证 (MFA) 登录。
ms.openlocfilehash: dfb4262c05399e1c5add9b151c42c143ac723a7d
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44066123"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a>步骤 1. 通过 MFA 提高远程工作者的登录安全性

要提高远程工作者的登录安全性，请使用多重身份验证 (MFA)。 MFA 要求用户登录受用户帐户密码之外的其他验证约束。 即使恶意用户确定了用户帐户密码，还必须能够响应其他验证（如发送到智能手机的短信）才能获得访问权限。

![正确的密码和其他验证会导致登录成功](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

对于所有用户（包括远程工作者，特别是管理员），Microsoft 强烈建议实施 MFA。

根据 Microsoft 365 套餐，可通过三种方式要求你的用户使用 MFA。

|套餐  |建议  |
|---------|---------|
|Microsoft 365 套餐（无 Azure AD Premium P1 或 P2）     |[在 Azure AD 中启用安全性默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD 中的安全性默认值于用户和管理员的 MFA。   |
|Microsoft 365 E3 （含 Azure AD Premium P1）     | 使用[常用条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)配置以下策略： <br>- [要求对管理员执行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [要求对所有用户执行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [阻止传统身份验证](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5（含 Azure AD Premium P2）     | 利用 Azure AD 标识保护，通过创建以下两个策略开始实施 Microsoft [推荐的一组条件访问和相关策略](../enterprise/identity-access-policies.md)：<br> - [要求在登录风险为“中等”或“高”时执行 MFA](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [阻止不支持新式身份验证的客户端](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [高风险用户必须更改密码](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>安全性默认值

安全性默认值是在 2019 年 10 月 21 日之后创建的 Microsoft 365 和 Office 365 付费或试用版订阅的一项新功能。 这些订阅启用了安全性默认值，这***要求所有用户将 MFA 与 Microsoft Authenticator 应用配合使用***。
 
用户有 14 天的时间从其智能手机中通过 Microsoft Authenticator 应用登录 MFA，自启用安全性默认值后首次登录起计。 14 天后，除非 MFA 注册完成，否则用户将无法登录。

安全性默认值可确保所有组织均对默认启用的用户登录具有基本的安全级别。 可使用条件访问策略或针对个别帐户禁用安全性默认值，以支持 MFA。

有关详细信息，请参阅此[安全性默认值概述](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。

## <a name="conditional-access-policies"></a>条件访问策略

条件访问策略是一组规则，指定评估和允许登录的条件。 例如，你可以创建一个条件访问策略，指明：

- 如果用户帐户名适用于作为 Exchange、用户、密码、安全性、SharePoint 或全局管理员的用户，则需要先进行 MFA，然后才能允许访问。

在这些管理员角色中添加或删除用户帐户时，此策略比尝试记住配置针对 MFA 的单个用户帐户要简单得多。

你还可以使用条件访问策略来实现更高级的功能，例如，要求从合规设备（例如运行 Windows 10 的电脑）完成登录。

条件访问需要 Microsoft 365 E3 和 E5 随附的 Azure AD Premium P1。

有关详细信息，请参阅此[条件访问概述](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。

## <a name="azure-ad-identity-protection-policies"></a>Azure AD 标识保护策略

Azure AD 标识保护策略是指定评估和允许登录的条件的规则。 例如，你可以创建一个 Azure AD 标识保护策略，指明：

- 如果登录风险确定为“中等”或“高”，则用户必须使用 MFA 登录。

Azure AD 标识保护需要 Microsoft 365 E5 随附的 Azure AD Premium P2。

有关详细信息，请参阅此 [Azure AD 标识保护概述](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。

## <a name="using-these-methods-together"></a>结合使用这些方法

请记住下列事项：

- 如果启用了任何条件访问策略，则无法启用安全性默认值。
- 如果启用了安全性默认值，则无法启用任何条件访问策略。

如果启用了安全性默认值，系统将提示所有新用户进行 MFA 注册并使用 Microsoft Authenticator 应用。 

下表显示了通过安全性默认值、条件访问策略和每用户帐户设置启用 MFA 的结果。

|| 已启用 | Disabled | 辅助身份验证方法 |
|:-------|:-----|:-------|:-------|
| **安全性默认值**  | 无法使用条件访问策略 | 可以使用条件访问策略 | Microsoft Authenticator 应用 |
| **条件访问策略** | 如果已启用任何条件访问策略，则无法启用安全性默认值 | 如果未启用任何条件访问策略，则可以启用安全性默认值  | 由用户在 MFA 注册期间指定  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a>用于 MFA 和身份的管理员培训和技术资源

- [适用于 Microsoft 365 的 MFA 计划](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [Azure AD 帮助你实现远程工作的 5 大方法](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [计划和部署 Microsoft 365 身份基础结构](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [Azure Academy Azure AD 培训视频](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [配置多重身份验证注册策略](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a>步骤 1 的结果

部署 MFA 之后，用户：

- 需要使用 MFA 进行登录。
- 已完成 MFA 注册流程，并将使用 MFA 进行所有登录。

## <a name="next-step"></a>后续步骤

继续执行[步骤 2](empower-people-to-work-remotely-remote-access.md)，提供对本地应用和服务的远程访问权限。
