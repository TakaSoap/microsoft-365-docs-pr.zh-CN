---
title: 修复准备情况评估工具发现的问题
description: 对工具找到的每个问题执行的详细操作
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b77313a18a5744549e492de991e282bc34dbb6da
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002413"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>修复准备情况评估工具发现的问题

对于每个检查，该工具将报告以下四个可能的结果之一：


|结果  |含义  |
|---------|---------|
|Ready     | 完成注册前不需要执行任何操作。        |
|欲    | 按照工具或本文中的步骤操作，以获取注册和用户的最佳体验。 你 *可以* 完成注册，但必须先解决这些问题，然后再部署你的第一个设备。        |
|未就绪 | *如果不解决这些问题，注册将失败。* 按照工具或本文中的步骤进行操作，以解决这些问题。        |
|错误 | 您正在使用的 Azure Active Director (AD) 角色没有足够的权限来运行此检查。 |

## <a name="microsoft-intune-settings"></a>Microsoft Intune 设置

### <a name="autopilot-deployment-profile"></a>Autopilot 部署配置文件

您不应具有任何目标为分配的或 Microsoft 托管桌面使用的动态组的现有 Autopilot 配置文件。 Microsoft 托管桌面使用 Autopilot 配置新设备。

**未就绪**

您有一个分配给所有设备的 Autopilot 配置文件。 有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。 在 Microsoft 托管桌面注册之后，将您的 Autopilot 策略设置为排除 **新式工作区设备-所有** Azure AD 组。

**欲**

确保您的 Autopilot 配置文件面向不包含将在注册中创建的 Microsoft 托管桌面设备的已分配或动态 Azure AD 组。 有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。 在 Microsoft 托管桌面注册之后，将您的 Autopilot 策略设置为排除 **新式工作区设备-所有** Azure AD 组。


### <a name="certificate-connectors"></a>证书连接器

如果你有要在 Microsoft 托管桌面中注册的设备使用的任何证书连接器，连接器将不能包含任何错误。 以下建议仅适用于你的情况，因此请仔细检查。

**欲**

