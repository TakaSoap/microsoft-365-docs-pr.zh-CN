---
title: 修复准备情况评估工具发现的问题
description: 针对工具找到的每个问题要采取的详细操作
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 5a22996ce9e39dc16191ddddc6aa9393de557bbc
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579406"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>修复准备情况评估工具发现的问题

对于每个检查，该工具将报告四个可能的结果之一：


|结果  |含义  |
|---------|---------|
|Ready     | 完成注册前无需任何操作。        |
|公告    | 按照工具或本文中的步骤操作，获得注册和用户的最佳体验。 *你可以完成* 注册，但在部署第一台设备之前必须修复这些问题。        |
|未就绪 | *如果不修复这些问题，注册将失败。* 请按照工具或本文中的步骤进行解析。        |
|错误 | 你 (Azure Active Directory) AD 角色没有足够的权限运行此检查。 |

> [!NOTE]
> 此工具报告的结果仅反映设置在运行它的特定时间点的状态。 如果稍后对 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的策略进行了任何更改，则"就绪"的项目可能会变为"未就绪"。 若要避免 Microsoft 托管桌面操作出现问题，请在更改任何策略之前检查本文中描述的特定设置。

## <a name="microsoft-intune-settings"></a>Microsoft Intune 设置

可以在 Microsoft Endpoint Manager 管理中心访问 Intune [设置](https://endpoint.microsoft.com)。

### <a name="autopilot-deployment-profile"></a>Autopilot 部署配置文件

不应有任何面向已分配或动态组（使用 Microsoft 托管桌面设备）的现有 Autopilot 配置文件。 Microsoft 托管桌面使用 Autopilot 预配新设备。

**未就绪**

你拥有分配给所有设备的 Autopilot 配置文件。 有关步骤，请参阅 [使用 Windows Autopilot 在 Intune](/mem/autopilot/enrollment-autopilot)中注册 Windows 设备。 注册 Microsoft 托管桌面后，设置 Autopilot 策略以排除 **现代工作区设备 -所有** Azure AD 组。

**公告**

确保 Autopilot 配置文件面向不包括 Microsoft 托管桌面设备的已分配或动态 Azure AD 组。 有关步骤，请参阅 [使用 Windows Autopilot 在 Intune](/mem/autopilot/enrollment-autopilot)中注册 Windows 设备。 注册 Microsoft 托管桌面后，设置 Autopilot 配置文件以排除 **现代工作区设备 -所有** Azure AD 组。


### <a name="certificate-connectors"></a>证书连接器

如果你有任何证书连接器将由你想要在 Microsoft 托管桌面中注册的设备使用，则连接器不应有任何错误。 只有以下公告之一适用于你的情况，因此请仔细检查它们。

**公告**

不存在证书连接器。 可能不需要任何连接器，但应评估是否需要一些连接器来建立 Microsoft 托管桌面设备的网络连接。 有关详细信息，请参阅准备 [Microsoft 托管桌面的证书和网络配置文件](certs-wifi-lan.md)。

**公告**

至少有一个证书连接器出现错误。 如果需要此连接器向 Microsoft 托管桌面设备提供证书，则必须解决此错误。 有关详细信息，请参阅准备 [Microsoft 托管桌面的证书和网络配置文件](certs-wifi-lan.md)。


**公告**

您至少有一个证书连接器，并且未报告任何错误。 但是，在准备部署时，可能需要创建配置文件以重用 Microsoft 托管桌面设备的连接器。 有关详细信息，请参阅准备 [Microsoft 托管桌面的证书和网络配置文件](certs-wifi-lan.md)。


### <a name="conditional-access-policies"></a>条件访问策略

条件访问策略不得阻止 Microsoft 托管桌面在 Intune 和 Azure AD (租户) 管理 Azure AD 组织。

**未就绪**

您至少有一个面向所有用户的条件访问策略。 注册期间，我们会将 Microsoft 托管桌面服务帐户从相关条件访问策略中排除，并应用新的条件访问策略来限制对这些帐户的访问。 注册后，可以在 Microsoft Endpoint Manager 中查看 Microsoft 托管桌面条件访问策略。 有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**公告**

您具有可能会阻止 Microsoft 托管桌面管理 Microsoft 托管桌面服务的条件访问策略。 注册期间，我们会将 Microsoft 托管桌面服务帐户从相关条件访问策略中排除，并应用新的条件访问策略来限制对这些帐户的访问。 有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**错误**

Intune 管理员角色没有足够的权限进行此检查。 还需要分配以下任一 Azure AD 角色来运行此检查：

- 安全读取者
- 安全管理员
- 条件访问管理员
- 全局读取者
- 设备管理员


### <a name="device-compliance-policies"></a>设备合规性策略

Azure AD 组织中 Intune 设备合规性策略可能会影响 Microsoft 托管桌面设备。

**未就绪**

您至少有一个面向所有用户的合规性策略。 Microsoft 托管桌面包括面向 Microsoft 托管桌面设备的合规性策略。  将策略更改为面向不包含任何 Microsoft 托管桌面用户或设备的特定 Azure AD 组。 有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](/mem/intune/protect/create-compliance-policy)。

