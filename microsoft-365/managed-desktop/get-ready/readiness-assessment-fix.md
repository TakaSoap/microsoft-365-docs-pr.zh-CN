---
title: 修复准备情况评估工具发现的问题
description: 针对工具找到的每个问题要采取的详细操作
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d2e055b553e3358107283236d634d9d46d33de4d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163152"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>修复准备情况评估工具发现的问题

对于每个检查，该工具将报告四个可能的结果之一：


|结果  |含义  |
|---------|---------|
|Ready     | 完成注册前无需任何操作。        |
|公告    | 按照工具或本文中的步骤操作，获得注册和用户的最佳体验。 *你可以完成* 注册，但在部署第一台设备之前必须修复这些问题。        |
|未就绪 | *如果不修复这些问题，注册将失败。* 请按照工具或本文中的步骤进行解析。        |
|错误 | 你Azure Active Directory (AD) 角色的权限不足，无法运行此检查。 |

> [!NOTE]
> 此工具报告的结果仅反映设置在运行它的特定时间点的状态。 如果您稍后对 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的策略进行了任何更改，则"就绪"的项目可能会变为"未就绪"。 若要避免与Microsoft 托管桌面问题，请在更改任何策略之前检查本文中描述的特定设置。

## <a name="microsoft-intune-settings"></a>Microsoft Intune设置

可以在管理中心访问 intune Microsoft Endpoint Manager[设置](https://endpoint.microsoft.com)。

### <a name="autopilot-deployment-profile"></a>Autopilot 部署配置文件

你不应具有面向分配的任何现有 Autopilot 配置文件或具有Microsoft 托管桌面动态组。 Microsoft 托管桌面 Autopilot 预配新设备。 如果你有现有的 Autopilot 部署配置文件，必须将"将所有目标设备转换为 Autopilot"设置设置为"否"，Autopilot 的托管桌面准备情况测试才能成功。

**未就绪**

你拥有分配给所有设备的 Autopilot 配置文件。 有关步骤，请参阅在[Intune Windows Autopilot 注册Windows设备](/mem/autopilot/enrollment-autopilot)。 注册Microsoft 托管桌面，设置 Autopilot 策略以排除 **现代工作区设备 -所有** Azure AD 组。

**公告**

确保你的 Autopilot 配置文件面向不包括任何设备的已分配或Microsoft 托管桌面 Azure AD 组。 有关步骤，请参阅在[Intune Windows Autopilot 注册Windows设备](/mem/autopilot/enrollment-autopilot)。 注册Microsoft 托管桌面，设置 Autopilot 配置文件以排除现代 **工作区设备 -所有** Azure AD 组。


### <a name="certificate-connectors"></a>证书连接器

如果你有任何证书连接器将由你想要在 Microsoft 托管桌面 中注册的设备使用，则连接器不应有任何错误。 只有以下其中一条公告适用于你的情况，因此请仔细检查它们。

**公告**

不存在证书连接器。 虽然可能不需要任何连接器，但应评估是否需要一些连接器在 Microsoft 托管桌面 连接。 有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面。](certs-wifi-lan.md)

**公告**

至少有一个证书连接器出现错误。 如果需要此连接器向设备Microsoft 托管桌面证书，则必须解决此错误。 有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面。](certs-wifi-lan.md)


**公告**

您至少有一个证书连接器，并且未报告任何错误。 但是，在准备部署时，可能需要创建一个配置文件，以将连接器重新用于Microsoft 托管桌面设备。 有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面。](certs-wifi-lan.md)

### <a name="company-portal"></a>公司门户

Microsoft 托管桌面 IT 管理员要求 IT 管理员Intune 公司门户为用户安装 Microsoft 托管桌面 设备。 

**未就绪**

您尚未为公司门户安装任何内容。 购买公司门户并强制 Intune 和 适用于企业的 Microsoft Store。 有关详细信息，请参阅 Install [Intune 公司门户 on devices。](../get-started/company-portal.md)


### <a name="conditional-access-policies"></a>条件访问策略

条件访问策略不得Microsoft 托管桌面 Intune 和 Azure AD (租户) 管理 Azure AD 组织。

**未就绪**

您至少有一个面向所有用户的条件访问策略。 注册期间，我们会从Microsoft 托管桌面条件访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。 注册后，你可以查看Microsoft 托管桌面条件访问策略Microsoft Endpoint Manager。 有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**公告**

您具有可能会阻止用户管理 Microsoft 托管桌面 服务的条件Microsoft 托管桌面策略。 注册期间，我们会从Microsoft 托管桌面条件访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。 有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**错误**

Intune 管理员角色没有足够的权限进行此检查。 你还需要分配以下任一 Azure AD 角色来运行此检查：

- 安全信息读取者
- 安全管理员
- 条件访问管理员
- 全局读取者
- 设备管理员


