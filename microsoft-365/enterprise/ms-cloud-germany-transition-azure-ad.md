---
title: 有关Azure Active Directory德国 Microsoft 云的迁移的其他详细信息
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：从德国 Microsoft 云Azure Active Directory德国 microsoft 云 (迁移到新的德国数据中心) Office 365服务时的其他详细信息。
ms.openlocfilehash: 88a151b61a93b4b65e16bbd100a126d44282e513
ms.sourcegitcommit: a84a7a9bda2b616a24af03b89a84f5e75ebfc0c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2021
ms.locfileid: "53578441"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>有关Azure Active Directory德国 Microsoft 云的迁移的其他详细信息

若要完成从 Azure 德国云到 Azure 公共云的迁移，我们建议在 OpenID 连接 (OIDC) 终结点开始报告商业云终结点时，将应用程序的身份验证终结点、Azure Active Directory (Azure AD) Graph 和 MS Graph 终结点更新为商业云终结点。 `https://login.microsoftonline.com/<TenantIdOrDomain>/.well-known/openid-configuration` 
 
**何时应进行此更改？**

当你的租户完成从德国云到商业云的迁移Office Azure/Office门户中，你将收到一条通知。 在收到此通知后 30 天内完成这些更新，以便应用继续适用于从 Azure Germany 云迁移到 Azure 公共云的租户。
 
更新登录权限有三个先决条件：

 - 租户的 OIDC 发现终结点 `https://login.microsoftonline.com/<TenantIdOrDomain>/.well-known/openid-configuration` 返回 Azure AD 公共云终结点。

 - 如果为租户设置了联合身份验证，Active Directory 联合身份验证服务 (AD FS) 更新为与 Azure AD Public 同步。 你可以按照说明更新 Azure AD 连接进行此更改的设置。

 - 应用程序使用的资源应用程序（如果有）将修改为接受由 Azure AD Germany 和 Azure AD Public 签名的令牌。
 
**哪种类型的应用程序？**

应用程序可以是以下任一应用程序：

