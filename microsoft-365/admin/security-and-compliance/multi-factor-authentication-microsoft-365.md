---
title: Microsoft 365 的多重身份验证
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 Microsoft 365 中的多因素身份验证。
ms.openlocfilehash: 128296b7dbc37ba5ebffb25a87bce589f8e5a904
ms.sourcegitcommit: 185d62f41f6b173894ba6e3e87b11b2b5d02db58
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "44340819"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Microsoft 365 的多重身份验证

密码是对计算机或联机服务进行身份验证的最常用方法，但它们也最容易受到攻击。 用户可以选择轻松使用密码，并将相同的密码用于多个登录到不同的计算机和服务。

若要为登录提供额外的安全级别，必须使用多重身份验证（MFA），该身份验证使用密码（应为 "强"）和其他验证方法（基于）：

- 您对其具有不容易复制的内容，例如智能手机。
- 您唯一且 biologically 的内容，如您的指纹、面孔或其他生物特征属性。

只有在验证了用户的密码之后，才会再采用其他验证方法。 通过 MFA，即使安全性较强的用户密码，攻击者也没有您的智能手机或指纹即可完成登录。

## <a name="mfa-support-in-microsoft-365"></a>Microsoft 365 中的 MFA 支持
默认情况下，Microsoft 365 和 Office 365 支持对用户帐户进行 MFA，使用：

- 发送到要求用户键入验证代码的电话的短信。
- 电话呼叫。
- Microsoft 身份验证器智能电话应用程序。

在这两种情况下，MFA 登录使用的是 "与你有的事情不容易复制" 方法进行其他验证。
可以通过多种方式为 Microsoft 365 和 Office 365 启用 MFA：

- 使用安全默认值
- 使用条件访问策略
- 对于每个单独的用户帐户（不推荐）

这些方法基于 Microsoft 365 计划。
    
|套餐  |建议  | 客户类型 |
|---------|---------|----------|
| 所有 Microsoft 365 计划 | 使用安全默认设置，这需要对所有用户帐户进行 MFA。 <br> 您还可以基于每个用户的帐户要求进行 MFA，但不建议这样做。 | 小型企业 |
| Microsoft 365 商业高级版 <br><br> Microsoft 365 E3 <br><br> Azure Active Directory （Azure AD）高级 P1 许可证 | 使用条件访问策略根据组成员身份、应用或其他条件要求对用户帐户进行 MFA。 | 小型企业到企业 |
| Microsoft 365 E5 <br><br> Azure AD 高级 P2 许可证 | 使用 Azure AD 标识保护根据登录风险条件要求进行 MFA。 |  企业版 |
||||

### <a name="security-defaults"></a>安全性默认值

安全性默认值是在 2019 年 10 月 21 日之后创建的 Microsoft 365 和 Office 365 付费或试用版订阅的一项新功能。 这些订阅启用了安全默认设置，其中：

- 要求所有用户都使用与 Microsoft 身份验证器应用的 MFA。
- 阻止旧版身份验证。

用户有 14 天的时间从其智能手机中通过 Microsoft Authenticator 应用登录 MFA，自启用安全性默认值后首次登录起计。 14 天后，除非 MFA 注册完成，否则用户将无法登录。

安全性默认值可确保所有组织均对默认启用的用户登录具有基本的安全级别。 您可以禁用安全默认设置，以支持使用条件访问策略的 MFA。

您可以在 Azure 门户中的 Azure AD 的**属性**窗格中启用或禁用安全默认设置。

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

您可以使用任何 Microsoft 365 计划的安全性默认设置。