### <a name="device-compliance-policies"></a>设备合规性策略

Azure AD 组织中 Intune 设备合规性策略可能会影响Microsoft 托管桌面设备。

**公告**

您至少有一个适用于所有用户的合规性策略。 Microsoft 托管桌面还包括将应用于你的设备Microsoft 托管桌面策略。 查看组织创建的所有适用于Microsoft 托管桌面合规性策略，以确保没有冲突。 有关步骤，请参阅[在策略Microsoft Intune。](/mem/intune/protect/create-compliance-policy)



### <a name="device-configuration-profiles"></a>设备配置文件

Azure AD 组织中 Intune 设备配置文件不得面向任何 Microsoft 管理桌面设备或用户。

**未就绪**

你至少有一个配置文件适用于所有用户、所有设备或两者。 重置配置文件以应用于不包括任何设备配置的特定 Azure AD Microsoft 托管桌面组。 有关步骤，请参阅[Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure)。

**公告**

确保你拥有的任何配置策略不包括任何Microsoft 托管桌面或用户。 有关步骤，请参阅[Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure)。



### <a name="device-type-restrictions"></a>设备类型限制

Microsoft 托管桌面设备必须在 Intune 中注册。

**未就绪**

你当前至少配置了一个注册限制策略，Windows Intune 中注册。 按照为面向用户的每个 [注册](/mem/intune/enrollment/enrollment-restrictions-set)限制策略设置注册Microsoft 托管桌面中的步骤操作，Windows (**MDM**) 设置更改为 **"允许"。** 但是，你可以将 MDM设备上个人拥有 **Windows ()** 设置为 **阻止**。 


### <a name="enrollment-status-page"></a>注册状态页

YOU currently have the Enrollment Status Page (ESP) enabled. 如果打算参加此功能的公共Microsoft 托管桌面预览版，可以忽略此项。 有关详细信息，请参阅 [Autopilot 首次运行体验和注册状态页面](../get-started/esp-first-run.md)。

**未就绪**

将 ESP 默认配置文件设置为"**显示应用和配置文件配置进度"。** 通过按照设置注册状态页 中的步骤操作，禁用此设置或确保任何 Azure AD 组的工作分配不包括Microsoft 托管桌面[设备](/mem/intune/enrollment/windows-enrollment-status)。

**公告**

确保未将具有"显示应用和配置文件配置进度"设置的任何配置文件分配给任何 Azure AD 组，该组Microsoft 托管桌面设备。 有关详细信息，请参阅设置 [注册状态页](/mem/intune/enrollment/windows-enrollment-status)。

### <a name="microsoft-store-for-business"></a>适用于企业的 Microsoft Store

我们使用 适用于企业的 Microsoft Store 在 Microsoft 托管桌面 上部署 公司门户 应用，以允许用户选择安装某些应用，例如 Microsoft Project 和 Microsoft Visio (（如果允许) ）。

**未就绪**

适用于企业的 Microsoft Store未启用或未与 Intune 同步。 有关详细信息，请参阅[如何使用](/mem/intune/apps/windows-store-for-business)适用于企业的 Microsoft Store 管理批量购买的应用Microsoft Intune在设备上Intune 公司门户[购买的应用](../get-started/company-portal.md)。

### <a name="multifactor-authentication"></a>多重身份验证

多重身份验证不得阻止Microsoft 托管桌面 Intune 和 Azure AD (Azure AD) Azure AD 组织。


**未就绪**

您具有为分配给所有用户的条件 **访问策略所需的** 一些多重身份验证策略。 注册期间，我们将从Microsoft 托管桌面条件访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。 有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**公告**

您具有条件访问策略所需的多重身份验证，这些策略Microsoft 托管桌面管理 Microsoft 托管桌面 服务。 注册期间，我们将从Microsoft 托管桌面条件访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。 有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。

**错误**

Intune 管理员角色没有足够的权限进行此检查。 你还需要分配以下任一 Azure AD 角色来运行此检查：

- 安全信息读取者
- 安全管理员
- 条件访问管理员
- 全局读取者
- 设备管理员


### <a name="powershell-scripts"></a>PowerShell 脚本

Windows PowerShell无法以面向特定设备的方式分配Microsoft 托管桌面脚本。  

**公告**

请确保 Azure AD Windows PowerShell中的脚本不面向任何 Microsoft 管理桌面设备或用户。 不要将 PowerShell 脚本分配给所有用户、所有设备或两者。 将策略更改为使用面向不包括任何设备或用户的特定 Azure AD Microsoft 托管桌面分配。 有关详细信息，请参阅在[Intune Windows 10设备上使用 PowerShell 脚本](/mem/intune/apps/intune-management-extension)。

### <a name="region"></a>区域

