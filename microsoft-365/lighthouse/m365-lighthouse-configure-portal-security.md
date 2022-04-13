---
title: 配置Microsoft 365 Lighthouse门户安全性
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (使用Microsoft 365 Lighthouse) MSP，了解如何配置门户安全性。
ms.openlocfilehash: de93ebfff03241500bb1788fc282c4b2bb747ea2
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823556"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>配置Microsoft 365 Lighthouse门户安全性

当托管服务提供商 (MSP) 向其租户委派访问权限时，保护对客户数据的访问是网络安全的优先级。 Microsoft 365 Lighthouse同时提供必需功能和可选功能来帮助配置 Lighthouse 门户安全性。 必须设置具有多重身份验证的特定角色 (启用 MFA) 才能访问 Lighthouse。 可以选择性地设置Azure AD Privileged Identity Management (PIM) 和条件访问。

## <a name="set-up-multifactor-authentication-mfa"></a>设置多重身份验证 (MFA) 

如博客文章《 [你的 Pa$$word](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) 中所述并不重要：

> “你的密码并不重要，但 MFA 确实如此。 根据我们的研究，如果使用 MFA，你的帐户被泄露的可能性要低 99.9% 以上。

当用户首次访问 Lighthouse 时，如果尚未配置其Microsoft 365帐户，系统会提示他们设置 MFA。 在完成所需的 MFA 设置步骤之前，用户将无法访问 Lighthouse。 若要详细了解身份验证方法，请参阅[为多重身份验证设置Microsoft 365登录](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。

## <a name="set-up-role-based-access-control"></a>设置基于角色的访问控制

基于角色的访问控制 (RBAC) 根据用户角色授予对资源或信息的访问权限。 对 Lighthouse 中的客户租户数据和设置的访问仅限于来自 云解决方案提供商 (CSP) 计划的特定角色。 若要在 Lighthouse 中设置 RBAC 角色，建议使用粒度委派的管理员权限 (GDAP) 为用户实现精细分配。 租户仍需要委派的管理员权限 (DAP) 才能成功加入，但仅限 GDAP 的客户将很快能够加入，而无需依赖 DAP。 当客户的 DAP 和 GDAP 共存时，GDAP 权限优先。

若要设置 GDAP 关系，请参阅 [获取精细的管理员权限来管理客户的服务](/partner-center/gdap-obtain-admin-permissions-to-manage-customer)。 有关建议使用 Lighthouse 的角色的详细信息，请参阅[Microsoft 365 Lighthouse中的权限概述](m365-lighthouse-overview-of-permissions.md)。

MSP 技术人员还可以通过委派的管理员权限 (DAP) 使用管理员代理或 Helpdesk 代理角色访问 Lighthouse。

对于 Lighthouse (中的非客户租户相关操作，例如载入、客户停用/重新激活、管理标记、查看日志) ，MSP 技术人员必须在合作伙伴租户中具有分配的角色。 有关合作伙伴租户角色的更多详细信息，请参阅[Microsoft 365 Lighthouse中的权限概述](m365-lighthouse-overview-of-permissions.md)。

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>设置Azure AD Privileged Identity Management (PIM) 

MSP 可以使用 PIM 最大程度地减少具有高特权角色访问权限来保护信息或资源的人数。 PIM 减少了恶意用户获取资源访问权限或授权用户无意中影响敏感资源的可能性。 MSP 还可以向用户授予实时高特权角色来访问资源、进行广泛更改，以及监视指定用户使用其特权访问执行的操作。

> [!NOTE]
> 使用Azure AD PIM 需要合作伙伴租户中的Azure AD Premium P2许可证。

以下步骤使用 PIM 将合作伙伴租户用户提升为时间范围更高的特权角色：

1. 如“[创建组以在Azure Active Directory中分配角色”一文中](/azure/active-directory/roles/groups-create-eligible)所述，创建可分配角色的组。

2. 转到[Azure AD – 所有组](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups)，将新组添加为高特权角色的安全组的成员 (例如，DAP 的管理员代理安全组或 GDAP 角色的类似相应安全组) 。

3. 设置对新组的特权访问，如为 [特权访问组分配符合条件的所有者和成员](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)一文中所述。

若要了解有关 PIM 的详细信息，请参阅[Privileged Identity Management是什么？](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="set-up-risk-based-azure-ad-conditional-access"></a>设置基于风险的Azure AD条件访问

MSP 可以使用基于风险的条件访问来确保其员工使用 MFA 证明其身份，并在检测到存在风险的用户 (凭据泄露或Azure AD威胁情报) 时更改其密码。 当检测到有风险的登录时，用户还必须从熟悉的位置或已注册的设备登录。 其他危险行为包括：从恶意或匿名 IP 地址或非典型或不可能的旅行位置登录、使用异常令牌、使用密码喷射中的密码或表现出其他异常登录行为。 MSP 还可以选择在登录时阻止访问，具体取决于用户的风险级别。 若要了解有关风险的详细信息， [请参阅什么是风险？](/azure/active-directory/identity-protection/concept-identity-protection-risks)

> [!NOTE]
> 条件访问需要合作伙伴租户中的Azure AD Premium P2许可证。 若要设置条件访问，请参阅[配置Azure Active Directory条件访问](/appcenter/general/configuring-aad-conditional-access)。

## <a name="related-content"></a>相关内容

[密码重置权](/azure/active-directory/roles/permissions-reference#password-reset-permissions) 限 (文章) \
[Microsoft 365 Lighthouse (](m365-lighthouse-requirements.md)文章) \ 的要求
[Microsoft 365 Lighthouse (](m365-lighthouse-overview.md)文章) 概述\
[注册Microsoft 365 Lighthouse (](m365-lighthouse-sign-up.md)文章) \
[Microsoft 365 Lighthouse常见问题解](m365-lighthouse-faq.yml)答 (文章) 