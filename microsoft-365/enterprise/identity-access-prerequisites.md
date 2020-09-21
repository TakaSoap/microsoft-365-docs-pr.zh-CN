---
title: 实现标识和设备访问策略的先决条件工作-适用于企业的 Microsoft 365 |Microsoft 文档
description: 介绍在实现标识和设备访问策略和配置之前的先决条件。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/01/2020
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 5e6ea6adf30223d4750c2c38a6918482577b8d7f
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132020"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>实现标识和设备访问策略的先决条件工作

本文介绍了在部署推荐的标识和设备访问策略之前需要实现的先决条件。 本文还讨论建议的默认平台客户端配置，以向用户提供最佳单一登录 (SSO) 体验，以及条件访问技术的先决条件。

## <a name="prerequisites"></a>先决条件

在实施推荐的标识和设备访问策略之前，您的组织必须满足以下几个先决条件：您的组织必须满足 Microsoft 365 和 Office 365 的这些身份验证模型：

- 仅限云
- 使用密码哈希同步 (PHS) 身份验证的混合
- 混合使用传递身份验证 (PTA) 
- 联合

下表详细介绍了适用于所有标识模型的先决条件功能及其配置，但注明的情况除外。 

| 配置 | Exceptions |
| :------------- | :-----------: |
|  [配置 PHS](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。  必须启用此功能，以检测泄露的凭据并对其执行基于风险的条件访问。 **注意：** 无论您的组织是否使用联合身份验证，都是必需的。 | 仅限云 |
| [启用无缝单一登录](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) ，以便在用户位于连接到组织网络的组织设备上时自动对用户进行签名。 | 仅限云和联合  |
| [配置命名网络](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。 Azure AD Identity Protection 收集并分析所有可用的会话数据，以生成风险评分。 我们建议您在 Azure AD 的 "网络配置" 中为您的网络指定组织的公共 IP 范围。 来自这些范围的流量被授予降低风险分数，来自组织环境外部的流量将获得较高风险分数。 | |
|[为所有用户注册自助服务密码重置 (SSPR) and 多重身份验证 (MFA) ](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)。 我们建议您提前注册用户以进行 Azure 多重身份验证。 Azure AD Identity Protection 使用 Azure 多因素身份验证来执行其他安全验证。 此外，为了获得最佳登录体验，我们建议用户在其设备上安装 [Microsoft 身份验证器应用](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) 和 Microsoft 公司门户应用。 可以从每个平台的应用商店中安装这些。 | |
| [启用域加入域的 Windows 计算机的自动设备注册](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 条件访问将确保连接到应用程序的设备已加入域或合规性。 要在 Windows 计算机上支持此操作，必须已向 Azure AD 注册设备。  本文介绍了如何配置自动设备注册。 | 仅限云 |
| **准备支持团队**。 为无法完成 MFA 的用户制定计划。 这可能会将其添加到策略排除组中，或为其注册新的 MFA 信息。 在进行任何安全敏感更改之前，您需要确保实际用户发出请求。 请求用户的管理人员来帮助审批是一个有效的步骤。 | |  
| [配置密码写回到本地 AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。 密码写回允许 Azure AD 在检测到高风险帐户泄漏时要求用户更改其本地密码。 您可以通过以下两种方式之一在 Azure AD Connect 中启用此功能：在 Azure AD Connect 安装向导的 "可选功能" 屏幕中启用 **密码写回** ，或通过 Windows PowerShell 启用它。 | 仅限云 |
| [配置 AZURE AD 密码保护](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)。 Azure AD 密码保护检测并阻止已知弱密码及其变体，还可以阻止特定于您的组织的其他弱术语。 默认全局禁止密码列表将自动应用于 Azure AD 租户中的所有用户。 您可以在 "自定义禁止密码" 列表中定义其他条目。 当用户更改或重置其密码时，将检查这些禁止的密码列表，以强制使用强密码。 |  |
| [启用 Azure Active Directory 标识保护](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。 Azure AD Identity Protection 使您能够检测到影响组织的身份的潜在漏洞，并将自动修正策略配置为低、中和高的登录风险和用户风险。  | |
| 为[Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)和[Skype For business Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)**启用新式验证**。 新式验证是使用 MFA 的先决条件。 默认情况下，将为 Office 2016 和2019客户端、SharePoint 和 OneDrive for business 启用新式验证。 |  |
|||

## <a name="recommended-client-configurations"></a>推荐的客户端配置
本节介绍了我们建议的默认平台客户端配置，以向用户提供最佳的 SSO 体验，以及条件访问的技术先决条件。

### <a name="windows-devices"></a>Windows 设备
我们建议 Windows 10 (版本2004或更) 高版本，因为 Azure 旨在提供内部部署和 Azure AD 最不能实现的 SSO 体验。 应将工作或学校签发的设备配置为直接加入 Azure AD，或者如果组织使用内部部署 AD 域加入，应将这些设备 [配置为自动并以无提示方式注册到 AZURE ad](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。

对于 BYOD Windows 设备，用户可以使用 " **添加工作或学校帐户**"。 请注意，Windows 10 设备上的 Google Chrome browser 的用户需要 [安装扩展](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) 才能获得与 Microsoft Edge 用户相同的平滑登录体验。 此外，如果您的组织具有加入域的 Windows 8 或8.1 设备，则可以为非 Windows 10 计算机安装 Microsoft Workplace Join。 [下载程序包以](https://www.microsoft.com/download/details.aspx?id=53554) 使用 Azure AD 注册设备。

### <a name="ios-devices"></a>iOS 设备
建议在部署条件访问或 MFA 策略之前，在用户设备上安装 [Microsoft 身份验证器应用程序](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) 。 在要求用户通过添加工作或学校帐户向 Azure AD 注册设备时，或者在安装 Intune 公司门户应用程序以将其设备注册到管理中时，应至少安装应用程序。 这取决于配置的条件访问策略。

### <a name="android-devices"></a>Android 设备
建议用户在部署条件访问策略之前安装 [Intune 公司门户应用程序](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) 和 [Microsoft 身份验证器应用](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) ，或在特定身份验证尝试过程中需要时安装。 安装应用后，系统可能会要求用户向 Azure AD 注册或向 Intune 注册设备。 这取决于配置的条件访问策略。

此外，我们还建议在支持使用 Android for Work 或 Samsung Knox 的 Oem 和版本上标准化组织拥有的设备，以允许通过 Intune MDM 策略管理和保护邮件帐户。


### <a name="recommended-email-clients"></a>推荐的电子邮件客户端
以下电子邮件客户端支持新式身份验证和条件访问。 

|平台|客户端|版本/说明|
|:-------|:-----|:------------|
|**Windows**|Outlook|2019、2016、2013 <BR> [启用新式验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)、 [所需更新](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook for iOS|[最新版本](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新版本](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019和2016|
|**Linux**|不支持||
|||

### <a name="recommended-client-platforms-when-securing-documents"></a>保护文档时推荐使用的客户端平台

如果应用了安全文档策略，则建议使用以下客户端。

|平台|Word/Excel/PowerPoint|OneNote|OneDrive 应用|SharePoint 应用|[OneDrive 同步客户端](https://docs.microsoft.com/onedrive/enable-conditional-access)|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 8.1|支持|支持|不适用|不适用|支持|
|Windows 10|支持|支持|不适用|不适用|支持|
|Android|支持|支持|支持|支持|不适用|
|iOS|支持|支持|支持|支持|不适用|
|macOS|支持|支持|不适用|不适用|不支持|
|Linux|不支持|不支持|不支持|不支持|不支持|

### <a name="microsoft-365-client-support"></a>Microsoft 365 客户端支持

有关 Microsoft 365 中的客户端支持的详细信息，请参阅以下文章：

- [Microsoft 365 客户端应用支持-条件访问](microsoft-365-client-support-conditional-access.md)
- [Microsoft 365 客户端应用程序支持-新式验证](microsoft-365-client-support-modern-authentication.md)

## <a name="protecting-administrator-accounts"></a>保护管理员帐户

对于 Microsoft 365 E3 或 E5 或使用单独的 Azure AD Premium P1 或 P2 许可证，您可以要求具有手动创建的条件访问策略的对管理员帐户进行 MFA。 有关详细信息，请参阅 [条件访问：需要针对管理员的 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) 。

对于不支持条件访问的 Microsoft 365 或 Office 365 版本，可以启用 [安全默认设置](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) ，要求对所有帐户进行 MFA。

以下是一些附加建议：

- 使用 [AZURE AD 特权标识管理](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started) 来减少永久管理帐户的数量。 
- [使用 "特权访问管理](../compliance/privileged-access-management-overview.md) " 保护您的组织免受可能使用现有特权管理员帐户访问敏感数据或访问关键配置设置的用户泄露的情况。 
- 创建和使用仅分配了[Microsoft 365 管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)*的单独帐户进行管理*。 管理员应拥有自己的用户帐户以进行常规非管理，并且仅在必要时才使用管理帐户来完成与其角色或作业功能相关联的任务。 
- 遵循在 Azure AD 中保护特权帐户的 [最佳做法](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) 。

## <a name="next-step"></a>后续步骤

[![步骤2：配置公共标识和访问条件访问策略](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[配置通用标识和设备访问策略](identity-access-policies.md)
