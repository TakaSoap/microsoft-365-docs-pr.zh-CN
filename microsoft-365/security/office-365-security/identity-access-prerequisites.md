---
title: 实现标识和设备访问策略的先决条件工作 - 企业Microsoft 365策略|Microsoft Docs
description: 本文介绍了使用零信任标识和设备访问策略和配置时需要满足的先决条件。
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
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: ba9694be615f0c669ed0b9c319909551ccf02315
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62244615"
---
# <a name="prerequisite-work-for-implementing-zero-trust-identity-and-device-access-policies"></a>实现零信任标识和设备访问策略的先决条件工作

本文介绍了管理员使用推荐的零信任标识和设备访问策略以及使用条件访问必须满足的先决条件。 此外，还讨论为 SSO (最佳单一登录体验配置客户端) 默认值。

## <a name="prerequisites"></a>先决条件

在使用建议的零信任标识和设备访问策略之前，组织需要满足先决条件。 对于列出的各种标识和身份验证模型，要求是不同的：

- 仅限云
- 使用密码哈希同步与 PHS (身份验证) 混合
- 使用传递身份验证与 PTA (混合) 
- Federated

下表详细介绍了适用于所有标识模型的先决条件功能及其配置（除非已指出）。

|配置|Exceptions|授权|
|---|:---:|---|
|[配置 PHS](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。  必须启用此功能，以检测泄露的凭据，并针对基于风险的条件访问处理这些凭据。 **注意：** 无论组织是否使用联合身份验证，都需要这样做。|仅限云|Microsoft 365 E3 或 E5|
|[启用无缝单一登录](/azure/active-directory/connect/active-directory-aadconnect-sso) ，以在用户连接到组织网络的组织设备上时自动登录。|仅云和联合|Microsoft 365 E3 或 E5|
|[配置命名位置](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)。 Azure AD Identity Protection 收集并分析所有可用的会话数据，以生成风险评分。 建议在命名位置配置中为网络指定Azure AD IP 范围。 来自这些范围的流量的风险评分将降低，来自组织环境外部的流量获得的风险评分更高。||Microsoft 365 E3 或 E5|
|[注册所有用户以使用 SSPR (和多重身份验证) MFA (重置) 。 ](/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) 我们建议你提前注册Azure AD多重身份验证的用户。 Azure AD Identity Protection 利用多Azure AD身份验证执行其他安全验证。 此外，为了获得最佳登录体验，我们建议用户在设备上安装[Microsoft Authenticator 和](/azure/active-directory/user-help/microsoft-authenticator-app-how-to)Microsoft 公司门户 应用。 可以从每个平台的应用商店安装这些组件。||Microsoft 365 E3 或 E5|
|[启用已加入域的计算机的自动Windows注册](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 条件访问将确保连接到应用的设备已加入域或符合域。 要在 Windows 计算机上支持此操作，必须已向 Azure AD 注册设备。  本文介绍了如何配置自动设备注册。|仅限云|Microsoft 365 E3 或 E5|
|**准备支持团队**。 为无法完成 MFA 的用户制定计划。 这可以是将它们添加到策略排除组，或者为它们注册新的 MFA 信息。 在做出上述任一安全敏感更改之前，您需要确保实际用户正在提出请求。 请求用户的管理人员来帮助审批是一个有效的步骤。||Microsoft 365 E3 或 E5|
|[配置密码写回到本地 AD](/azure/active-directory/active-directory-passwords-getting-started)。 密码写回Azure AD在检测到高风险帐户泄露时要求用户更改其本地密码。 您可以使用以下两Azure AD 连接之一启用此功能：在安装程序的可选功能屏幕中启用密码写Azure AD 连接，或通过 Windows PowerShell 启用。|仅限云|Microsoft 365 E3 或 E5|
|[配置Azure AD密码保护 。](/azure/active-directory/authentication/concept-password-ban-bad) Azure AD 密码保护会检测并阻止已知的弱密码及其变体，还会阻止特定于你组织的额外弱项。 默认全局禁止使用的密码列表将自动应用于 Azure AD 租户中的所有用户。 可在自定义禁止密码列表中定义额外条目。 用户更改或重置其密码时，将检查这些禁止的密码列表，强制使用强密码。||Microsoft 365 E3 或 E5|
|[启用Azure Active Directory Identity Protection 。](/azure/active-directory/identity-protection/overview-identity-protection) Azure AD Identity Protection，可以检测影响组织标识的潜在漏洞，将自动修正策略配置为低、中、高登录风险和用户风险。||Microsoft 365 E5或Microsoft 365 E3 E5 安全附加设备|
|**为 Exchange Online** [和](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)Skype for Business Online [启用新式验证](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。 新式验证是使用 MFA 的先决条件。 默认情况下，为 Office 2016 和 2019 客户端、SharePoint和 OneDrive for Business 启用新式OneDrive for Business。||Microsoft 365 E3 或 E5|
|[为用户启用连续](microsoft-365-continuous-access-evaluation.md)访问Azure AD。 连续访问评估会主动终止活动用户会话，并近实时强制执行租户策略更改。||Microsoft 365 E3 或 E5|
|

## <a name="recommended-client-configurations"></a>推荐的客户端配置

本节介绍建议的默认平台客户端配置，以便为用户提供最佳的 SSO 体验，以及条件访问的技术先决条件。

### <a name="windows-devices"></a>Windows 设备

我们建议Windows 11或 Windows 10 (版本 2004 或更高版本) ，因为 Azure 旨在为本地和 Azure AD 提供尽可能流畅的 SSO 体验。 工作或学校颁发的设备应配置为直接加入 Azure AD或者如果组织使用本地 AD 域加入，则这些设备应配置为自动以静默方式向 Azure AD[注册](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。

对于 BYOD Windows设备，用户可以使用 **"添加工作或学校帐户"。** 请注意，Windows 11 或 Windows 10 设备上 Google Chrome 浏览器的用户需要安装扩展，才能[](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)获得与 Microsoft Edge 相同的登录体验。 此外，如果你的组织拥有加入域Windows 8或 8.1 设备，你可以为非计算机安装 Microsoft Workplace Join Windows 10加入。 [下载程序包以向](https://www.microsoft.com/download/details.aspx?id=53554)设备注册Azure AD。

### <a name="ios-devices"></a>iOS 设备

我们建议在部署条件[Microsoft Authenticator](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) MFA 策略之前，在用户设备上安装应用。 至少，当要求用户通过添加工作或学校帐户向 Azure AD 注册其设备时，或者当他们安装 Intune 公司门户应用以将其设备注册到管理中时，应安装该应用。 这取决于配置的条件访问策略。

### <a name="android-devices"></a>Android 设备

建议用户在部署条件[Intune 公司门户或在](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en)Microsoft Authenticator身份验证尝试期间需要[](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)时安装应用和应用。 安装应用后，系统可能会要求用户向 Azure AD 注册或向 Intune 注册设备。 这取决于配置的条件访问策略。

我们还建议组织拥有的设备在支持 Android for Work 或 Samsung Knox 的 OEM 和版本上实现标准化，以允许邮件帐户、受 Intune MDM 策略管理和保护。

### <a name="recommended-email-clients"></a>推荐的电子邮件客户端

以下电子邮件客户端支持新式验证和条件访问。

|平台|客户端|版本/说明|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [启用新式验证](../../admin/security-and-compliance/enable-modern-authentication.md) <p> [所需更新](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook for iOS|[最新版本](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新版本](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 和 2016|
|**Linux**|不支持||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>保护文档时推荐使用的客户端平台

应用安全文档策略后，建议以下客户端。

|平台|Word/Excel/PowerPoint|OneNote|OneDrive 应用|SharePoint 应用|[OneDrive 同步客户端](/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 11 或 Windows 10|支持|支持|不适用|不适用|受支持|
|Windows 8.1|支持|支持|不适用|不适用|受支持|
|Android|支持|支持|支持|支持|不适用|
|iOS|支持|支持|支持|支持|不适用|
|macOS|支持|支持|不适用|不适用|不支持|
|Linux|不支持|不支持|不支持|不支持|不支持|
|

### <a name="microsoft-365-client-support"></a>Microsoft 365 客户端支持

有关客户端支持在 Microsoft 365，请参阅以下文章：

- [Microsoft 365客户端应用支持 - 条件访问](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Microsoft 365客户端应用支持 - 多重身份验证](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>保护管理员帐户

对于Microsoft 365 E3 E5 或具有Azure AD Premium P1或 P2 许可证，可以使用手动创建的条件访问策略要求管理员帐户使用 MFA。 有关详细信息[，请参阅条件访问：要求管理员使用 MFA。](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)

对于不支持Microsoft 365访问的 Office 365 版本，可以启用安全默认值以要求所有帐户使用 MFA。 [](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

下面是一些其他建议：

- 使用[Azure AD Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-getting-started)减少永久管理帐户的数量。
- [使用特权访问管理](../../compliance/privileged-access-management-overview.md) 保护组织免受可能使用现有特权管理员帐户（长期访问敏感数据或访问关键配置设置）的泄露。
- 创建和使用单独的帐户，这些帐户Microsoft 365 [管理员角色进行](../../admin/add-users/about-admin-roles.md)*管理*。 管理员应拥有自己的用户帐户用于常规的非管理用途，并且仅在必要时使用管理帐户来完成与其角色或作业功能相关联的任务。
- 遵循[保护](/azure/active-directory/admin-roles-best-practices)企业中的特权帐户Azure AD。

## <a name="next-step"></a>后续步骤

[![步骤 2：配置常见的零信任标识和访问条件访问策略。](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[配置常见的零信任标识和设备访问策略](identity-access-policies.md)