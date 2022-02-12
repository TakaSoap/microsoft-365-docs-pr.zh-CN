---
title: 修复准备情况评估工具发现的问题
description: 针对工具找到的每个问题要采取的详细操作
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: badf2d65f2b29e265a1312cb1d5f4802a44f3cb3
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766544"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>修复准备情况评估工具发现的问题

对于每个检查，该工具将报告四个可能的结果之一：

| 结果  | 含义 |
| ----- | ----- |
| Ready | 完成注册前无需任何操作。 |
| 公告 | 按照工具或本文中的步骤操作，获得注册和用户的最佳体验。 <br><br> *你可以完成* 注册，但在部署第一台设备之前必须修复这些问题。 |
| 未就绪 | **如果不修复这些问题，注册将失败。** <br><br> 请按照工具或本文中的步骤进行解析。 |
| Error | 你Azure Active Directory (AD) 角色的权限不足，无法运行此检查。 |

> [!NOTE]
> 此工具报告的结果仅在运行设置时反映设置的状态。 如果您稍后对 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的策略进行更改，则"就绪"的项目可能会变为"未就绪"。 若要避免与Microsoft 托管桌面问题，请在更改任何策略之前检查本文中描述的特定设置。

## <a name="microsoft-intune-settings"></a>Microsoft Intune设置

可以在管理中心访问 intune Microsoft Endpoint Manager[设置](https://endpoint.microsoft.com)。

### <a name="autopilot-deployment-profile"></a>Autopilot 部署配置文件

不应有任何面向已分配或动态组的现有 Autopilot 配置文件Microsoft 托管桌面设备。 Microsoft 托管桌面 Autopilot 配置新设备。 如果你有现有的 Autopilot 部署配置文件，必须将"将所有目标设备转换为 **Autopilot**"设置设置为 **"** 否"，Microsoft 托管桌面 Autopilot 准备情况测试才能成功。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 你拥有分配给所有设备的 Autopilot 配置文件。 <br><br> 有关详细信息，请参阅使用 [Windows Autopilot 在 Intune 中注册Windows设备](/mem/autopilot/enrollment-autopilot)。 注册Microsoft 托管桌面，设置 Autopilot 策略以排除现代 **工作区设备 -** 所有Azure AD组。
| 公告 | 确保你的 Autopilot 配置文件面向不包括Azure AD分配或动态Microsoft 托管桌面组。 <br><br> 有关详细信息，请参阅使用 [Windows Autopilot 在 Intune 中注册Windows设备](/mem/autopilot/enrollment-autopilot)。 注册Microsoft 托管桌面，将 Autopilot 配置文件设置为排除现代 **工作区设备 -** 所有Azure AD组。 |

### <a name="certificate-connectors"></a>证书连接器

如果你有任何证书连接器将由你想要在 Microsoft 托管桌面 注册的设备使用，则连接器不应有任何错误。 只有以下其中一条公告适用于你的情况，因此请仔细检查它们。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | 不存在证书连接器。 可能不需要任何连接器，但应评估是否需要一些连接器来连接 Microsoft 托管桌面连接。 <br><br> 有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面](certs-wifi-lan.md)。 |
| 公告 | 至少有一个证书连接器出现错误。 如果需要此连接器向设备Microsoft 托管桌面证书，则必须解决此错误。 <br><br> 有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面](certs-wifi-lan.md)。 |
| 公告 | 您至少有一个证书连接器，并且未报告任何错误。 但是，在准备部署时，你可能需要创建一个配置文件，以将连接器重新用于Microsoft 托管桌面设备。 <br><br> 有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面](certs-wifi-lan.md)。 |

### <a name="company-portal"></a>公司门户

Microsoft 托管桌面要求 IT 管理员使用 Intune 公司门户 为用户安装 Microsoft 托管桌面 服务。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 你未为公司门户安装任何内容。 购买公司门户并强制 Intune 和 适用于企业的 Microsoft Store。 <br><br> 有关详细信息，请参阅在[设备上Intune 公司门户安装程序](../get-started/company-portal.md)。