**公告**

确保你拥有的任何合规性策略不面向任何 Microsoft 托管桌面用户。 有关步骤，请参阅 [在 Microsoft Intune 中创建合规性策略](/mem/intune/protect/create-compliance-policy)。



### <a name="device-configuration-profiles"></a>设备配置文件

Azure AD 组织中 Intune 设备配置文件不得面向任何 Microsoft 管理桌面设备或用户。

**未就绪**

你至少具有一个面向所有用户和/或所有设备的配置文件。 重置配置文件以面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组。 有关步骤，请参阅 [使用 Microsoft Intune 中的自定义设置创建配置文件](/mem/intune/configuration/custom-settings-configure)。

**公告**

确保你拥有的任何配置策略不包括任何 Microsoft 托管桌面设备或用户。 有关步骤，请参阅 [使用 Microsoft Intune 中的自定义设置创建配置文件](/mem/intune/configuration/custom-settings-configure)。



### <a name="device-type-restrictions"></a>设备类型限制

必须允许 Microsoft 托管桌面设备在 Intune 中注册。

**未就绪**

你当前至少配置了一个注册限制策略，以防止 Windows 设备在 Intune 中注册。 按照针对 Microsoft 托管桌面 [用户](/mem/intune/enrollment/enrollment-restrictions-set) 的每个注册限制策略设置注册限制中的步骤操作，将 **Windows (MDM)** 设置为 **允许**。 但是，你可以将个人拥有的任何 **Windows (MDM)** 设置为 **阻止**。 


### <a name="enrollment-status-page"></a>注册状态页

YOU currently have the Enrollment Status Page (ESP) enabled. 如果你打算参与此功能的 Microsoft 托管桌面公共预览版，可以忽略此项。 有关详细信息，请参阅 [Autopilot 首次运行体验和注册状态页面](../get-started/esp-first-run.md)。

**未就绪**

将 ESP 默认配置文件设置为"**显示应用和配置文件配置进度"。** 通过按照设置注册状态页 中的步骤操作，禁用此设置或确保任何 Azure AD 组的工作分配不包括 Microsoft 托管 [桌面设备](/mem/intune/enrollment/windows-enrollment-status)。

**公告**

确保未将具有"显示应用和配置文件配置进度"设置的任何配置文件分配给任何包含 Microsoft 托管桌面设备的 Azure AD 组。 有关详细信息，请参阅设置 [注册状态页](/mem/intune/enrollment/windows-enrollment-status)。

### <a name="microsoft-store-for-business"></a>适用于企业的 Microsoft Store

我们使用适用于 Business 的 Microsoft Store，在 Microsoft 托管桌面上部署公司门户应用，以允许用户选择安装某些应用，如 Microsoft Project 和 Microsoft Visio (（如果允许) ）。

**未就绪**

适用于 Business 的 Microsoft Store 未启用或未与 Intune 同步。 有关详细信息，请参阅如何使用 [Microsoft Intune](/mem/intune/apps/windows-store-for-business) 管理从适用于企业 Microsoft Store 购买的批量应用和在设备上安装 [Intune 公司门户](../get-started/company-portal.md)。

### <a name="multifactor-authentication"></a>多重身份验证

多重身份验证不得阻止 Microsoft 托管桌面在 Intune 和 Azure AD (托管) 管理 Azure AD 组织。


**未就绪**

您具有为分配给所有用户的条件 **访问策略所需的** 一些多重身份验证策略。 注册期间，我们会将 Microsoft 托管桌面服务帐户从相关条件访问策略中排除，并应用新的条件访问策略来限制对这些帐户的访问。 有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**公告**

对于可能阻止 Microsoft 托管桌面管理 Microsoft 托管桌面服务的条件访问策略，您需要进行多重身份验证。 注册期间，我们会将 Microsoft 托管桌面服务帐户从相关条件访问策略中排除，并应用新的条件访问策略来限制对这些帐户的访问。 有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**错误**

Intune 管理员角色没有足够的权限进行此检查。 还需要分配以下任一 Azure AD 角色来运行此检查：

- 安全读取者
- 安全管理员
- 条件访问管理员
- 全局读取者
- 设备管理员


### <a name="powershell-scripts"></a>PowerShell 脚本