- [SPA 应用程序 (单页) ](/azure/active-directory/develop/scenario-spa-overview)
- [登录用户的 Web 应用](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [调用 Web API 的 Web 应用](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [受保护的 Web API](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [调用 Web API 的 Web API](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [桌面应用](/azure/active-directory/develop/scenario-desktop-overview)
- [守护程序应用](/azure/active-directory/develop/scenario-daemon-overview)
- [移动应用](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> 当应用程序切换到使用 作为颁发机构时，此新颁发机构 `login.microsoftonline.com` 将签署令牌。 如果你托管了其他应用程序调用的任何资源应用程序，则需要允许令牌验证。 这意味着你的应用需要允许由 Azure AD Germany 和 Azure AD 公共云签名的令牌。 在调用你的服务的所有客户端应用程序完全迁移到 Azure AD 公共云之前，需要此令牌验证。 迁移后，你的资源应用程序只需接受 Azure AD 公共云签名的令牌。

**我需要更新哪些内容？**

1. 如果你要在德国 Azure 中托管用于对 Azure 德国或 Office 365用户进行身份验证的应用程序，请确保在身份验证上下文中用作 `https://login.microsoftonline.com` 颁发机构。

    - 请参阅 Azure AD 身份验证上下文。
    - 这既适用于对应用程序的身份验证，也适用于应用程序可能调用 (的任何 API 的身份验证，即 Microsoft Graph、Azure AD Graph、Azure 资源管理器) 。

2. 将 Azure AD Graph 终结点更新为 `https://graph.windows.net` 。

3. 将 Microsoft Graph 终结点更新为 `https://graph.microsoft.com` 。

4. 将任何德国云终结点 (，如 Exchange Online 和 SharePoint Online) ，应用程序使用它们作为公共云终结点。

5. 更新要更新的环境 `AzurePublic` (，) `AzureGermany` 管理工具和脚本中更新这些参数：

    - [Azure PowerShell](/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline) ](/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD) ](/powershell/azure/active-directory/install-adv2)
    - [Azure CLI](/cli/azure/install-azure-cli)
 
**我发布的应用程序呢？**

如果发布可供租户外部用户使用的应用程序，可能需要更改应用程序注册以确保连续性。 使用应用程序的其他租户可能在与租户不同的时间移动。 若要确保用户不会丢失对应用程序的访问权限，你将需要同意将应用从 Azure 德国同步到 Azure 公共。

**在迁移期间添加新的多租户应用程序如何？**

如果要使用由另一个组织发布的新应用程序 (多租户应用程序) 你将在迁移过程（第 2 阶段至第 9 阶段）期间 (限制你添加该应用程序) 。  当你的组织完成第 9 阶段并完全转换到 Azure 公共实例时，你可以执行此任务。

## <a name="additional-considerations"></a>其他注意事项

下面是 Azure AD 的一些其他注意事项：

- 对于联合身份验证：

  - 在租户转换过程中，不得创建、升级或降级联合域。 在租户完全完成迁移 (Azure AD 服务) ，可以恢复管理联盟域。

  - 如果对 Active Directory 联合身份验证服务 (AD FS) 使用联合身份验证，则不应对用于迁移期间本地 Active Directory 域服务 (AD DS) 的所有身份验证的颁发者 URI 进行更改。 更改颁发者 URI 将导致域中用户的身份验证失败。 颁发者 URI 可以直接在 AD FS 中更改，或在将域从托管域转换为联盟域时更改，反之亦然。 Microsoft 建议客户不要在要迁移的 Azure AD 租户中添加、删除或转换联合域。 完全完成迁移后，可更改颁发者 URI。

- 对于网络：

  - 创建以 IPv6 命名的网络在 Azure 门户中不起作用 `http://portal.microsoftazure.de/` 。 使用 Azure 门户 ，创建 `https://portal.azure.com` 以 IPv6 命名的网络。
 
   - 无法从 Microsoft 云德国门户为 Azure 多重身份验证创建受信任的 IP 地址 (MFA) 服务设置。 使用 Azure AD 门户创建Office 365 Azure MFA 受信任 IP 地址范围。


- 对于条件访问： 

  - 在最终完成[Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized)迁移阶段完成后，Office 365服务 (以下授予控制的条件访问策略) ：

    - 需要兼容设备
    - 需要批准的应用
    - 需要应用保护策略
    
  - 条件访问策略接口会针对为租户启用安全默认值（即使已禁用）以及租户已存在的条件访问策略，提供一个假警告。 应忽略警告或使用 Office 365门户管理条件访问策略。 

- 租户迁移完成后，仅针对全球终结点支持 Intune 方案，包括所有 Office 工作负载迁移。

- 对 MFA 请求使用移动应用通知方法的 Microsoft 云德国用户会看到用户的 ObjectId (GUID) 而不是 Microsoft Authenticator 应用中的用户主体名称 (UPN) 。 完成 Azure AD 租户的迁移并托管在 Office 365 服务中后，新的 Microsoft Authenticator 激活将显示用户的 UPN。 现有Microsoft Authenticator帐户将继续显示用户 ObjectId，但它们将继续用于移动应用通知。 

- 对于在 2019 年 10 月 22 日之后创建的租户，当租户迁移到 Office 365 服务时，可能会为租户自动启用安全默认值。 租户管理员可以选择保持启用安全默认值并注册 MFA，也可以禁用该功能。 有关详细信息，请参阅 [禁用安全默认值](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)。 

  > [!NOTE]
  > 迁移期间未自动启用的组织将来可能仍可以自动注册，因为启用安全默认值的功能在 Office 365 服务中推出。 选择显式禁用或启用安全默认值的管理员可以通过更新"属性"下的"Azure Active Directory >**来这样做**。 在管理员显式启用该功能后，它将不会自动启用。

- 租户迁移后，将在 Office 365 Germany 门户和 Office 365 门户中显示有关 Azure AD 连接 版本的警告。 如果迁移完成后版本警告不再显示警告，可以忽略此警告。 如果在迁移之前或之后在任一门户中出现警告，则必须连接 Azure AD 帐户。 警告消息显示："我们检测到你正在使用过时的目录同步工具。 我们建议你转到 Microsoft 下载中心，获取最新版 Azure AD 连接。"

## <a name="more-information"></a>更多信息

入门：

- [从德国 Microsoft 云迁移到Office 365新的德国数据中心区域提供服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移期间客户体验](ms-cloud-germany-transition-experience.md)

在转换过程中移动：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他前期工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 迁移计划信息](/power-bi/admin/service-admin-migrate-data-germany)
- [开始 Microsoft Teams 升级](/microsoftteams/upgrade-start-here)
