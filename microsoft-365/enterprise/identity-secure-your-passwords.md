---
title: 步骤2：保护密码安全
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 你需要确保你的密码在整个组织中都强大并易于管理。
ms.openlocfilehash: c0ad9e2ad86cb803484e3d350fe112580610f509
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544051"
---
# <a name="step-2-secure-your-passwords"></a>第 2 步：保护密码安全

![第 2 阶段 - 标识](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>防止密码错误

*这是可选的，适用于 Microsoft 365 的 E3 和 E5 版本*

所有用户都应使用 [Microsoft 的密码指南](https://www.microsoft.com/research/publication/password-guidance/)来创建用户帐户密码。

若要防止用户创建易于确定的密码，请使用 Azure AD 密码保护，该功能同时使用全局阻止密码列表和你指定的可选的自定义禁止密码列表。 例如，你可以指定特定于贵组织的术语，例如：

- 品牌名称
- 产品名称
- 位置（例如公司总部）
- 特定于公司的内部条款
- 具有特定公司含义的缩写

可[在云端](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)和[本地 Active Directory 域服务 (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) 中禁止错误密码。

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-password-prot)。

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>简化密码重置

*这是可选的，适用于 Microsoft 365 的 E3 和 E5 版本*

在此部分中，将启用自助密码重置 (SSPR)，以允许用户重置或解除锁定其密码或帐户。 为提醒你避免误用或滥用，可以使用详细报告，跟踪用户访问系统的时间，并进行通知。 必须先启用密码写回，然后才能部署密码重置。

请参阅[推出密码重置说明](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：密码重置](password-reset-m365-ent-test-environment.md) |
|||

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-pw-reset)。


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>简化用户登录

*这对于混合环境来说是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此部分中，将设置 Azure Active Directory 无缝单一登录（Azure AD 无缝 SSO），该功能与密码哈希同步 (PHS) 和传递身份验证 (PTA) 一起使用，以允许用户登录到使用 Azure AD 用户帐户的服务，而无需键入其密码（在许多情况下，还无需键入用户名）。 这可使用户更方便地访问基于云的应用程序（如 Office 365）而无需任何额外的本地组件（如联合身份验证服务器）。

将使用 Azure AD Connect 工具配置 Azure AD 无缝 SSO。

请参阅[配置 Azure AD 无缝 SSO 说明](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：Azure AD 无缝单一登录](single-sign-on-m365-ent-test-environment.md) |
|||

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-sso)。


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a>自定义 Office 365 登录页

*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此部分中，将帮助用户通过添加公司名称、徽标和其他可识别元素来识别组织的登录页。 

使用 Microsoft 365 企业版，可以自定义登录页和访问面板页的外观，使其包含公司徽标、配色方案和自定义用户信息。 

有关详细信息，请参阅[向 Office 365 登录页添加公司品牌](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)。

有关配置说明，请参阅[向登录页和访问面板页添加公司品牌](https://aka.ms/aadpaddbranding)。

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-custom-sign-in)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![第 3 步](../media/stepnumbers/Step3.png)| [保护和管理用户登录](identity-secure-user-sign-ins.md) |