### <a name="conditional-access-policies"></a>条件访问策略

条件访问策略无法阻止用户Microsoft 托管桌面 Intune Azure AD租户 () 管理Azure AD。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 您至少有一个面向所有用户的条件访问策略。 <br><br> 注册期间，我们将从相关Microsoft 托管桌面访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。 <br><br> 注册后，可以在 Microsoft Endpoint Manager 中查看Microsoft 托管桌面条件访问Microsoft Endpoint Manager。 有关这些服务帐户的更多信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。 |
| 公告 | 您具有可能会阻止用户管理 Microsoft 托管桌面 服务的条件Microsoft 托管桌面策略。 <br><br> 注册期间，我们将从相关Microsoft 托管桌面访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。 <br><br> 有关这些服务帐户详细信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。 |
| Error | Intune 管理员角色没有足够的权限进行此检查。 还需要分配以下角色Azure AD运行此检查： <ul><li>安全读取者</li><li>安全管理员</li><li>条件访问管理</li><li>全局读取者</li><li>设备管理员</li></ul>
### <a name="device-compliance-policies"></a>设备合规性策略

组织中 Intune 设备合规性Azure AD可能会影响Microsoft 托管桌面设备。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | 您至少有一个适用于所有用户的合规性策略。 Microsoft 托管桌面还包括将应用于你的设备Microsoft 托管桌面策略。 查看组织创建的所有适用于Microsoft 托管桌面合规性策略，以确保没有冲突。 <br><br> 有关详细信息，请参阅在 Microsoft Intune[。](/mem/intune/protect/create-compliance-policy) |

### <a name="device-configuration-profiles"></a>设备配置文件

你的组织中的 Intune 设备Azure AD配置文件不能面向任何 Microsoft 管理桌面设备或用户。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 你至少有一个配置文件适用于所有用户、所有设备或两者。 重置配置文件，以应用于Azure AD不包括任何设备的特定Microsoft 托管桌面组。 <br><br> 有关详细信息，请参阅 Create [a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure)。 |
| 公告 | 确保你拥有的任何配置策略不包括任何Microsoft 托管桌面或用户。 <br><br> 有关详细信息，请参阅 Create [a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure)。 |

### <a name="device-type-restrictions"></a>设备类型限制

Microsoft 托管桌面设备必须在 Intune 中注册。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 你当前至少配置了一个注册限制策略，Windows Intune 中注册。 <br><br> 按照为面向用户的每个 [注册](/mem/intune/enrollment/enrollment-restrictions-set)限制策略设置注册Microsoft 托管桌面中的步骤操作，Windows (**MDM**) 设置为 **允许**。 但是，你可以将 MDM 设备上Windows (拥有 **)** 设置为 **阻止**。 |

### <a name="enrollment-status-page"></a>注册状态页

YOU currently have the Enrollment Status Page (ESP) enabled. 如果你打算参加此功能的公共Microsoft 托管桌面预览版，可以忽略此项。 有关详细信息，请参阅 [Autopilot 首次运行体验和注册状态页](../get-started/esp-first-run.md)。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 将 ESP 默认配置文件设置为 **"显示应用和配置文件配置进度"**。 <br><br> 通过按照设置注册状态Azure AD中的步骤，禁用此设置或确保Azure AD组的工作分配不包括Microsoft 托管桌面[设备](/mem/intune/enrollment/windows-enrollment-status)。 |
| 公告 | 确保未将具有"显示应用和配置文件配置进度"设置的任何配置文件分配给任何包含Azure AD配置Microsoft 托管桌面组。 <br><br> 有关详细信息，请参阅设置 [注册状态页](/mem/intune/enrollment/windows-enrollment-status)。 |

### <a name="microsoft-store-for-business"></a>适用于企业的 Microsoft Store

