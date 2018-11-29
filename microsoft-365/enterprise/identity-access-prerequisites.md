---
title: 用于实现标识和设备的系统必备工作访问策略-Microsoft 365 企业版 |Microsoft 文档
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
ms.openlocfilehash: e97b16b3520d500737e0b397e8e2a515ecac9b3f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866054"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>必备工时实现标识和设备访问策略

本文介绍必备组件所需实现之前可以部署的建议的标识和设备访问策略。本文还讨论了我们建议您的用户，以及条件访问技术先决条件提供最佳的 SSO 体验的默认平台客户端配置。


## <a name="prerequisites"></a>先决条件

在实施之前的建议的标识和设备访问策略，有几个您的组织必须满足的先决条件。请参阅适用于您环境的先决条件的以下表。 


| 配置 | 仅云 | 使用密码哈希同步的 active Directory |  使用 AD FS 联合身份验证 |
| :------------- | :-----------: | :--------------: | :------------: |
|  [配置密码哈希同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)。必须启用此来检测泄漏的凭据和操作这些风险的基于条件的访问。**注意：** 这是必需的无论您的组织是否使用托管身份验证，如传递身份验证 (PTA) 或联合身份验证。 |    | 是 | 是 |
| [无缝单一登录启用](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso)该选项将自动登录时位于其公司设备连接到企业网络中的用户。 |  | 是 |  |
| [配置名为网络](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。Azure AD 身份保护收集和分析要生成的风险分数的所有可用的会话数据。我们建议贵组织的公共 IP 地址范围为您的网络指定名为网络配置 Azure AD 中。来自这些范围的通信提供的降低的风险分数，以便从公司环境外部通信视为高风险分数。 | 是  | 是 | 是 |
|[注册的自助服务密码重置 (SSPR) 和多因素身份验证 (MFA) 的所有用户](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)。我们建议为 Azure MFA 用户注册提早制定。Azure AD 身份保护将使用的 Azure MFA 执行额外的安全验证。此外，获得最佳登录体验，我们建议用户安装[Microsoft Authenticator 应用程序](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to)并在其设备上的 Microsoft 公司门户应用程序。可以从每个平台的 app store 安装这些。 | 是 | 是 | 是 |
| [启用已加入域的 Windows 计算机的自动注册](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。 条件访问可确保连接到服务的设备已加入域或是兼容设备。 要在 Windows 计算机上支持此操作，必须已向 Azure AD 注册设备。  本文介绍了如何配置自动设备注册。 |   | 是 |  是 |
| **准备支持团队**。 为无法完成 MFA 的用户制定计划。 例如，将他们添加到策略排除组，或为它们注册新 MFA 信息。 在对上述任何安全敏感问题作出更改之前，请先确保实际用户正在发出请求。 请求用户的管理人员来帮助审批是一个有效的步骤。 | 是 | 是 | 是 |
| [配置密码写回到本地 AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。 当检测到高风险的帐户泄漏时，密码写回允许 Azure AD 要求用户更改其本地密码。 可使用 Azure AD Connect 通过以下两种方法之一来启用此功能。 可以在 Azure AD Connect 设置向导的可选功能屏幕中启用密码写回，也可以通过 Windows PowerShell 启用。 |   | 是 | 是 |
| [启用 Azure Active Directory 标识保护](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable)。Azure AD 身份保护可以检测潜在安全漏洞影响组织的标识和配置自动的修正策略到低、 中型和高登录助手风险和用户风险。  | 是 | 是 | 是 |
| **启用现代身份验证**的[Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662)和[Skype 业务 online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。现代身份验证是使用多因素身份验证 (MFA) 的先决条件。Office 2016 客户端、 SharePoint Online 和 OneDrive for Business 的情况下，默认情况下启用现代身份验证。 | 是 | 是 | 是 |
|||||



## <a name="recommended-client-configurations"></a>推荐的客户端配置
本部分介绍了我们为了向用户提供最佳 SSO 体验而推荐的默认平台客户端配置，以及条件访问的技术先决条件。

### <a name="windows-devices"></a>Windows 设备
由于 Azure 旨在为本地和 Azure AD 提供尽可能流畅的 SSO 体验，因此建议使用 Windows 10（版本 1703 或更高版本）。 应将工作或学校设备配置为直接加入 Azure AD，或者当组织使用本地 AD 域加入时，这些设备应[配置为自动以无提示方式注册到 Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。

对于 BYOD Windows 设备，用户可以使用“添加工作或学校帐户”。 请注意，Windows 10 上的 Chrome 浏览器用户需要[安装扩展](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)，以便获得与 Microsoft Edge/IE 相同的流畅登录体验。 此外，如果组织的 Windows 7 设备已加入域，可以安装非 Windows 10 计算机的 Microsoft Workplace Join 包以[向 Azure AD 注册设备](https://www.microsoft.com/download/details.aspx?id=53554)。

### <a name="ios-devices"></a>iOS 设备
我们建议部署条件访问或 MFA 策略之前在用户设备上安装[Microsoft Authenticator 应用程序](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。至少，当询问用户以通过添加工作与 Azure AD 中注册其设备或学校帐户或安装 Intune 的公司门户应用程序注册到管理其设备时，应在安装应用程序。这取决于在配置条件的访问策略。

### <a name="android-devices"></a>Android 设备
建议用户在部署条件访问策略之前，或在某些身份验证尝试期间需要时，安装 [Intune 公司门户应用](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en
)和 [Microsoft Authenticator 应用](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。 安装应用后，系统可能会要求用户向 Azure AD 注册或向 Intune 注册设备。 具体取决于配置的条件访问策略。

我们还建议企业拥有的设备 (COD) 使用支持 Android for Work 或 Samsung Knox 的标准化 OEM 和版本，以便通过 Intune MDM 策略管理和保护电子邮件帐户。


### <a name="recommended-email-clients"></a>推荐的电子邮件客户端
下面的电子邮件客户端支持现代身份验证和条件的访问。 

|平台|客户端|版本/说明|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016、2013 [启用新式身份验证](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910)，[所需更新](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook iOS|[最新版本](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新版本](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|不支持||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>保护文档时推荐使用的客户端平台
应用安全文档策略时，建议使用以下客户端。

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

<sup>*</sup>了解有关使用[OneDrive 同步客户端](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)的条件的访问。

### <a name="office-365-client-support"></a>Office 365 客户端支持
有关 Office 365 客户端支持的详细信息，请参阅以下文章：
- [Office 365 客户端应用程序支持的条件的访问](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365 客户端应用程序支持的移动应用程序管理](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365 客户端应用程序支持的现代身份验证](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>保护管理员帐户
Azure Active Directory 提供了一种简单方式，用于开始保护预配置的条件访问策略的管理员访问权限。Azure AD 中转到条件访问刀片并查找此策略 —**基准策略： 对于管理员需要 MFA**。单击此策略，并选择**立即使用策略**。 

此策略要求 MFA 对以下角色：
- 全局管理员
- SharePoint 管理员
- Exchange 管理员
- 管理人员的条件的访问
- 安全管理员

有关详细信息，请参阅[Azure AD 管理员帐户的基准安全策略](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/)。

其他建议如下：
- 使用 Azure AD 特权标识管理减少持久的管理帐户数。请参阅[开始使用 PIM](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started)。 
- [使用 Office 365 中的访问权限的管理](https://docs.microsoft.com/en-us/office365/securitycompliance/privileged-access-management-overview)保护您的组织可以使用现有的破坏特权位置访问敏感数据或关键的配置设置的访问权限的管理员帐户。 
- Office 365 管理员帐户仅用于管理。管理员应具有单独的用户帐户用于常规非管理并仅使用其管理帐户时需要完成其作业函数与关联的任务。[Office 365 管理员](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)角色具有到 Office 365 服务的更多权限。
- 遵循用于保护特权的帐户在 Azure AD 中，此[文章](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)中所述的最佳做法。

## <a name="next-steps"></a>后续步骤

[配置公用标识和设备访问策略](identity-access-policies.md)

