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
ms.openlocfilehash: ee517e774e0606c62efdc67d869ad0aca5a41640
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866054"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>必备工时实现标识和设备访问策略

本文介绍建议的标识和设备访问策略可以部署之前必须实现的先决条件。本文还讨论了我们建议您的用户，以及用于条件访问技术先决条件提供最佳的 SSO 体验的默认平台客户端配置。


## <a name="prerequisites"></a>先决条件

在实施之前的建议的标识和设备访问策略，有几个您的组织必须满足的先决条件。下表详细介绍适用于您环境的先决条件。 


| 配置 | 仅云 | 使用密码哈希同步的 active Directory |  传递身份验证 |  使用 AD FS 联合身份验证 |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [配置密码哈希同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)。这必须启用来检测泄漏的凭据和风险基于条件访问这些操作。**注意：** 这是必需无论您的组织是否使用托管身份验证，如传递身份验证 (PTA) 或联合身份验证。 |    | 是 | 是 | 是 |
| [启用无缝的单一登录](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso)进行自动签名时位于其公司设备连接到企业网络中的用户。 |  | 是 | 是 |  |
| [配置名为网络](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal)。Azure AD 身份保护收集和分析要生成的风险分数的所有可用的会话数据。我们建议贵组织的公共 IP 地址范围为您的网络指定名为网络配置 Azure AD 中。来自这些范围的通信给定的降低的风险分数，并从公司环境外部通信得分较高风险。 | 是  | 是 | 是 | 是 |
|[注册的自助服务密码重置 (SSPR) 和多因素身份验证 (MFA) 的所有用户](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged)。我们建议为 Azure MFA 用户注册提早制定。Azure AD 身份保护将使用的 Azure MFA 执行额外的安全验证。此外，获得最佳登录体验，我们建议用户安装[Microsoft Authenticator 应用程序](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to)并在其设备上的 Microsoft 公司门户应用程序。可以从每个平台的 app store 安装这些。 | 是 | 是 | 是 | 是 |
| [启用的加入域的 Windows 计算机的设备自动注册](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。条件访问将确保设备连接到应用程序都加入域的或法规要求。若要在 Windows 的计算机上支持此功能，必须使用 Azure AD 注册设备。 本文讨论如何配置设备自动注册。 |   | 是 |  是 |  是 |
| **准备您的支持团队**。具有现成的无法完成 MFA 用户计划。这可以将其添加到策略排除组，或注册为它们的新 MFA 信息。在之前这些安全敏感更改之一，您需要确保的实际用户发出请求。需要用户的经理，以帮助实现审批是一个有效的步骤。 | 是 | 是 | 是 | 是 |  
| [配置密码回写到本地 AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)。密码写回允许 Azure AD 若要要求用户更改本地密码，当检测到高风险帐户危及安全时。您可以启用此功能使用 Azure AD 连接中两种方式之一： 在可选功能屏幕中的 Azure AD 连接安装向导中，启用**密码写回**或通过 Windows PowerShell 启用它。 |   | 是 | 是 | 是 |
| [启用 Azure Active Directory 标识保护](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/enable)。Azure AD 身份保护可用于检测潜在安全漏洞影响组织的标识和配置自动的修正策略低、 中型和高登录助手风险和用户风险。  | 是 | 是 | 是 | 是 |
| **启用现代身份验证**的[Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662)和[Skype 业务 online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。现代身份验证是使用多因素身份验证 (MFA) 的先决条件。Office 2016 客户端、 SharePoint Online 和 OneDrive for Business 的情况下，默认情况下启用现代身份验证。 | 是 | 是 | 是 | 是 |
||||||



## <a name="recommended-client-configurations"></a>推荐的客户端配置
本节介绍建议为您的用户，以及用于条件访问技术先决条件提供最佳的 SSO 体验的默认平台客户端配置。

### <a name="windows-devices"></a>Windows 设备
我们建议 Windows 10 （1703年或更高版本），如 Azure 旨在提供平滑 SSO 体验可能为内部部署和 Azure AD。工作或学校颁发设备应以直接加入 Azure AD 的情况下配置，或者如果组织使用内部部署 AD 域加入，这些设备应[配置为自动，并以无提示方式注册到 Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)。

对于 BYOD Windows 设备，用户可以使用**添加工作或学校帐户**。请注意，在 Windows 10 Chrome 浏览器用户需要[安装扩展](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog)到获取相同顺利登录的体验边缘/IE 用户。此外，如果您的组织已加入域的 Windows 7 设备，可以安装 Microsoft 工作场所加入 Windows 10 计算机[下载程序包注册](https://www.microsoft.com/download/details.aspx?id=53554)设备与 Azure AD。

### <a name="ios-devices"></a>iOS 设备
我们建议部署条件访问或 MFA 策略之前在用户设备上安装[Microsoft Authenticator 应用程序](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。至少，当用户将要求其设备注册 Azure AD 通过添加工作或学校帐户，或安装 Intune 的公司门户应用程序注册到管理其设备时，应在安装应用程序。这取决于在配置条件的访问策略。

### <a name="android-devices"></a>Android 设备
建议用户在部署条件访问策略之前，或在某些身份验证尝试期间需要时，安装 [Intune 公司门户应用](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en)和 [Microsoft Authenticator 应用](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。 安装应用后，系统可能会要求用户向 Azure AD 注册或向 Intune 注册设备。 具体取决于配置的条件访问策略。

我们还建议企业拥有设备 (COD) 进行了标准化 Oem 和支持的工作或三星 Knox 允许邮件帐户、 管理和保护 Intune MDM 策略的 Android 版本上。


### <a name="recommended-email-clients"></a>推荐的电子邮件客户端
下面的电子邮件客户端支持现代身份验证和条件的访问。 

|平台|客户端|版本/说明|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016、 2013年[启用现代身份验证](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910)、[所需更新](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook iOS|[最新版本](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook for Android|[最新版本](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016 年|
|**Linux**|不支持||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>保护文档时推荐使用的客户端平台
在已应用的安全文档策略时，建议使用以下客户端。

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

<sup>*</sup>了解有关使用条件访问[OneDrive 同步客户端](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e)的详细信息。

### <a name="office-365-client-support"></a>Office 365 客户端支持
有关 Office 365 客户端支持的详细信息，请参阅以下文章：
- [Office 365 客户端应用程序支持的条件的访问](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-conditional-access)
- [Office 365 客户端应用程序支持的移动应用程序管理](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-mobile-application-management)
- [Office 365 客户端应用程序支持的现代身份验证](https://docs.microsoft.com/en-us/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>保护管理员帐户
Azure AD 提供了一种简单方式，用于开始保护预配置的条件访问策略的管理员访问权限。在 Azure AD，转到**条件的访问**，查找此策略 —**基准策略： 对于管理员需要 MFA**。选择此策略，然后选择**立即使用策略**。 

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
- Office 365 管理员帐户仅用于管理。管理员应具有单独的用户帐户用于常规非管理并仅使用其管理帐户时需要完成其作业函数与关联的任务。[Office 365 管理员](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)角色具有比 Office 365 服务的更多权限。
- 遵循用于保护特权的帐户在 Azure AD 中，此[文章](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)中所述的最佳做法。

## <a name="next-steps"></a>后续步骤

[配置公用标识和设备访问策略](identity-access-policies.md)

