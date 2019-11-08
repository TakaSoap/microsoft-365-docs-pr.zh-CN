---
title: 实现标识和设备访问策略的先决条件工作-Microsoft 365 企业版 |Microsoft 文档
description: 介绍针对有关如何应用标识和设备访问策略以及配置的 Microsoft 建议的策略。
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 667dfe355aca61eff99a85c2a2c29ee0b57e74c5
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "38030957"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>实现标识和设备访问策略的先决条件工作

本文介绍了在部署推荐的标识和设备访问策略之前需要实现的先决条件。 本文还讨论了我们建议的默认平台客户端配置，以向用户提供最佳的 SSO 体验，以及条件访问的技术先决条件。


## <a name="prerequisites"></a>先决条件

在实施推荐的标识和设备访问策略之前，您的组织必须满足几个先决条件。 下表详细介绍了适用于您的环境的先决条件。 


| 配置 | 仅云 | 具有密码哈希同步的 Active Directory |  传递身份验证 |  与 AD FS 的联盟 |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [配置密码哈希同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)。必须启用此功能，以检测泄露的凭据并对其执行基于风险的条件访问。 **注意：** 无论您的组织使用的是托管身份验证（如传递身份验证（PTA）还是联合身份验证），都是必需的。 |    | 是 | 是 | 是 |
| [启用无缝单一登录](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso)，以便在用户位于连接到公司网络的公司设备上时自动对用户进行签名。 |  | 是 | 是 |  |
| [配置命名网络](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。 Azure AD Identity Protection 收集并分析所有可用的会话数据，以生成风险评分。 我们建议您在 Azure AD 的 "网络配置" 中为您的网络指定组织的公共 IP 范围。 来自这些范围的流量被授予降低风险分数，从公司环境外部的流量获得的风险分数越高。 | 是  | 是 | 是 | 是 |
|[为所有用户注册自助密码重置（SSPR）和多因素身份验证（MFA）](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)。 我们建议您提前为 Azure MFA 注册用户。 Azure AD Identity Protection 利用 Azure MFA 来执行其他安全性验证。 此外，为了获得最佳登录体验，我们建议用户在其设备上安装[Microsoft 身份验证器应用](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to)和 Microsoft 公司门户应用。 可以从每个平台的应用商店中安装这些。 | 是 | 是 | 是 | 是 |
| [启用域加入域的 Windows 计算机的自动设备注册](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 条件访问将确保连接到应用程序的设备已加入域或合规性。 要在 Windows 计算机上支持此操作，必须已向 Azure AD 注册设备。  本文介绍了如何配置自动设备注册。 |   | 是 |  是 |  是 |
| **准备支持团队**。 为无法完成 MFA 的用户制定计划。 这可能会将其添加到策略排除组中，或为其注册新的 MFA 信息。 在进行任何安全敏感更改之前，您需要确保实际用户发出请求。 请求用户的管理人员来帮助审批是一个有效的步骤。 | 是 | 是 | 是 | 是 |  
| [配置密码写回到本地 AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。 密码写回允许 Azure AD 在检测到高风险帐户泄漏时要求用户更改其本地密码。 您可以通过以下两种方式之一在 Azure AD Connect 中启用此功能：在 Azure AD Connect 安装向导的 "可选功能" 屏幕中启用**密码写回**，或通过 Windows PowerShell 启用它。 |   | 是 | 是 | 是 |
| [启用 Azure Active Directory 标识保护](https://docs.microsoft.com/azure/active-directory/identity-protection/enable)。 Azure AD Identity Protection 使您能够检测到影响组织的身份的潜在漏洞，并将自动修正策略配置为低、中和高的登录风险和用户风险。  | 是 | 是 | 是 | 是 |
| 为[Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662)和[Skype For business Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)**启用新式验证**。 新式验证是使用多重身份验证（MFA）的先决条件。 默认情况下，将为 Office 2016 客户端、SharePoint Online 和 OneDrive for business 启用新式验证。 | 是 | 是 | 是 | 是 |
||||||



## <a name="recommended-client-configurations"></a>推荐的客户端配置
本节介绍了我们建议的默认平台客户端配置，以向用户提供最佳的 SSO 体验，以及条件访问的技术先决条件。

### <a name="windows-devices"></a>Windows 设备
由于 Azure 旨在为本地和 Azure AD 提供尽可能流畅的 SSO 体验，因此建议使用 Windows 10（版本 1703 或更高版本）。 应将工作或学校签发的设备配置为直接加入 Azure AD，或者如果组织使用内部部署 AD 域加入，应将这些设备[配置为自动并以无提示方式注册到 AZURE ad](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。

对于 BYOD Windows 设备，用户可以使用 "**添加工作或学校帐户**"。 请注意，Windows 10 上的 Chrome browser 用户需要[安装扩展](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)，以获得与边缘/IE 用户相同的平滑登录体验。 此外，如果您的组织具有加入域的 Windows 7 设备，则可以为非 Windows 10 计算机安装 Microsoft Workplace Join。[下载该程序包以](https://www.microsoft.com/download/details.aspx?id=53554)使用 Azure AD 注册设备。

### <a name="ios-devices"></a>iOS 设备
建议在部署条件访问或 MFA 策略之前，在用户设备上安装 [Microsoft Authenticator 应用](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。 在要求用户通过添加工作或学校帐户向 Azure AD 注册设备时，或者在安装 Intune 公司门户应用程序以将其设备注册到管理中时，应至少安装应用程序。 具体取决于配置的条件访问策略。

### <a name="android-devices"></a>Android 设备
建议用户在部署条件访问策略之前，或在某些身份验证尝试期间需要时，安装 [Intune 公司门户应用](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en)和 [Microsoft Authenticator 应用](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。 安装应用后，系统可能会要求用户向 Azure AD 注册或向 Intune 注册设备。 具体取决于配置的条件访问策略。

此外，我们还建议在支持使用 Android for Work 或 Samsung Knox 的 Oem 和版本上对公司拥有的设备（货到）进行标准化，以允许通过 Intune MDM 策略管理和保护邮件帐户。


### <a name="recommended-email-clients"></a>推荐的电子邮件客户端
以下电子邮件客户端支持新式身份验证和条件访问。 

|平台|客户端|版本/说明|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016，2013[启用新式验证](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910)（[必需的更新](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)）|
|**iOS**|Outlook for iOS|[最新版本](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新版本](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|不支持||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>保护文档时推荐使用的客户端平台
如果应用了安全文档策略，则建议使用以下客户端。

|平台|Word/Excel/PowerPoint|OneNote|OneDrive 应用|SharePoint 应用|OneDrive 同步客户端|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|支持|支持|不适用|不适用|预览<sup>*</sup>|
|Windows 8.1|支持|支持|不适用|不适用|预览<sup>*</sup>|
|Windows 10|支持|支持|不适用|不适用|预览<sup>*</sup>|
|Windows Phone 10|不支持|不支持|不支持|不支持|不支持|
|Android|支持|支持|支持|支持|不适用|
|iOS|支持|支持|支持|支持|不适用|
|macOS|公共预览版|公共预览版|不适用|不适用|不支持|
|Linux|不支持|不支持|不支持|不支持|不支持|

<sup>*</sup>了解有关在[OneDrive 同步客户端](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)中使用条件访问的详细信息。

### <a name="office-365-client-support"></a>Office 365 客户端支持
有关 Office 365 客户端支持的详细信息，请参阅以下文章：
- [Office 365 客户端应用支持-条件访问](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365 客户端应用程序支持-移动应用程序管理](https://docs.microsoft.com/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365 客户端应用程序支持-新式验证](https://docs.microsoft.com/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>保护管理员帐户
Azure AD 为你提供一种简单的方法，以使用预配置的条件访问策略开始保护管理员访问。 在 Azure AD 中，转到 "**条件访问**并查找此策略-**基准策略：要求对管理员进行 MFA （预览）**"。 选择 "此策略"，然后选择 "**立即使用策略**"。 

此策略需要对以下角色进行 MFA：
- 全局管理员
- SharePoint 管理员
- Exchange 管理员
- 条件访问管理员
- 安全管理员

有关详细信息，请参阅[AZURE AD 管理员帐户的基准安全策略](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)。

其他建议包括以下内容：
- 使用 Azure AD Privileged Identity Management 减少永久管理帐户的数目。 请参阅[开始使用 PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started)。 
- [使用 Office 365 中的特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)来保护您的组织免受可能使用现有特权管理员帐户访问敏感数据或访问关键配置设置的用户泄露的行为。 
- 仅使用管理员帐户进行管理。 管理员应使用单独的用户帐户进行常规非管理，并且仅在必要时才使用其管理帐户完成与工作职能相关联的任务。 [Office 365 管理员](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)角色具有比 office 365 服务更多的权限。
- 遵循[本文](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)中所述的在 Azure AD 中保护特权帐户的最佳做法。

## <a name="next-steps"></a>后续步骤

[配置通用标识和设备访问策略](identity-access-policies.md)

