---
title: 第 3 步。 Microsoft 365 企业版租户的标识
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 为 Microsoft 365 租户部署正确的标识模型，并强制执行强用户登录。
ms.openlocfilehash: ca545e0152b567cd566ce939e369988f864042a9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407166"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a>步骤 3. Microsoft 365 企业版租户的标识

Microsoft 365 租户包括 Azure Active Directory (Azure AD) 租户，用于管理登录的标识和身份验证。正确配置标识基础结构对于管理组织的 Microsoft 365 用户访问和权限至关重要。

## <a name="cloud-only-vs-hybrid"></a>仅云与混合

下面是两种类型的标识模型及其最佳适合和优点。


| 模型 | 说明 | Microsoft 365 如何对用户凭据进行身份验证 | 最适用于 | 最大好处 |
|:-------|:-----|:-----|:-----|:-----|
| 仅限云 | 用户帐户仅存在于 Microsoft 365 租户的 Azure AD 租户中。 | Microsoft 365 租户的 Azure AD 租户使用云标识帐户执行身份验证。 | 没有或不需要本地 AD DS 的组织。 | 易于使用。 无需额外的目录工具或服务器。 |
| 混合 |  用户帐户存在于本地 Active Directory 域服务 (AD DS) 并且副本也位于 Microsoft 365 租户的 Azure AD 租户中。 Azure AD Connect 在本地服务器上运行，以将 AD DS 更改同步到 Azure AD 租户。 Azure AD 中的用户帐户可能还包括已哈希 AD DS 用户帐户密码的哈希版本。 | Microsoft 365 租户的 Azure AD 租户处理身份验证过程或将用户重定向到其他标识提供程序。 | 使用 AD DS 或其他标识提供程序的组织。 | 在访问本地或基于云的资源时，用户可以使用相同的凭据。 |
||||||

以下是仅云标识的基本组件。
 
![仅云标识的基本组件](../media/about-microsoft-365-identity/cloud-only-identity.png)

在此图中，本地和远程用户使用其 Microsoft 365 租户的 Azure AD 租户中的帐户登录。

下面是混合标识的基本组件。

![混合标识的基本组件](../media/about-microsoft-365-identity/hybrid-identity.png)

在此图中，本地用户和远程用户使用 Azure AD 租户中已复制自其本地 AD DS 的帐户登录到其 Microsoft 365 租户。

## <a name="synchronizing-your-on-premises-ad-ds"></a>同步本地 AD DS

混合标识模型和目录同步是采用 Microsoft 365 的企业客户最常用的选择，具体取决于业务需求和技术要求。 目录同步允许你管理 AD DS 中的标识，并且用户帐户、组和联系人的所有更新都同步到 Microsoft 365 租户的 Azure AD 租户。

>[!Note]
>首次同步 AD DS 用户帐户时，不会自动为其分配 Microsoft 365 许可证，也无法访问 Microsoft 365 服务（如电子邮件）。 您必须先为其分配使用位置。 然后，单独或动态地通过组成员身份为这些用户帐户分配许可证。
>

下面是使用混合标识模型的两种类型的身份验证。

| 身份验证类型 | 说明 |
|:-------|:-----|
| 托管身份验证 | Azure AD 使用本地存储的密码哈希版本处理身份验证过程，或将凭据发送到本地软件代理，由本地 AD DS 进行身份验证。 <br> <br>  托管身份验证有两种类型：密码哈希同步 (PHS) 和 PTA (传递) 。 借助 PHS，Azure AD 本身执行身份验证。 借助 PTA，Azure AD 具有 AD DS 来执行身份验证。 |
| 联合身份验证 | Azure AD 将请求身份验证的客户端计算机重定向到其他标识提供程序。 |
|  |  |

请参阅 [选择正确的身份验证方法](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 了解更多信息。

## <a name="enforcing-strong-sign-ins"></a>强制执行强登录

若要提高用户登录的安全性，请使用下表中的特性和功能。

| 功能 | 说明 | 更多信息 | 许可要求 |
|:-------|:-----|:-----|:-----|:-----|
| Windows Hello 企业版 | 在 Windows 设备上签名时，将密码替换为强双因素身份验证。 这两个因素是一种与设备和生物识别或 PIN 相关联的新型用户凭据。 | [Windows Hello 企业版概述](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) | Microsoft 365 E3 或 E5 |
| Azure AD 密码保护 | 检测和阻止已知的弱密码及其变体，还可以阻止特定于您的组织的其他弱术语。 | [配置 Azure AD 密码保护](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | Microsoft 365 E3 或 E5 |
| 使用多重身份验证 (MFA) | MFA 要求用户登录除了用户帐户密码之外还需要进行其他验证，例如使用智能手机应用进行验证或发送到智能手机的短信。 有关 [用户](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) 如何设置 MFA 的说明，请参阅此视频。 | [适用于 Microsoft 365 企业版 MFA](../enterprise/microsoft-365-secure-sign-in.md#mfa) | Microsoft 365 E3 或 E5 |
| 标识和设备访问配置 | 由建议的先决条件功能及其设置以及条件访问、Intune 和 Azure AD Identity Protection 策略组成的设置和策略，这些策略确定是否应授予给定访问请求以及应在哪些条件下授予。  | [标识和设备访问配置](../security/office-365-security/microsoft-365-policies-configurations.md) | Microsoft 365 E3 或 E5 |
| Azure AD Identity Protection | 防止凭据泄露，攻击者确定用户帐户名和密码以访问组织的云服务和数据。 | [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) | Identity 为 & 威胁防护加载项的 Microsoft 365 E5 或 Microsoft 365 E3 |
|  |  |  |



## <a name="results-of-step-3"></a>步骤 3 的结果

对于 Microsoft 365 租户的标识，已确定：

- 要使用哪种标识模型。
- 如何强制实施强用户和设备访问。

下面是一个突出显示了新混合标识元素的租户示例。

![租户的混合标识示例](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

在此图中，租户具有：

- 使用 DirSync 服务器和 Azure AD Connect 与 Azure AD 租户同步的 AD DS 林。
- AD DS 用户帐户和 AD DS 林中其他对象的副本。
- 一组条件访问策略，用于基于用户帐户强制实施安全用户登录和访问。 

## <a name="ongoing-maintenance-for-identity"></a>持续维护标识

你可能需要持续：

- 添加或修改用户帐户和组。 对于仅云标识，可以使用 Azure AD 工具（如 Microsoft 365 管理中心或 PowerShell）维护基于云的用户和组。 对于混合标识，使用 AD DS 工具维护本地用户和组。
- 添加或修改标识和设备访问配置，以强制实施登录安全要求。

## <a name="next-step"></a>后续步骤

[![步骤 4.迁移本地 Office 服务器和数据](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)

继续 [迁移](tenant-management-migration.md) ，将本地 Office 服务器及其数据迁移到 Microsoft 365。
