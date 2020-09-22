---
title: 安全地让用户登录到 Microsoft 365 租户
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/16/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 要求用户通过多重身份验证（MFA）和其他功能安全地登录。
ms.openlocfilehash: 6c8f58e54ae21b4a5e1566dc72673e1d69152863
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132235"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a>安全地让用户登录到 Microsoft 365 租户

若要增强用户登录的安全性，请执行以下操作：

- 使用 Azure Active Directory (Azure AD) 密码保护
- 使用多重身份验证 (MFA)
- 部署标识和设备访问策略

## <a name="azure-ad-password-protection"></a>Azure AD 密码保护

Azure AD 密码保护会检测并阻止已知的弱密码及其变体，还会阻止特定于你组织的额外弱项。 默认全局禁止使用的密码列表将自动应用于 Azure AD 租户中的所有用户。 可在自定义禁止密码列表中定义额外条目。 用户更改或重置其密码时，将检查这些禁止的密码列表，强制使用强密码。

有关详细信息，请参阅“[配置 Azure AD 密码保护](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)”。

## <a name="mfa"></a>MFA

MFA 要求用户登录受用户帐户密码之外的其他验证约束。 即使恶意用户确定了用户帐户密码，还必须能够响应其他验证（如发送到智能手机的短信）才能获得访问权限。

![正确的密码和其他验证会导致登录成功](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

使用 MFA 的第一步是***对所有管理员帐户要求使用 MFA***，这些帐户也被称为特权帐户。

比第一步更好的是，Microsoft 强烈建议对所有用户要求使用 MFA。

根据 Microsoft 365 套餐，可通过三种方式要求你的管理员或用户使用 MFA。

| 计划 | 建议 |
|---------|---------|
|所有 Microsoft 365 套餐（无 Azure AD Premium P1 或 P2 许可证）     |[在 Azure AD 中启用安全性默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 Azure AD 中的安全性默认值于用户和管理员的 MFA。   |
|Microsoft 365 E3 （包括 Azure AD Premium P1 许可证）     | 使用[常用条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)配置以下策略： <br>- [要求对管理员执行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [要求对所有用户执行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [阻止传统身份验证](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 （包括 Azure AD Premium P2 许可证）     | 利用 Azure AD 标识保护，通过创建以下两个策略开始实施 Microsoft [推荐的一组条件访问和相关策略](../enterprise/identity-access-policies.md)：<br> - [要求在登录风险为“中等”或“高”时执行 MFA](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [高风险用户必须更改密码](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

### <a name="security-defaults"></a>安全性默认值

安全性默认值是在 2019 年 10 月 21 日之后创建的 Microsoft 365 和 Office 365 付费或试用版订阅的一项新功能。 这些订阅启用了安全性默认值，这***要求所有用户将 MFA 与 Microsoft Authenticator 应用配合使用***。
 
用户有 14 天的时间从其智能手机中通过 Microsoft Authenticator 应用登录 MFA，自启用安全性默认值后首次登录起计。 14 天后，除非 MFA 注册完成，否则用户将无法登录。

安全性默认值可确保所有组织均对默认启用的用户登录具有基本的安全级别。 可使用条件访问策略或针对个别帐户禁用安全性默认值，以支持 MFA。

有关详细信息，请参阅此[安全性默认值概述](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。

### <a name="conditional-access-policies"></a>条件访问策略

条件访问策略是一组规则，指定评估登录和授予访问的条件。 例如，你可以创建一个条件访问策略，指明：

- 如果用户帐户名是分配了 Exchange、用户、密码、安全性、SharePoint 或全局管理员角色的用户组的成员，则需要先进行 MFA，然后才能允许访问。

通过此策略，当为用户分配或取消分配了上述管理员角色时，你可以根据其组成员身份要求进行 MFA，而不是针对单个用户帐户进行 MFA 配置。

你还可以使用条件访问策略来实现更高级的功能，例如，要求从合规设备（例如运行 Windows 10 的电脑）完成登录。

条件访问需要 Microsoft 365 E3 和 E5 随附的 Azure AD Premium P1 许可证。

有关详细信息，请参阅此[条件访问概述](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。

### <a name="using-these-methods-together"></a>结合使用这些方法

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

## <a name="identity-and-device-access-policies"></a>标识和设备访问策略

标识和设备访问设置和策略是推荐的必备功能，而且它们的设置与用于确定是否应授予给定的访问请求，以及在何种情况下授予请求的“条件访问”、Intune 和 Azure AD 标识保护策略结合在了一起。 这种决定是基于登录的用户帐户、正在使用的设备、用户为获得访问权限而正在使用的应用程序、创建访问请求的位置，以及对请求风险的评估。 这个功能有助于确保只有经过批准的用户和设备才能访问关键的公司资源。

>[!Note]
>Azure AD 标识保护需要 Microsoft 365 E5 随附的 Azure AD Premium P2 许可证。
>

标识和设备访问策略被定义以用于三种层级： 

- 对于访问应用和数据的身份和设备，基线保护是最低级别的安全性。
- 敏感保护提供针对特定数据的额外安全性。 标识和设备遵循更高级别的安全性和设备运行状况要求。
- 对具有高度管控或分类数据的环境的保护仅用于高度分类、包含商业机密或遵守数据法规的一般少量数据。 标识和设备遵循非常高级别的安全性和设备运行状况要求。 

这些层及其相应的配置会跨数据、标识和设备，提供一致级别的保护。

Microsoft 强烈建议在组织中配置和推出标识和设备访问策略，包括 Microsoft Teams、Exchange Online 和 SharePoint 的特定设置。 有关详细信息，请参阅“[标识和设备访问配置](microsoft-365-policies-configurations.md)”。

<!--

## Let your users reset their own passwords

Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff. Users can quickly reset their passwords at any time and from any place. Watch [this video](https://go.microsoft.com/fwlink/?linkid=2128524) to set up SSPR.

## Sign in to SaaS apps with Azure AD

In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud. By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for your users to discover the applications they need and sign into them securely.

## Results of deployment of secure sign-ins

After deployment of MFA, your users:

- Are required to use MFA for sign-ins.
- Have completed the MFA registration process and are using MFA for all sign-ins.
- Can use SSPR to reset their own passwords.

- [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)

--> 

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>用于 MFA 和身份验证的管理员技术资源

- [适用于 Microsoft 365 的 MFA](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Microsoft 365 的识别指南](identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD 培训视频](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [配置多重身份验证注册策略](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [标识和设备访问配置](microsoft-365-policies-configurations.md)

