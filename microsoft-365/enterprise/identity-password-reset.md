---
title: 步骤 5：简化用户访问权限
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置 Azure AD 自助密码重置 (SSPR)。
ms.openlocfilehash: ec81b2931fd4ad599ffcf983ea8a7d764c56404a
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981793"
---
# <a name="step-5-simplify-access-for-users"></a>步骤 5：简化用户访问权限

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>简化密码更新

*这对于混合环境来说是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此部分中，将允许用户通过 Azure Active Directory (AD) 重置其密码，然后复制到本地 Active Directory 域服务 (AD DS)。 此过程称为密码写回。 通过密码写回，用户不需要通过本地 AD DS（用户帐户及其属性的存储位置）更新其密码。 这非常适用于对本地网络没有远程访问连接的漫游或远程用户。

需要密码写回才可充分利用 Azure AD 标识保护功能，例如，当检测到高风险的帐户泄露时要求用户更改其本地密码。

有关其他信息和配置说明，请参阅 [Azure AD SSPR 密码写回](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)。

>[!Note]
>升级到最新版本的 Azure AD Connect，以确保即时获取最佳体验和新功能。有关详细信息，请参阅 [Azure AD Connect 自定义安装](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。
>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：密码写回](password-writeback-m365-ent-test-environment.md) |
|||

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-pw-writeback)。

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>简化密码重置

*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此部分中，将启用自助密码重置 (SSPR)，以允许用户重置或解除锁定其密码或帐户。 为提醒你避免误用或滥用，可以使用详细报告，跟踪用户访问系统的时间，并进行通知。 必须先启用密码写回，然后才能部署密码重置。

请参阅[推出密码重置说明](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：密码重置](password-reset-m365-ent-test-environment.md) |
|||

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-pw-reset)。


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>简化用户登录

*这对于混合环境来说是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此部分中，将设置 Azure Active Directory 无缝单一登录（Azure AD 无缝 SSO），以允许用户登录到使用 Azure AD 用户帐户的服务，而无需键入其密码（在许多情况下，还无需键入用户名）。 这可使用户更方便地访问基于云的应用程序（如 Office 365）而无需任何额外的本地组件（如联合身份验证服务器）。

将使用 Azure AD Connect 工具配置 Azure AD 无缝 SSO。

请参阅[配置 Azure AD 无缝 SSO 说明](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：Azure AD 无缝单一登录](single-sign-on-m365-ent-test-environment.md) |
|||

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-sso)。


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a>自定义 Office 365 登录页

*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*

在此部分中，将帮助用户通过添加公司名称、徽标和其他可识别元素来识别组织的登录页。 

使用 Microsoft 365 企业版，可以自定义登录页和访问面板页的外观，使其包含公司徽标、配色方案和自定义用户信息。 

有关详细信息，请参阅[向 Office 365 登录页添加公司品牌](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)。

有关配置说明，请参阅[向登录页和访问面板页添加公司品牌](http://aka.ms/aadpaddbranding)。

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-custom-sign-in)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [使用组实现更轻松地管理](identity-self-service-group-management.md) |


