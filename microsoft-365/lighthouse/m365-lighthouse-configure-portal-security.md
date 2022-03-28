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
description: 对于托管服务提供商 (使用) 托管服务提供商Microsoft 365 Lighthouse，了解如何配置门户安全性。
ms.openlocfilehash: dd99330d520b409a93cfd5d1ca777c17b9ef4373
ms.sourcegitcommit: 9c8eca862a2f0fdca7a66c641e382e37fcaefa10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2022
ms.locfileid: "63775931"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>配置Microsoft 365 Lighthouse门户安全性

当 Managed Service Provider (MSP) 其租户具有委派访问权限时，保护客户数据的访问是网络安全的优先级。 Microsoft 365 Lighthouse具有必需和可选功能，可帮助你配置 Lighthouse 门户安全性。 你必须使用启用了 MFA 的多重 (设置) 角色，然后才能访问 Lighthouse。 可以选择设置 PIM Azure AD Privileged Identity Management (和) 访问。

## <a name="set-up-multifactor-authentication-mfa"></a>设置 MFA (多重) 

如博客文章 Pa [$$word并不重要](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)：

> "你的密码无关紧要，但 MFA 会这样做。 根据我们的研究，如果使用 MFA，你的帐户泄露的可能性将超过 99.9%。"

当用户首次访问 Lighthouse 时，如果用户的 Microsoft 365 帐户尚未配置 MFA，系统将提示他们设置 MFA。 在所需的 MFA 设置步骤完成之前，用户无法访问 Lighthouse。 若要了解有关身份验证方法的更多信息，请参阅[设置Microsoft 365登录进行多重身份验证](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。

## <a name="set-up-role-based-access-control"></a>设置基于角色的访问控制

基于角色的访问控制 (RBAC) 基于用户角色授予对资源或信息的访问权限。 对 Lighthouse 中的客户租户数据和设置的访问权限仅限于云解决方案提供商计划云解决方案提供商 (特定) 角色。 若要在 Lighthouse 中设置 RBAC 角色，我们建议使用 GDAP (委派管理员) 为用户实现精细分配。 租户仍 (DAP) 委派管理员权限才能成功载入，但仅 GDAP 客户将很快能够在不依赖 DAP 的情况下载入。 当 DAP 和 GDAP 为客户共存时，GDAP 权限优先。 

若要开始使用 GDAP，请参阅 [设置角色以管理客户租户](m365-lighthouse-set-up-roles.md)。

MSP 技术人员还可通过使用管理员代理或支持人员代理角色通过 DAP (访问) 。

对于 Lighthouse (中的非客户租户相关操作，例如载入、客户停用/重新激活、管理标记、查看日志) ，MSP 技术人员必须在合作伙伴租户中分配有角色。 上一篇文章链接详细介绍了在 Lighthouse 中的角色及其权限。

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>设置Azure AD Privileged Identity Management (PIM) 

MSP 可以最大程度地减少使用 PIM 对保护信息或资源具有高特权角色访问权限的用户数量。 PIM 降低了恶意用户访问资源或授权用户无意中影响敏感资源的机会。 MSP 还可以授予用户实时高特权角色以访问资源、进行广泛更改以及监视指定用户使用其特权访问执行哪些操作。 

> [!NOTE]
> 使用Azure AD PIM 需要Azure AD Premium P2租户中的许可证。

以下步骤使用 PIM 将合作伙伴租户用户提升为时间范围的更高特权角色：

1. 创建角色可分配组，如创建组[以](/azure/active-directory/roles/groups-create-eligible)在角色分配Azure Active Directory。

2. 转到["Azure AD –](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) 所有组"，将新组添加为高特权角色的安全组的成员 (例如，DAP 的管理员代理安全组或 GDAP 角色安全组的类似) 。

3. 设置新组的特权访问，如分配特权访问组的合格所有者和成员 [一文中所述](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)。

若要了解有关 PIM 的更多信息，请参阅[什么是Privileged Identity Management？](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="set-up-risk-based-azure-ad-conditional-access"></a>设置基于风险Azure AD条件访问

MSP 可以使用基于风险的条件访问，以确保其员工成员通过使用 MFA 和更改密码来证明其身份，当被检测为凭据泄露的风险用户 (或按 Azure AD 威胁情报) 。 当检测到存在风险登录时，用户还必须从熟悉的位置或注册的设备登录。 其他有风险的行为包括从恶意或匿名 IP 地址或者非典型或不可能的旅行位置登录、使用异常令牌、使用密码来自密码的密码，或者呈现其他异常登录行为。 根据用户的风险级别，MSP 还可以选择在登录时阻止访问。 若要详细了解风险，请参阅 [什么是风险？](/azure/active-directory/identity-protection/concept-identity-protection-risks) 

> [!NOTE]
> 条件访问需要Azure AD Premium P2租户中的许可证。 若要设置条件访问，请参阅 [Configuring Azure Active Directory Conditional Access](/appcenter/general/configuring-aad-conditional-access)。

## <a name="related-content"></a>相关内容

[密码重置权限](/azure/active-directory/roles/permissions-reference#password-reset-permissions) (文章) \
[本文Microsoft 365 Lighthouse (](m365-lighthouse-requirements.md)的要求) \
[Microsoft 365 Lighthouse (](m365-lighthouse-overview.md)概述) \
[注册Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (文章) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 