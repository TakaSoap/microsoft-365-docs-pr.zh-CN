---
title: 实现标识和设备访问策略的先决条件工作 - Microsoft 365 企业版|Microsoft Docs
description: 本文介绍了使用标识和设备访问策略和配置时必须满足的先决条件。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
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
ms.openlocfilehash: 53d64d869b80c6fe5c6e0954a00af5b6f5359356
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233082"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>实现标识和设备访问策略的先决条件工作

**适用对象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- Azure

本文介绍了管理员使用推荐的标识和设备访问策略以及使用条件访问必须满足的先决条件。 它还讨论为 SSO) 体验的最佳单一登录配置客户端 (默认值。

## <a name="prerequisites"></a>先决条件

在使用建议的标识和设备访问策略之前，组织需要满足先决条件。 列出的各种标识和身份验证模型的要求不同：

- 仅限云
- 使用密码哈希同步和 PHS (混合) 身份验证
- 使用 PTA 身份验证的 (混合) 
- 联合

下表详细介绍了适用于所有标识模型的先决条件功能及其配置（除非已说明）。

|配置|Exceptions|
|---|:---:|
|[配置 PHS](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。  必须启用此功能，以检测泄露的凭据，并针对基于风险的条件访问对凭据采取行动。 **注意：** 无论组织是否使用联合身份验证，都需要这样做。|仅限云|
|[启用无缝单一登录](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) ，以在用户位于连接到组织网络的组织设备上时自动登录。|仅云和联合|
|[配置命名位置](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations)。 Azure AD Identity Protection 收集并分析所有可用的会话数据，以生成风险评分。 我们建议你在 Azure AD 命名位置配置中为网络指定组织的公用 IP 范围。 为来自这些范围的流量提供一个降低的风险分数，并且来自组织环境外部的流量获得更高的风险分数。||
|[注册所有用户，以使用 SSPR ](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) (和多重身份验证) MFA (重置) 。 我们建议你提前为用户注册 Azure AD 多重身份验证。 Azure AD Identity Protection 利用 Azure AD 多重身份验证执行其他安全验证。 此外，为了获得最佳登录体验，我们建议用户在设备上安装 [Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) 应用和 Microsoft 公司门户应用。 可以从每个平台的应用商店安装这些组件。||
|[启用已加入域的 Windows 计算机的自动设备注册](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 条件访问将确保连接到应用的设备已加入域或符合域。 要在 Windows 计算机上支持此操作，必须已向 Azure AD 注册设备。  本文介绍了如何配置自动设备注册。|仅限云|
|**准备支持团队**。 为无法完成 MFA 的用户制定计划。 这可以是将它们添加到策略排除组，或者为它们注册新的 MFA 信息。 在做出上述任一安全敏感更改之前，您需要确保实际用户正在提出请求。 请求用户的管理人员来帮助审批是一个有效的步骤。||
|[配置密码写回到本地 AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。 密码写回允许 Azure AD 要求用户在检测到高风险帐户泄露时更改其本地密码。 可以通过以下两种方式之一使用 Azure AD Connect 启用此功能：在 Azure AD Connect 设置向导的可选功能屏幕中启用密码写回，或通过 Windows PowerShell。|仅限云|
|[配置 Azure AD 密码保护](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)。 Azure AD 密码保护会检测并阻止已知的弱密码及其变体，还会阻止特定于你组织的额外弱项。 默认全局禁止使用的密码列表将自动应用于 Azure AD 租户中的所有用户。 可在自定义禁止密码列表中定义额外条目。 用户更改或重置其密码时，将检查这些禁止的密码列表，强制使用强密码。||
|[启用 Azure Active Directory 标识保护](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。 借助 Azure AD Identity Protection，可以检测影响组织标识的潜在漏洞，将自动修正策略配置为低、中、高登录风险和用户风险。||
|**为 Exchange** [Online 和](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) [Skype for Business Online 启用新式验证](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。 新式验证是使用 MFA 的先决条件。 默认情况下，为 Office 2016 和 2019 客户端、SharePoint 和 OneDrive for Business 启用新式验证。||
|

## <a name="recommended-client-configurations"></a>推荐的客户端配置

本节介绍我们建议为用户提供最佳 SSO 体验的默认平台客户端配置，以及条件访问的技术先决条件。

### <a name="windows-devices"></a>Windows 设备

我们建议使用 Windows 10 (版本 2004 或更高版本) ，因为 Azure 旨在为本地和 Azure AD 提供尽可能流畅的 SSO 体验。 工作或学校颁发的设备应配置为直接加入 Azure AD，或者如果组织使用本地 AD 域加入，则这些设备应配置为自动以无提示方式注册[Azure AD。](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)

对于 BYOD Windows 设备，用户可以使用 **添加工作或学校帐户**。 请注意，Windows 10 设备上 Google Chrome 浏览器的用户需要[](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)安装扩展，才能获得与 Microsoft Edge 用户相同的流畅登录体验。 此外，如果你的组织具有加入域的 Windows 8 或 8.1 设备，你可以为非 Windows 10 计算机安装 Microsoft Workplace Join。 [下载程序包以向](https://www.microsoft.com/download/details.aspx?id=53554) Azure AD 注册设备。

### <a name="ios-devices"></a>iOS 设备

我们建议在部署条件访问或 MFA 策略之前，在用户设备上安装 [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) 应用。 至少，当用户通过添加工作或学校帐户要求他们向 Azure AD 注册设备时，或者当他们安装 Intune 公司门户应用以将其设备注册到管理中时，应安装该应用。 这取决于配置的条件访问策略。

### <a name="android-devices"></a>Android 设备

我们建议用户在部署条件访问策略之前或在某些身份验证尝试期间需要时安装 [Intune 公司](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) 门户应用和 [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) 应用。 安装应用后，系统可能会要求用户向 Azure AD 注册或向 Intune 注册设备。 这取决于配置的条件访问策略。

我们还建议在支持 Android for Work 或 Samsung Knox 的 OEM 和版本上对组织拥有的设备进行标准化，以允许邮件帐户，由 Intune MDM 策略进行管理和保护。

### <a name="recommended-email-clients"></a>推荐的电子邮件客户端

以下电子邮件客户端支持新式身份验证和条件访问。

|平台|客户端|版本/说明|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [启用新式验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication) <p> [所需的更新](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook for iOS|[最新版本](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新版本](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 和 2016|
|**Linux**|不支持||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>保护文档时推荐使用的客户端平台

应用安全文档策略时，建议以下客户端。

|平台|Word/Excel/PowerPoint|OneNote|OneDrive 应用|SharePoint 应用|[OneDrive 同步客户端](https://docs.microsoft.com/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|支持|支持|不适用|不适用|受支持|
|Windows 10|支持|支持|不适用|不适用|受支持|
|Android|支持|支持|支持|支持|不适用|
|iOS|支持|支持|支持|支持|不适用|
|macOS|支持|支持|不适用|不适用|不支持|
|Linux|不支持|不支持|不支持|不支持|不支持|
|

### <a name="microsoft-365-client-support"></a>Microsoft 365 客户端支持

有关 Microsoft 365 中的客户端支持详细信息，请参阅以下文章：

- [Microsoft 365 客户端应用支持 - 条件访问](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Microsoft 365 客户端应用支持 - 多重身份验证](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>保护管理员帐户

对于 Microsoft 365 E3 或 E5 或具有单独的 Azure AD Premium P1 或 P2 许可证，可以使用手动创建的条件访问策略要求管理员帐户使用 MFA。 有关详细信息[，请参阅条件访问：要求管理员使用 MFA。](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)

对于不支持条件访问的 Microsoft 365 或 Office 365 版本，可以[](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)启用安全默认值以要求所有帐户使用 MFA。

下面是一些其他建议：

- 使用 [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started) 减少永久管理帐户的数量。
- [使用特权访问管理](../../compliance/privileged-access-management-overview.md) 保护组织免受可能使用现有特权管理员帐户的漏洞，这些帐户具有对敏感数据的长期访问权限或关键配置设置的访问权限。
- 创建和使用分配 [有 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)管理员角色的单独 *帐户，用于管理*。 管理员应拥有自己的用户帐户，用于常规的非管理用途，并且仅在必要时使用管理帐户来完成与其角色或作业功能相关联的任务。
- 遵循 [在](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) Azure AD 中保护特权帐户的最佳实践。

## <a name="next-step"></a>后续步骤

[![步骤 2：配置通用标识和访问条件访问策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[配置通用标识和设备访问策略](identity-access-policies.md)