有关详细信息，请参阅此[安全性默认值概述](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。 

### <a name="conditional-access-policies"></a>条件访问策略

条件访问策略是一组规则，指定评估和允许登录的条件。 例如，你可以创建一个条件访问策略，指明：

- 如果用户帐户名是分配了 Exchange、用户、密码、安全性、SharePoint 或全局管理员角色的用户组的成员，则需要先进行 MFA，然后才能允许访问。

通过此策略，当为用户分配或取消分配了上述管理员角色时，你可以根据其组成员身份要求进行 MFA，而不是针对单个用户帐户进行 MFA 配置。

您还可以使用条件访问策略进行更高级的功能，例如，要求对特定应用进行 MFA，或在兼容设备（如运行 Windows 10 的便携式计算机）上完成登录。

在 Azure 门户中，从 Azure AD 的 "**安全**" 窗格中配置条件访问策略。

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

您可以通过以下方式使用条件访问策略：

- Microsoft 365 商业高级版
- Microsoft 365 E3 和 E5
- Azure AD 高级 P1 和 Azure AD 高级 P2 许可证 

对于具有 Microsoft 365 商业高级版的小型企业，可以通过以下步骤轻松使用条件访问策略：

1. 创建一个组，以包含需要进行 MFA 的用户帐户。
2. 启用 "**要求对全局管理员进行 MFA** " 策略。
3. 使用以下设置创建基于组的条件访问策略：
    - > 用户和组的工作分配：上述步骤1中的组名称。
    - 云应用或操作 > 的工作分配：所有云应用。
    - 访问控制 > 授予 > 授予访问权限 > 需要多重身份验证。
4. 启用该策略。
5. 将用户帐户添加到在上面的步骤1中创建的组并进行测试。
6. 若要对其他用户帐户要求进行 MFA，请将其添加到在步骤1中创建的组。

通过此条件访问策略，您可以按自己的步调向用户展示 MFA 要求。

企业应使用[常见的条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)来配置以下策略：

- [要求对管理员执行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [要求对所有用户执行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [阻止传统身份验证](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

有关详细信息，请参阅此[条件访问概述](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

使用 Azure AD Identity Protection，可以创建额外的条件访问策略，以便[在登录风险为中或高时需要进行 MFA](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)。

您可以使用 Azure AD 标识保护和基于风险的条件访问策略：

- Microsoft 365 E5
- Azure AD 高级 P2 许可证

有关详细信息，请参阅此 [Azure AD 标识保护概述](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。

### <a name="mfa-for-an-individual-user-account-not-recommended"></a>对单个用户帐户的 MFA （不推荐）

应使用安全默认设置或条件访问策略来要求对用户帐户登录进行 MFA。但是，如果无法使用其中一种方法，Microsoft 强烈建议对具有管理员角色（尤其是全局管理员角色）的用户帐户进行 MFA，以进行任何大小订阅。 

您可以从 Microsoft 365 管理中心的 "**活动用户**" 窗格中为单个用户帐户启用 MFA。

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

启用后，下次用户登录时，系统将提示他们注册 MFA，并选择和测试其他验证方法。

### <a name="using-these-methods-together"></a>结合使用这些方法

下表显示了通过安全性默认值、条件访问策略和每用户帐户设置启用 MFA 的结果。

|| 已启用 | Disabled | 辅助身份验证方法 |
|:-------|:-----|:-------|:-------|
| **安全性默认值** | 无法使用条件访问策略 |   可以使用条件访问策略 | Microsoft Authenticator 应用 |
| **条件访问策略** |如果已启用任何条件访问策略，则无法启用安全性默认值 | 如果已禁用所有条件访问策略，则可以启用安全性默认值 | 由用户在 MFA 注册期间指定 |
| **每用户帐户设置（不推荐）** | 由需要 MFA 的安全默认值和条件访问策略重写 | 由安全默认值和条件访问策略重写 | 由用户在 MFA 注册期间指定|
||||

如果启用了安全默认设置，则系统会提示用户在下一次登录时进行 MFA 注册和使用 Microsoft 身份验证器应用的所有新用户。

但是，如果用户具有可接收短信但无法运行 Microsoft 验证程序应用程序的较旧的电话，则可以对该特定用户帐户启用 MFA，并让它们使用文本代码其他验证方法注册这些步骤：

1. 禁用 Azure 门户中的安全默认设置。
2. 为 Microsoft 365 管理中心中的用户帐户启用 MFA。
3. 让用户登录并注册 MFA 和文本代码身份验证方法。
4. 完成后，在 Azure 门户中启用安全默认设置

## <a name="ways-to-manage-mfa-settings"></a>管理 MFA 设置的方法

有两种管理 MFA 设置的方法。

在 Azure 门户中，可以执行以下操作：

- 启用和禁用安全默认设置
- 配置条件访问策略

在 Microsoft 365 管理中心，您可以配置每用户和服务 MFA 设置。

## <a name="your-next-step"></a>下一步

[为 Microsoft 365 设置 MFA](set-up-multi-factor-authentication.md)

