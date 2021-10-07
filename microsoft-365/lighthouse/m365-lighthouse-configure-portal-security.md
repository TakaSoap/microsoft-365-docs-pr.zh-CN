---
title: 配置Microsoft 365 Lighthouse门户安全性
f1.keywords: NOCSH
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
description: 对于托管服务提供商 (MSP) 使用Microsoft 365 Lighthouse，了解如何配置门户安全性。
ms.openlocfilehash: fadff316b98b57960179214d3d895ecad6467a69
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152474"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>配置Microsoft 365 Lighthouse门户安全性

> [!NOTE]
> 本文中所述的功能在预览版中，可能会更改，并且仅对满足要求 [的合作伙伴可用](m365-lighthouse-requirements.md)。 如果你的组织没有Microsoft 365 Lighthouse，请参阅注册[Microsoft 365 Lighthouse。](m365-lighthouse-sign-up.md)

当 Managed Service Provider (MSP) 其租户具有委派访问权限时，保护客户数据的访问是网络安全的优先级。 Microsoft 365 Lighthouse具有必需和可选功能，可帮助你配置 Lighthouse 门户安全性。

## <a name="set-up-multifactor-authentication-mfa"></a>在 MFA (设置多重) 

如博客文章 [Pa$$word并不重要](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984)：

> "你的密码无关紧要，但 MFA 会这样做。 根据我们的研究，如果使用 MFA，你的帐户泄露的可能性将超过 99.9%。"

当用户首次访问 Lighthouse 时，如果用户的 Microsoft 365 帐户尚未配置 MFA，系统将提示他们设置 MFA。 在所需的 MFA 设置步骤完成之前，用户无法访问 Lighthouse。 若要了解有关身份验证方法的更多信息，请参阅[设置Microsoft 365登录进行多重身份验证](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。

## <a name="set-up-roles-to-manage-customer-tenants"></a>设置角色以管理客户租户

对 Lighthouse 中的客户租户数据和设置的访问权限仅限于云解决方案提供商云解决方案提供商计划云解决方案提供商计划中的管理员代理 (支持) 角色。

可以通过查看 [Azure AD](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) – 所有组页面上的安全组成员身份来检查合作伙伴租户中哪些用户具有管理员代理和技术支持代理角色。 若要了解如何向用户分配云解决方案提供商计划角色和其他权限，请参阅向用户分配 [角色和权限](/partner-center/permissions-overview)。 作为 MSP，如果尚未将访问权限委派给客户租户，请通过获取客户服务或订阅的权限一文了解如何 [获取权限](/partner-center/customers-revoke-admin-privileges)。

下表列出了不同的 Lighthouse 页面，以及查看和操作客户租户数据和管理员代理和技术支持代理角色设置所需的权限。<br><br>

| Lighthouse 页面 | 管理员代理权限 | 支持人员代理权限 |
|--|--|--|
| 主页 | <ul><li>查看全部</li></ul> | <ul><li>查看全部</li></ul> |
| 租户 | <ul><li>查看全部</li><li>更新客户联系人和网站</li><li>查看和应用部署计划</li></ul> | <ul><li>查看全部</li><li>更新客户联系人和网站</li><li>查看部署计划</li></ul> |
| 用户 | <ul><li>查看全部</li><li>重置密码</li><li>阻止登录</li><li>启用 MFA</li></ul> | <ul><li>查看全部</li><li>重置密码</li><li>阻止登录</li></ul> |
| 设备 | <ul><li>查看全部</li></ul> | <ul><li>查看全部</li></ul> |
| 威胁 | <ul><li>查看全部</li><li>运行快速扫描</li><li>运行完全扫描</li><li>重新启动设备</li><li>更新防病毒</li></ul> | <ul><li>查看全部</li></ul> |
| 基线 | <ul><li>查看全部</li></ul> | <ul><li>查看全部</li></ul> |
| 服务运行状况 | <ul><li>查看全部*</li></ul> | <ul><li>查看全部*</li></ul> |

> [!NOTE]
> 目前，若要执行表中标记为 * 的操作，用户还需要在合作伙伴租户中具有以下属性集的 Azure AD 角色 **：microsoft.office365.serviceHealth/allEntities/allTasks**。 有关 Azure AD 角色的列表，请参阅 [Azure AD 内置角色](/azure/active-directory/roles/permissions-reference)。

鉴于与管理员代理角色相关的广泛权限，我们建议在将合作伙伴租户用户指定为管理员代理而非支持代理[](/azure/active-directory/develop/secure-least-privileged-access)时遵循最小特权访问原则。 为此，一个方法就是将支持代理角色分配给所需的合作伙伴租户用户。 这样，他们可以查看客户数据和设置，但不能进行广泛更改。 然后，如果需要，使用 Azure AD Privileged Identity Management (PIM) 实时访问审批功能为用户提供时间范围的管理员代理角色。

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>设置 Azure AD Privileged Identity Management (PIM) 

通过使用 Azure AD 或 PIM Privileged Identity Management (，MSP 可以最大程度地减少有权访问信息或资源) 。 PIM 降低了恶意用户访问资源或授权用户无意中影响敏感资源的机会。 MSP 还可以授予用户实时特权访问资源，并监视指定用户使用其特权访问执行哪些操作。

> [!NOTE]
> 使用 Azure AD PIM 需要Azure AD Premium P2租户中的许可证。

以下步骤使用 Azure AD PIM 将合作伙伴租户用户提升为时间范围的管理员代理角色：

1. 创建可分配角色的组，如在角色分配组一文中所述[Azure Active Directory。](/azure/active-directory/roles/groups-create-eligible)

2. 转到 [Azure AD – 所有组](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) ，并添加新组作为管理员代理组的成员。

3. 设置新组的特权访问，如分配特权访问组的合格所有者和成员 [一文中所述](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)。

若要了解更多信息，请参阅[什么是Privileged Identity Management？](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="other-roles-and-permissions"></a>其他角色和权限

下表列出了合作伙伴租户角色及其关联权限。<br><br>

| 合作伙伴租户角色 | 合作伙伴租户内的权限 |
|--|--|
| 合作伙伴租户的全局管理员 | <ul><li>在"2013"中注册Microsoft 365 管理中心。</li><li>在首次运行体验期间接受合作伙伴合同修正。</li><li>在"租户"页上查看客户租户。\*</li><li>激活和停用租户。\*</li><li>更新客户联系人和网站。\*</li><li>创建、更新和删除标记。\*</li><li>分配和删除客户租户中的标记。\*</li></ul> |
| 至少具有一个合作伙伴租户的合作伙伴租户管理员<br> 分配了以下属性集的 Azure AD 角色：<br> **microsoft.office365.supportTickets/allEntities/allTasks**<br>  (有关 Azure AD 角色的列表，请参阅 [Azure AD 内置角色](/azure/active-directory/roles/permissions-reference).)  | <ul><li>创建 Lighthouse 服务请求。</li></ul> |

> [!NOTE]
> 目前，若要执行表中标记为 * 的操作，全局管理员必须担任管理员代理角色。

## <a name="related-content"></a>相关内容

[Microsoft 365 Lighthouse (](m365-lighthouse-overview.md)概述) \
[注册Microsoft 365 Lighthouse (](m365-lighthouse-sign-up.md)文章) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 