你的区域必须受 Microsoft 托管桌面。

**未就绪**

你的 Azure AD 组织区域当前不受 Microsoft 托管桌面。 有关详细信息，请参阅支持Microsoft 托管桌面[和语言](../service-description/regions-languages.md)。

**公告**

Azure AD 组织所在的一个或多个国家/地区不受 Microsoft 托管桌面。 有关详细信息，请参阅支持Microsoft 托管桌面[和语言](../service-description/regions-languages.md)。


### <a name="security-baselines"></a>安全基线

安全基线策略不应面向任何Microsoft 托管桌面设备。

**未就绪**

你有一个面向所有用户、所有设备或两者的安全基线配置文件。 更改策略以使用面向不包含任何设备配置的特定 Azure AD Microsoft 托管桌面分配。 有关步骤，请参阅[使用安全基线配置Windows 10 Intune 中的设备](/mem/intune/protect/security-baselines)。 在注册期间，我们将新的安全基线应用于所有Microsoft 托管桌面设备。 注册后，你可以查看 Microsoft 托管桌面 配置策略区域中 **的** Microsoft Endpoint Manager。

**公告**

确保你已排除任何安全基线策略Microsoft 托管桌面设备。 有关步骤，请参阅[使用安全基线配置Windows 10 Intune 中的设备](/mem/intune/protect/security-baselines)。 在注册期间，我们将新的安全基线应用于所有Microsoft 托管桌面设备。 现代 **工作区设备 - 所有** Azure AD 组是注册 Microsoft 托管桌面 时创建的动态组，因此你必须在注册后返回以排除此组。 

### <a name="unlicensed-admins"></a>未经授权的管理员

当我们与 Azure AD 组织交互时，必须启用此设置以避免出现"缺少权限"错误。 

**未就绪**

**应启用允许访问** 未授权的管理员。 有关步骤，请参阅 [来宾帐户的先决条件](/microsoft-365/managed-desktop/get-ready/guest-accounts)。

### <a name="windows-apps"></a>Windows应用

查看希望用户拥有Microsoft 托管桌面的应用。

**公告**