Windows PowerShell脚本无法以面向 Microsoft 托管桌面设备的方式分配。  

**公告**

请确保 Azure AD Windows PowerShell中的脚本不面向任何 Microsoft 管理桌面设备或用户。 不要将 PowerShell 脚本分配给所有用户、所有设备或两者。 更改策略以使用面向不包括任何 Microsoft 托管桌面设备或用户的特定 Azure AD 组的分配。 有关详细信息，请参阅在 [Intune 中的 Windows 10 设备上使用 PowerShell 脚本](/mem/intune/apps/intune-management-extension)。

### <a name="region"></a>地区

你的区域必须受 Microsoft 托管桌面支持。

**未就绪**

你的 Azure AD 组织区域当前不受 Microsoft 托管桌面支持。 有关详细信息，请参阅 [Microsoft 托管桌面支持的地区和语言](../service-description/regions-languages.md)。

**公告**

Microsoft 托管桌面不支持 Azure AD 组织所在的一个或多个国家/地区。 有关详细信息，请参阅 [Microsoft 托管桌面支持的地区和语言](../service-description/regions-languages.md)。


### <a name="security-baselines"></a>安全基线

安全基线策略不应面向任何 Microsoft 托管桌面设备。

**未就绪**

你有一个面向所有用户、所有设备或两者的安全基线配置文件。 更改策略以使用面向不包含任何 Microsoft 托管桌面设备的特定 Azure AD 组的分配。 有关步骤，请参阅 [使用安全基线在 Intune](/mem/intune/protect/security-baselines)中配置 Windows 10 设备。 注册期间，我们会将新的安全基线应用于所有 Microsoft 托管桌面设备。 注册后，可以在 Microsoft Endpoint Manager 的配置策略区域中查看Microsoft 托管桌面安全基线策略。

**公告**

确保已排除 Microsoft 托管桌面设备的任何安全基线策略。 有关步骤，请参阅 [使用安全基线在 Intune](/mem/intune/protect/security-baselines)中配置 Windows 10 设备。 注册期间，我们会将新的安全基线应用于所有 Microsoft 托管桌面设备。 现代 **工作区设备 - 所有** Azure AD 组是注册 Microsoft 托管桌面时创建的动态组，因此你必须在注册后返回以排除此组。 


### <a name="windows-apps"></a>Windows 应用

查看希望 Microsoft 托管桌面用户拥有的应用。

**公告**