不存在任何证书连接器。 您可能不需要任何连接器，但应评估是否需要对 Microsoft 托管桌面设备进行网络连接。 有关详细信息，请参阅 [为 Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。

**欲**

至少一个证书连接器有错误。 如果需要此连接器连接到 Microsoft 托管桌面设备，则必须解决该错误。 有关详细信息，请参阅 [为 Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。


**欲**

您至少有一个证书连接器，并且未报告任何错误。 但是，您可能需要创建一个配置文件以重用 Microsoft 托管桌面设备的连接器。 有关详细信息，请参阅 [为 Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)。


### <a name="conditional-access-policies"></a>条件访问策略

Azure AD 组织中的条件访问策略不得以任何 Microsoft 管理桌面用户为目标。

**未就绪**

您至少具有一个面向所有用户的条件访问策略。 将策略重置为面向不包含将在注册时创建的 Microsoft 托管桌面服务帐户的 Azure AD 组的特定 Azure AD 组。 有关步骤，请参阅 [条件访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。

**欲**

请确保您已排除了所有条件访问 **策略 "AZURE** AD 组"。 有关步骤，请参阅 [调整条件访问](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)。 **新式 Workplace Service 帐户** Azure AD 组是我们在注册时为服务创建的动态组。 注册后，必须返回以排除此组。 有关这些服务帐户的详细信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**Error**

Intune 管理员角色对此检查没有足够的权限。 您还需要分配给运行此检查的任何 Azure AD 角色：

- 安全读取者
- 安全管理员
- 条件访问管理员
- 全局读取者
- 设备管理员


### <a name="device-compliance-policies"></a>设备合规性策略

Azure AD 组织中的 Intune 设备合规性策略不得以任何 Microsoft 托管桌面用户为目标。

**未就绪**

您至少具有一个面向所有用户的合规性策略。 将策略重置为面向不包含任何 Microsoft 托管桌面用户的特定 Azure AD 组。 有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。

**欲**

确保任何不包含任何 Microsoft 托管桌面用户的合规性策略。 有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。



### <a name="device-configuration-policies"></a>设备配置策略

Azure AD 组织中的 Intune 设备配置策略不得以任何 Microsoft 管理桌面设备或用户为目标。

**未就绪**

至少有一个针对所有用户、所有设备或同时针对这两者的配置策略。 将策略重置为面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组。 有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。

**欲**

确保任何不包含任何 Microsoft 托管桌面设备或用户的合规性策略。 有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。



### <a name="device-type-restrictions"></a>设备类型限制

必须允许 Microsoft 托管桌面设备在 Intune 中注册。

**未就绪**

按照 " [设置注册限制](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) " 中的步骤将设置更改为 " **允许** "。


### <a name="enrollment-status-page"></a>"注册状态" 页

您当前已启用 "注册状态" 页面 (ESP) 。 如果你参与此功能的公开预览，则可以忽略此项。 有关详细信息，请参阅 [首次运行体验 With Autopilot 和注册状态页](../get-started/esp-first-run.md)。

**未就绪**

您已将 ESP 默认配置文件设置为 **显示应用和配置文件配置进度** 。 通过执行 " [设置注册状态" 页](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)中的步骤，禁用此设置或确保对任何 Azure AD 组的分配不包括 Microsoft 托管桌面设备。

**欲**

确保具有 " **显示应用程序" 和 "配置文件配置进度** " 设置的任何配置文件未分配给任何包含 Microsoft 托管桌面设备的 Azure AD 组。 有关详细信息，请参阅 [设置注册状态页](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。

### <a name="intune-enrollment"></a>Intune 注册

Azure AD 组织中的 Windows 10 设备必须在 Intune 中自动注册。

**欲**

确保将 MDM 用户作用域设置为 " **部分** 或 **全部** "，而不是 " **无** "。 如果选择 " **某些** "，请在注册后返回，并选择 **新式工作区-** **组** 的所有 Azure AD 组。


### <a name="microsoft-store-for-business"></a>适用于企业的 Microsoft Store

我们使用 Microsoft Store for Business，以便您可以下载公司门户，以部署一些应用程序，如 Microsoft Project 和 Microsoft Visio。

**未就绪**

适用于企业的 Microsoft Store 不是已启用或未与 Intune 同步。 有关详细信息，请参阅 [如何使用 Microsoft Intune 在 Microsoft Store For Business 中管理批量购买的应用](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) ，并 [在设备上安装 Intune 公司门户](../get-started/company-portal.md)。

### <a name="multi-factor-authentication"></a>多重身份验证

多因素身份验证不能意外应用于 Microsoft 托管桌面服务帐户。


**未就绪**

您有一些多重身份验证 (MFA) 策略设置为分配给所有用户的条件访问策略的 "必需"。 将策略更改为使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。 有关详细信息，请参阅 [条件访问策略](#conditional-access-policies) 和 [条件访问：要求对所有用户进行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。

**欲**

请确保任何需要 MFA 的条件访问策略排除 **新式工作区-所有** Azure AD 组。 有关详细信息，请参阅 [条件访问策略](#conditional-access-policies) 和 [条件访问：要求对所有用户进行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。 **新式工作区-所有** Azure AD 组是在注册 Microsoft 托管桌面时创建的动态组，因此你必须在注册后返回以排除此组。

**Error**

Intune 管理员角色对此检查没有足够的权限。 您还需要分配给运行此检查的任何 Azure AD 角色：

- 安全读取者
- 安全管理员
- 条件访问管理员
- 全局读取者
- 设备管理员


### <a name="powershell-scripts"></a>PowerShell 脚本

无法以 Microsoft 托管桌面设备的目标方式分配 Windows PowerShell 脚本。  

**欲**

请确保 Azure AD 组织中的 Windows PowerShell 脚本不会针对任何 Microsoft 管理桌面设备或用户。 不要将 PowerShell 脚本分配给所有用户、所有设备，或同时针对两者。 将策略更改为使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。 有关详细信息，请参阅在 [Intune 中使用 Windows 10 设备上的 PowerShell 脚本](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)。

### <a name="region"></a>区域

Microsoft 托管桌面必须支持你的区域。

**未就绪**

Microsoft 托管桌面目前不支持 Azure AD 组织区域。 有关详细信息，请参阅 [Microsoft 托管桌面支持的区域和语言](../service-description/regions-languages.md)。

**欲**

Microsoft 托管桌面不支持 Azure AD 组织所在的一个或多个国家/地区。 有关详细信息，请参阅 [Microsoft 托管桌面支持的区域和语言](../service-description/regions-languages.md)。


### <a name="security-baselines"></a>安全基准

安全基准策略不应以任何 Microsoft 托管桌面设备为目标。

**未就绪**

您有一个面向所有用户、所有设备或两者的安全基准配置文件。 将策略更改为使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。 有关步骤，请参阅 [使用安全基准在 Intune 中配置 Windows 10 设备](https://docs.microsoft.com/mem/intune/protect/security-baselines)。

**欲**

请确保任何安全基准策略都已排除 Microsoft 托管桌面设备。 有关步骤，请参阅 [使用安全基准在 Intune 中配置 Windows 10 设备](https://docs.microsoft.com/mem/intune/protect/security-baselines)。 **新式工作区设备-所有** Azure AD 组是在注册 Microsoft 托管桌面时创建的动态组，因此你必须在注册后返回以排除此组。


### <a name="windows-apps"></a>Windows 应用

查看你希望 Microsoft 托管桌面用户拥有的应用。

**欲**

应准备您希望 Microsoft 托管桌面用户拥有的应用程序的清单。 由于这些应用程序必须由 Intune 部署，因此请评估 "重新使用现有 Intune 应用"。 请考虑使用公司门户 (请参阅在设备和注册状态页 [上安装 Intune 公司门户](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) (ESP) 将应用程序分发给用户。 有关详细信息，请参阅 [Microsoft 托管桌面中的应用程序](apps.md) 和 [首次运行体验中的 Autopilot 和注册状态页](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)。

可以在 Microsoft 终结点配置管理器中向 Microsoft 帐户代表查询，以确定那些准备迁移到 Intune 或需要调整的应用程序。


### <a name="windows-hello-for-business"></a>Windows Hello 企业版

Microsoft 托管桌面要求启用 Windows Hello 企业版。

**未就绪**

Windows Hello 企业版已禁用。 按照[创建 Windows Hello 企业版策略](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步骤启用它

**欲**

Windows Hello 企业版尚未设置。 按照 [创建 Windows Hello 企业版策略](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)中的步骤启用它。


### <a name="windows-10-update-rings"></a>Windows 10 更新环

Intune 中的 "Windows 10 更新循环" 策略不得以任何 Microsoft 托管桌面设备为目标。

**未就绪**

您有一个面向所有设备和/或所有用户的 "更新循环" 策略。 将策略更改为使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的工作分配。 有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。

**欲**

确保任何更新环策略都排除了 **新式工作区设备-所有** Azure AD 组。 如果已将 Azure AD 用户组分配给这些策略，请确保所有更新环策略也都已排除 **新式工作区-所有** 包含 Microsoft 托管桌面用户的 Azure AD 组。 有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。 新式的 **工作区设备-all** 和 **新式工作区-所有** Azure AD 组都分配了我们在注册 Microsoft 托管桌面时创建的组，因此在注册后必须返回以排除此组。


## <a name="azure-active-directory-settings"></a>Azure Active Directory 设置


### <a name="ad-hoc-subscriptions"></a>临时订阅

建议如何检查 (如果设置为 "false" 的设置 ) 可能会阻止企业状态漫游正常工作。

**欲**

确保将 **AllowAdHocSubscriptions** 设置为 **True** 。 否则，企业状态漫游可能无法工作。 有关详细信息，请参阅 [set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。


### <a name="enterprise-state-roaming"></a>企业状态漫游

应启用企业状态漫游。

**欲**

确保为 **所有** 或 **选定** 的组启用了企业状态漫游。 有关详细信息，请参阅 [在 Azure Active Directory 中启用企业状态漫游](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。

### <a name="licenses"></a>许可证

需要许多许可证才能使用 Microsoft 托管桌面。

**未准备就绪**

你没有使用 Microsoft 托管桌面所需的所有许可证。 有关详细信息，请参阅 [Microsoft 托管桌面技术](../intro/technologies.md) 和 [有关许可证的详细](prerequisites.md#more-about-licenses)信息。


### <a name="security-account-names"></a>安全帐户名称

某些安全帐户名称与 Microsoft 托管桌面创建的名称相冲突。

**未就绪**

至少有一个帐户名称与 Microsoft 托管桌面创建的帐户名称冲突。 与你的 Microsoft 帐户代表合作，以排除这些帐户名称。


### <a name="security-administrator-roles"></a>安全管理员角色

具有特定安全角色的用户必须在 Microsoft Defender for Endpoint 中分配这些角色。

**欲**

如果你已将用户分配到 Azure AD 组织中的任何角色，请确保他们还在 Microsoft Defender for Endpoint 中分配了这些角色。 否则，拥有这些角色的管理员将无法访问管理门户。

- 安全操作员
- 全局读取者

有关详细信息，请参阅 [创建和管理基于角色的访问控制的角色](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。


### <a name="security-default"></a>安全性默认

Azure Active Directory 中的安全性默认值将阻止 Microsoft 托管桌面管理设备。

**未就绪**

您启用了安全默认设置。 关闭安全默认设置并设置条件访问策略。 有关详细信息，请参阅 [常见条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。

### <a name="self-service-password-reset"></a>自助服务密码重置

自助服务密码重置 (应为所有不包括 Microsoft 托管桌面服务帐户的 Microsoft 托管桌面用户启用 SSPR) 。 有关详细信息，请参阅 [教程：使用户能够解锁其帐户或使用 Azure Active Directory 自助服务密码重置重置密码](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。

**欲**

请确保 SSPR **选择** 的设置包括 Microsoft 托管桌面设备，但不包括 Microsoft 托管桌面服务帐户。 启用 SSPR 后，Microsoft 托管桌面服务帐户无法按预期工作。  


### <a name="standard-user-role"></a>标准用户角色

除了分配有全局管理员和设备管理员的 Azure AD 角色的用户之外，Microsoft 托管桌面用户将是没有本地管理员权限的标准用户。 在启动 Microsoft 托管桌面设备时，将为所有其他用户分配一个标准用户角色。

**欲**

Microsoft 托管桌面用户在注册后将不具有对其 Microsoft 托管桌面设备的本地管理员权限。

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 企业应用版

### <a name="onedrive"></a>OneDrive

" **仅允许在加入特定域的电脑上进行同步** " 设置将与 Microsoft 托管桌面发生冲突。

**欲**

您正在使用 " **仅允许在加入特定域的 pc 上同步** " 设置。 此设置不适用于 Microsoft 托管桌面。 禁用此设置，而将 OneDrive 设置为使用条件访问策略。 请参阅 [规划条件访问部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 以获取帮助。