我们使用 适用于企业的 Microsoft Store，公司门户部署 Microsoft 托管桌面。 此方法允许用户选择性地安装某些应用，如 Microsoft Project 和 Microsoft Visio (（如果允许) ）。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 适用于企业的 Microsoft Store未启用或未与 Intune 同步。 <br><br> 有关详细信息，请参阅[如何使用](/mem/intune/apps/windows-store-for-business) 适用于企业的 Microsoft Store 管理批量购买的应用Microsoft Intune设备上Intune 公司门户[购买的应用](../get-started/company-portal.md)。 |

### <a name="multi-factor-authentication"></a>多重身份验证

多重身份验证无法阻止用户Microsoft 托管桌面 Intune 和 Azure AD 中的 Azure AD () 租户Azure AD。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 为分配给所有用户的条件访问策略设置了一些多重身份验证策略。 <br><br> 注册期间，我们将从相关Microsoft 托管桌面访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。 <br><br> 有关这些服务帐户详细信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。 |
| 公告 | 您具有条件访问策略所需的多重身份验证，这些策略Microsoft 托管桌面管理 Microsoft 托管桌面服务。 <br><br> 在注册期间，请Microsoft 托管桌面条件访问策略中排除服务帐户，并应用新的条件访问策略来限制访问这些帐户。 有关这些服务帐户详细信息，请参阅 [标准操作过程](../service-description/operations-and-monitoring.md#standard-operating-procedures)。 |
| Error | Intune 管理员角色没有足够的权限进行此检查。 还需要分配以下角色Azure AD运行此检查： <ul><li>安全读取者</li><li>安全管理员</li><li>条件访问管理</li><li>全局读取者</li><li>设备管理员</li></ul>

### <a name="powershell-scripts"></a>PowerShell 脚本

Windows PowerShell脚本无法以面向特定设备的方式Microsoft 托管桌面分配。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | 请确保你的Windows PowerShell中的Azure AD脚本不面向任何 Microsoft 管理桌面设备或用户。 不要将 PowerShell 脚本分配给所有用户、所有设备或两者。 将策略更改为使用面向不包含任何Azure AD组的特定组分配Microsoft 托管桌面用户。 <br><br> 有关详细信息，请参阅[在 Intune Windows 10使用 PowerShell 脚本](/mem/intune/apps/intune-management-extension)。 |

### <a name="region"></a>地区

你的区域必须受 Microsoft 托管桌面。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 你的 Azure AD 组织区域当前不受组织Microsoft 托管桌面。 <br><br> 有关详细信息，请参阅支持Microsoft 托管桌面[和语言](../service-description/regions-languages.md)。 |
| 公告 | 你的组织所在的一Azure AD国家/地区不受 Microsoft 托管桌面。 <br><br> 有关详细信息，请参阅支持Microsoft 托管桌面[和语言](../service-description/regions-languages.md)。 |

### <a name="security-baselines"></a>安全基线

安全基线策略不应面向任何Microsoft 托管桌面设备。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 你有一个面向所有用户、所有设备或两者的安全基线配置文件。 更改策略以使用面向不包含任何Azure AD组的特定组Microsoft 托管桌面分配。 <br><br> 有关详细信息，请参阅使用[安全基线配置Windows 10 Intune 中的设备](/mem/intune/protect/security-baselines)。 在注册期间，我们将新的安全基线应用于所有Microsoft 托管桌面设备。 注册后，你可以查看 Microsoft 托管桌面 配置策略区域中 **的** Microsoft Endpoint Manager。 |
| 公告 | 确保你拥有的任何安全基线策略都Microsoft 托管桌面设备。 有关详细信息，请参阅使用[安全基线配置Windows 10 Intune 中的设备](/mem/intune/protect/security-baselines)。 <br><br> 在注册期间，我们将新的安全基线应用于所有Microsoft 托管桌面设备。 现代 **工作区设备 -** 所有Azure AD组都是当你注册到 Microsoft 托管桌面 时我们创建的动态Microsoft 托管桌面。 注册后，必须返回以排除此组。 |

### <a name="unlicensed-admins"></a>未经授权的管理员

必须启用此设置，以避免当我们与您的组织进行交互时出现"缺少Azure AD错误。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | **应启用允许访问** 未授权的管理员。 有关详细信息，请参阅 [来宾帐户的先决条件](/microsoft-365/managed-desktop/get-ready/guest-accounts)。 |

### <a name="windows-apps"></a>Windows应用

查看希望用户Microsoft 托管桌面的应用。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | 你应该准备希望用户拥有的应用Microsoft 托管桌面清单。 由于这些应用必须由 Intune 部署，因此请评估是否重新使用现有 Intune 应用。 请考虑使用 [公司门户 (请参阅在](../get-started/company-portal.md)设备上Intune 公司门户安装应用和注册状态页 (ESP) 将应用分发给你的用户。 <br><br> 有关详细信息，请参阅 [Autopilot Microsoft 托管桌面](apps.md)首次运行体验的应用和[注册状态页](../get-started/esp-first-run.md)。 <br><br> 你可以要求 Microsoft 帐户代表在 Microsoft Endpoint Configuration Manager 中查询，以确定准备迁移到 Intune 或需要调整的应用。 |

### <a name="windows-hello-for-business"></a>Windows Hello 企业版

Microsoft 托管桌面需要Windows Hello For Business。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | Windows Hello或已禁用或不设置适用于 Business 的组。 按照 Create [a Windows Hello for Business policy 中的步骤启用它](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。 |

### <a name="windows-10-update-rings"></a>Windows 10更新圈

Intune Windows 10更新圈"策略不得面向任何Microsoft 托管桌面设备。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 你有一个面向所有设备、所有用户或两者同时面向的"更新圈"策略。 更改策略以使用面向不包含任何Azure AD组的特定组Microsoft 托管桌面分配。 <br><br> 有关详细信息，请参阅在 [Intune Windows 10软件更新](/mem/intune/protect/windows-update-for-business-configure)。 |
| 公告 | 确保你拥有的任何更新圈策略都排除现代 **工作区设备 - 所有** Azure AD组。 如果你向这些策略分配了 Azure AD 用户组，请确保你已排除所有已排除的新式工作区 **-** 你向 (或等效组) 添加 Microsoft 托管桌面 用户的所有 Azure AD 组。 <br><br> 有关详细信息，请参阅在 [Intune Windows 10软件更新](/mem/intune/protect/windows-update-for-business-configure)。 现代 **工作区设备 - 全部和** 现代工作区 **-** 所有Azure AD组都是当你注册新工作区时创建的Microsoft 托管桌面。 注册后，必须返回以排除此组。 |

## <a name="azure-active-directory-settings"></a>Azure Active Directory设置

可以在 Azure Azure Active Directory访问[自定义设置](https://portal.azure.com)。

### <a name="intune-enrollment"></a>Intune 注册

Windows 10组织中Azure AD设备必须能够在 Intune 中自动注册。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | 确保 MDM **用户作用域** 设置为 **"** 部分"或" **全部**"，而不是 **"无"**。 <br><br> 如果选择"**部分"**，请在注册后返回并选择"新式工作区 **-** 所有Azure AD **组"组** 或面向所有用户的等效Microsoft 托管桌面组。 <br><br> 有关详细信息，请参阅使用 Windows [设置设备注册Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。 |

### <a name="ad-hoc-subscriptions"></a>临时订阅

建议如何检查设置，如果设置为"false"，可能会Enterprise状态漫游正常工作。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | 确保 **AllowAdHocSubscriptions** 设置为 **True**。 否则，Enterprise状态漫游可能不起作用。 <br><br> 有关详细信息，请参阅 [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings)。 |

### <a name="enterprise-state-roaming"></a>企业状态漫游

Enterprise应启用状态漫游。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | 确保为"Enterprise"**组** 或"所选组"启用状态 **漫游**。 <br><br> 有关详细信息，请参阅 Enable [Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable)。 |

### <a name="guest-invitation-settings"></a>来宾邀请设置

Microsoft 托管桌面建议调整来宾邀请设置，因为默认设置允许目录中的所有用户和来宾邀请来宾。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | **应启用分配给特定管理员角色的成员用户和用户可以** 邀请来宾，包括具有成员权限的来宾。 <br><br> 有关详细信息，请参阅 [来宾帐户的先决条件](/microsoft-365/managed-desktop/get-ready/guest-accounts)。 |

### <a name="guest-user-access"></a>来宾用户访问

Microsoft 托管桌面调整来宾访问，因为默认设置允许目录中的所有来宾与成员具有相同的访问权限。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | **应启用来宾用户对目录对象的属性** 和成员身份的有限访问权限。 <br><br> 有关详细信息，请参阅 [来宾帐户的先决条件](/microsoft-365/managed-desktop/get-ready/guest-accounts)。 |

### <a name="licenses"></a>许可证

许多许可证都需要用于Microsoft 托管桌面。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 没有使用许可证所需的全部许可证Microsoft 托管桌面。 <br><br> 有关详细信息，请参阅Microsoft 托管桌面[和](../intro/technologies.md)[关于许可证详细信息](prerequisites.md#more-about-licenses)。 |

### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft 托管桌面服务帐户

某些帐户名可能会与管理 Microsoft 托管桌面 服务Microsoft 托管桌面名称冲突。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 您至少有一个帐户名称与由 Microsoft 托管桌面。 与 Microsoft 帐户代表合作，排除这些帐户名。 我们不会公开列出帐户名称，以最大限度地降低安全风险。

### <a name="security-administrator-roles"></a>安全管理员角色

具有特定安全角色的用户必须在 Microsoft Defender for Endpoint 中分配这些角色。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | 如果你的用户分配了组织中任何这些角色Azure AD，请确保他们在 Microsoft Defender for Endpoint 中也分配了这些角色。 否则，具有这些角色的管理员将无法访问管理门户。 <ul><li>安全操作员</li><li>全局读取者</li></ul> <br> 有关详细信息，请参阅为基于角色 [的访问控制创建和管理角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。

### <a name="security-default"></a>安全默认值

Azure Active Directory中的Microsoft 托管桌面将阻止用户管理设备。

| 结果  | 含义 |
| ----- | ----- |
| 未就绪 | 你已打开"安全性默认值"。 关闭安全默认值并设置条件访问策略。 <br><br> 有关详细信息，请参阅 Common [Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。 |

### <a name="self-service-password-reset"></a>自助服务密码重置

SSPR (可) SSPR 帐户的自助服务密码重置Microsoft 托管桌面服务帐户Microsoft 托管桌面用户。 <br><br> 有关详细信息，请参阅[教程：允许用户](/azure/active-directory/authentication/tutorial-enable-sspr)使用自助密码重置解锁Azure Active Directory重置密码。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | 确保"SSPR **选择**"设置包括Microsoft 托管桌面用户，但不包括Microsoft 托管桌面帐户。 Microsoft 托管桌面 SSPR 后，服务帐户无法正常工作。 |

### <a name="standard-user-role"></a>标准用户角色

除了分配了全局管理员和设备管理员角色Azure Active Directory，Microsoft 托管桌面用户将是没有本地管理员权限的标准用户。 在所有其他用户启动其新设备时，将为其分配Microsoft 托管桌面角色。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | Microsoft 托管桌面注册后，用户将不会在 Microsoft 托管桌面设备上拥有本地管理员权限。 |

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 企业应用版

### <a name="onedrive"></a>OneDrive

"**仅允许在加入特定域的 PC** 上同步"设置将与Microsoft 托管桌面。 可以在管理OneDrive访问OneDrive[设置](https://admin.onedrive.com)。

| 结果  | 含义 |
| ----- | ----- |
| 公告 | 你正在使用" **仅允许在加入特定域的 PC 上同步"** 设置。 此设置将不能用于Microsoft 托管桌面。 禁用此设置。 相反，将OneDrive设置为使用条件访问策略。 <br><br> 有关详细信息，请参阅 [规划条件访问部署](/azure/active-directory/conditional-access/plan-conditional-access) 获取帮助。 |