你应该准备希望用户拥有的应用Microsoft 托管桌面清单。 由于这些应用必须由 Intune 部署，因此请评估是否重新使用现有 Intune 应用。 请考虑使用[公司门户 (请参阅在](../get-started/company-portal.md)设备上Intune 公司门户安装应用和注册状态页 (ESP) 将应用分发给你的用户。 有关详细信息，请参阅[Autopilot](../get-started/esp-first-run.md) [Microsoft 托管桌面](apps.md)和注册状态页的应用和首次运行体验。

你可以要求 Microsoft 帐户代表在 Microsoft Endpoint Configuration Manager中确定准备迁移到 Intune 或需要调整的应用。


### <a name="windows-hello-for-business"></a>Windows Hello 企业版

Microsoft 托管桌面需要Windows Hello For Business。

**公告**

Windows Hello禁用或不设置适用于 Business 的组。 按照 Create [a Windows Hello for Business policy 中的步骤启用它](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。


### <a name="windows-10-update-rings"></a>Windows 10更新圈

Intune Windows 10更新圈"策略不得面向任何Microsoft 托管桌面设备。

**未就绪**

你有一个面向所有设备、所有用户或两者同时面向的"更新圈"策略。 更改策略以使用面向不包含任何设备配置的特定 Azure AD Microsoft 托管桌面分配。 有关步骤，请参阅[在 Intune Windows 10软件更新。](/mem/intune/protect/windows-update-for-business-configure)

**公告**

确保你拥有的任何更新圈策略不包括现代 **工作区设备 -所有** Azure AD 组。 如果你已向这些策略分配了 Azure AD 用户组，请确保你已排除任何更新圈策略，并且你已排除将 Microsoft 托管桌面 用户添加到 (或等效组) 的新式 **工作区 -** 所有 Azure AD 组。 有关步骤，请参阅[在 Intune Windows 10软件更新。](/mem/intune/protect/windows-update-for-business-configure) 现代 **工作区设备 -全部** 和现代工作区 **-所有** Azure AD 组都是我们在注册 Microsoft 托管桌面 时创建的组，因此你必须在注册后返回以排除此组。


## <a name="azure-active-directory-settings"></a>Azure Active Directory设置

可以在 Azure Azure Active Directory 访问[自定义设置](https://portal.azure.com)。

### <a name="intune-enrollment"></a>Intune 注册

Windows 10 Azure AD 组织的设备必须能够在 Intune 中自动注册。

**公告**

确保 MDM **用户作用域设置为****"** 部分"或"**全部"，** 而不是"**无"。** 如果你选择 **"一些**"，请在注册后返回，然后为组选择"新式 **工作区 -** 所有 Azure AD"组，或选择面向所有用户的Microsoft 托管桌面组。   请参阅[使用 Windows 设置设备注册Microsoft Intune。](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

### <a name="ad-hoc-subscriptions"></a>临时订阅

建议如何检查设置，如果 (设置为"false"，) 可能会Enterprise状态漫游正常工作。

**公告**

确保 **AllowAdHocSubscriptions** 设置为 **True**。 否则，Enterprise状态漫游可能不起作用。 有关详细信息，请参阅 [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings)。


### <a name="enterprise-state-roaming"></a>企业状态漫游

Enterprise应启用状态漫游。

**公告**

确保为"Enterprise"**组** 或"所选组"启用状态 **漫游**。 有关详细信息，请参阅 Enable [Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable)。

### <a name="guest-invitation-settings"></a>来宾邀请设置

Microsoft 托管桌面建议调整来宾邀请设置，因为默认设置允许目录中的所有用户和来宾邀请来宾。

**公告**

**应启用分配给特定管理员角色** 的成员用户和用户可以邀请来宾用户，包括具有成员权限的来宾。 有关步骤，请参阅 [来宾帐户的先决条件](/microsoft-365/managed-desktop/get-ready/guest-accounts)。

### <a name="guest-user-access"></a>来宾用户访问

Microsoft 托管桌面建议调整来宾用户访问，因为默认设置允许目录中的所有来宾用户与成员具有相同的访问权限。

**公告**

**应启用来宾用户对目录对象的属性** 和成员身份的有限访问权限。 有关步骤，请参阅 [来宾帐户的先决条件](/microsoft-365/managed-desktop/get-ready/guest-accounts)。

### <a name="licenses"></a>许可证

需要大量许可证才能使用Microsoft 托管桌面。

**未就绪**

没有使用许可证所需的全部许可证Microsoft 托管桌面。 有关详细信息，请参阅Microsoft 托管桌面[和](../intro/technologies.md)[关于许可证的更多信息](prerequisites.md#more-about-licenses)。


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft 托管桌面服务帐户

某些帐户名可能会与管理 Microsoft 托管桌面 服务Microsoft 托管桌面名称冲突。

**未就绪**

您至少有一个帐户名称与由 Microsoft 托管桌面。 与 Microsoft 帐户代表合作，排除这些帐户名。 我们不会公开列出帐户名称，以最大限度地降低安全风险。 


### <a name="security-administrator-roles"></a>安全管理员角色

具有特定安全角色的用户必须在 Microsoft Defender for Endpoint 中分配这些角色。

**公告**

如果你的用户已分配到 Azure AD 组织中任何这些角色，请确保他们在 Microsoft Defender for Endpoint 中也分配了这些角色。 否则，具有这些角色的管理员将无法访问管理门户。

- 安全操作员
- 全局读取者

有关详细信息，请参阅为基于角色 [的访问控制创建和管理角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。


### <a name="security-default"></a>安全默认值

Azure Active Directory中的Microsoft 托管桌面将阻止用户管理设备。

**未就绪**

你已打开"安全性默认值"。 关闭安全默认值并设置条件访问策略。 有关详细信息，请参阅 Common [Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。

### <a name="self-service-password-reset"></a>自助服务密码重置

SSPR 帐户 (SSPR) 可以启用自助服务密码重置Microsoft 托管桌面服务帐户Microsoft 托管桌面用户。 有关详细信息，请参阅[教程：允许用户](/azure/active-directory/authentication/tutorial-enable-sspr)使用自助密码重置解锁Azure Active Directory重置密码。

**公告**

确保"SSPR **选择**"设置包括Microsoft 托管桌面但不包括Microsoft 托管桌面帐户。 Microsoft 托管桌面启用 SSPR 后，服务帐户将无法正常工作。  


### <a name="standard-user-role"></a>标准用户角色

除了分配了全局管理员和设备管理员的 Azure AD 角色的用户外，Microsoft 托管桌面用户将是没有本地管理员权限的标准用户。 当所有其他用户启动其新设备时，将为其分配一个Microsoft 托管桌面角色。

**公告**

Microsoft 托管桌面注册后，用户将不会在 Microsoft 托管桌面 设备上拥有本地管理员权限。

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 企业应用版

### <a name="onedrive"></a>OneDrive

"**仅允许在加入特定域** 的 PC 上同步"设置将与Microsoft 托管桌面。 可以在管理OneDrive访问OneDrive[设置](https://admin.onedrive.com)。

**公告**

你正在使用" **仅允许在加入特定域的 PC 上同步"** 设置。 此设置将不能用于Microsoft 托管桌面。 禁用此设置，改为将OneDrive设置为使用条件访问策略。 请参阅 [规划条件访问部署](/azure/active-directory/conditional-access/plan-conditional-access) 获取帮助。