应准备希望 Microsoft 托管桌面用户拥有的应用清单。 由于这些应用必须由 Intune 部署，因此请评估是否重新使用现有 Intune 应用。 请考虑使用公司门户 (在设备上安装 [Intune 公司](../get-started/company-portal.md) 门户和注册状态页 (ESP) 将应用分发到用户。 有关详细信息，请参阅 [Microsoft 托管桌面](apps.md) 中的应用和 Autopilot 的首次运行体验和 [注册状态页面](../get-started/esp-first-run.md)。

你可以要求 Microsoft 帐户代表在 Microsoft Endpoint Configuration Manager 中查询，以确定准备迁移到 Intune 或需要调整的应用。


### <a name="windows-hello-for-business"></a>Windows Hello 企业版

Microsoft 托管桌面需要启用 Windows Hello 企业版。

**未就绪**

Windows Hello 企业应用已禁用。 按照创建 Windows Hello 企业策略 [中的步骤启用它](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**公告**

未设置 Windows Hello 企业版本。 按照创建 Windows Hello 企业策略 [中的步骤启用它](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。


### <a name="windows-10-update-rings"></a>Windows 10 更新圈

Intune 中的"Windows 10 更新圈"策略不得面向任何 Microsoft 托管桌面设备。

**未就绪**

你有一个面向所有设备、所有用户或两者同时面向的"更新圈"策略。 将策略更改为使用面向不包括任何 Microsoft 托管桌面设备的特定 Azure AD 组的分配。 有关步骤，请参阅在 Intune 中管理 [Windows 10 软件更新](/mem/intune/protect/windows-update-for-business-configure)。

**公告**

确保你拥有的任何更新圈策略不包括现代 **工作区设备 -所有** Azure AD 组。 如果你已向这些策略分配了 Azure AD 用户组，请确保你已排除所有更新圈策略，并且你已排除将 Microsoft 托管桌面用户添加到 (或等效组) 的新式工作区 **-** 所有 Azure AD 组。 有关步骤，请参阅在 Intune 中管理 [Windows 10 软件更新](/mem/intune/protect/windows-update-for-business-configure)。 现代 **工作区设备 -全部** 和现代工作区 **-所有** Azure AD 组都是我们在注册 Microsoft 托管桌面时创建的组，因此你必须在注册后返回以排除此组。


## <a name="azure-active-directory-settings"></a>Azure Active Directory 设置

可以在 Azure 门户访问 Azure Active Directory [设置](https://portal.azure.com)。

### <a name="intune-enrollment"></a>Intune 注册

Azure AD 组织的 Windows 10 设备必须能够在 Intune 中自动注册。

**公告**

确保 MDM **用户作用域设置为**"部分"**或"****全部"，** 而不是"**无"。** 如果选择"**一些**"，请在注册后返回，然后为组选择"新式 **工作区 -** 所有Azure AD"组，或选择面向所有 Microsoft 托管桌面用户的等效组。  请参阅 [使用 Microsoft Intune 设置 Windows 设备的注册](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。


### <a name="ad-hoc-subscriptions"></a>临时订阅

建议如何检查设置，如果 (设置为"false"，) 可能会阻止企业状态漫游正常工作。

**公告**

确保 **AllowAdHocSubscriptions** 设置为 **True**。 否则，企业状态漫游可能无法工作。 有关详细信息，请参阅 [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。


### <a name="enterprise-state-roaming"></a>企业状态漫游

应启用企业状态漫游。

**公告**

确保为"全部"或" **所选组"** 启用企业状态 **漫游** 。 有关详细信息，请参阅在 [Azure Active Directory 中启用企业状态漫游](/azure/active-directory/devices/enterprise-state-roaming-enable)。

### <a name="licenses"></a>许可证

使用 Microsoft 托管桌面需要大量许可证。

**未就绪**

你没有使用 Microsoft 托管桌面所需的全部许可证。 有关详细信息，请参阅[Microsoft 托管桌面技术和](../intro/technologies.md)[有关许可证的更多内容](prerequisites.md#more-about-licenses)。


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft 托管桌面服务帐户

某些帐户名可能会与 Microsoft 托管桌面创建用于管理 Microsoft 托管桌面服务的帐户名称冲突。

**未就绪**

您至少有一个与 Microsoft 托管桌面创建的帐户名称相冲突的帐户名称。 与 Microsoft 帐户代表合作，排除这些帐户名。 我们不会公开列出帐户名称，以最大限度地降低安全风险。 


### <a name="security-administrator-roles"></a>安全管理员角色

具有特定安全角色的用户必须在 Microsoft Defender for Endpoint 中分配这些角色。

**公告**

如果你的用户已分配到 Azure AD 组织中任何这些角色，请确保他们在 Microsoft Defender for Endpoint 中也分配了这些角色。 否则，具有这些角色的管理员将无法访问管理门户。

- 安全操作员
- 全局读取者

有关详细信息，请参阅为基于角色 [的访问控制创建和管理角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。


### <a name="security-default"></a>安全默认值

Azure Active Directory 中的安全默认值将阻止 Microsoft 托管桌面管理设备。

**未就绪**

你已打开"安全性默认值"。 关闭安全默认值并设置条件访问策略。 有关详细信息，请参阅 Common [Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。

### <a name="self-service-password-reset"></a>自助服务密码重置

SSPR (SSPR) 可以启用所有 Microsoft 托管桌面用户（不包括 Microsoft 托管桌面服务帐户）。 有关详细信息，请参阅教程： [允许用户使用 Azure Active Directory](/azure/active-directory/authentication/tutorial-enable-sspr)自助服务密码重置解锁其帐户或重置密码。

**公告**

确保"SSPR **选择** "设置包括 Microsoft 托管桌面用户，但不包括 Microsoft 托管桌面服务帐户。 启用 SSPR 后，Microsoft 托管桌面服务帐户无法正常工作。  


### <a name="standard-user-role"></a>标准用户角色

除了分配了全局管理员和设备管理员的 Azure AD 角色的用户外，Microsoft 托管桌面用户将是没有本地管理员权限的标准用户。 当所有其他用户启动其 Microsoft 托管桌面设备时，将为其分配标准用户角色。

**公告**

注册后，Microsoft 托管桌面用户将没有 Microsoft 托管桌面设备的本地管理员权限。

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 企业应用版

### <a name="onedrive"></a>OneDrive

" **仅允许在加入特定域** 的 PC 上同步"设置将与 Microsoft 托管桌面冲突。 可以在 OneDrive 管理中心访问 OneDrive [设置](https://admin.onedrive.com)。

**公告**

你正在使用" **仅允许在加入特定域的 PC 上同步"** 设置。 此设置将不能用于 Microsoft 托管桌面。 禁用此设置，改为将 OneDrive 设置为使用条件访问策略。 请参阅 [规划条件访问部署](/azure/active-directory/conditional-access/plan-conditional-access) 获取帮助。