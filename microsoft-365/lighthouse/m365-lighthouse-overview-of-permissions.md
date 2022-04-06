---
title: 管理中的权限Microsoft 365 Lighthouse
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
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: 有关托管服务提供商 (MSP) 使用Microsoft 365 Lighthouse，请详细了解 Lighthouse 权限要求。
ms.openlocfilehash: 25f38b8cbc0c6815139fd6afd3616cfaa7df48e1
ms.sourcegitcommit: 33bc25167812b31c51cf096c728e3a5854e94f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2022
ms.locfileid: "64595403"
---
# <a name="overview-of-permissions-in-microsoft-365-lighthouse"></a>管理中的权限Microsoft 365 Lighthouse

Managed Service Providers (MSP) 客户租户的委派访问权限Microsoft 365 Lighthouse。 通过 GDAP (委派管理) 通过内置角色提供客户访问权限，为 MSP 提供了高级控制[Azure Active Directory (Azure AD) 灵活性](/azure/active-directory/roles/permissions-reference)。 通过 GDAP 将最低特权角色按任务分配给 MSP 技术人员可降低 MSP 和客户的安全风险。 有关按任务分配最小特权角色的信息，请参阅最低特权角色 [-](/partner-center/gdap-least-privileged-roles-by-task) 合作伙伴中心和任务最低特权[Azure Active Directory](/azure/active-directory/roles/delegate-by-task)。 有关设置与客户租户的 GDAP 关系的信息，请参阅获取管理客户服务的细化管理员 [权限 - 合作伙伴中心。](/partner-center/gdap-obtain-admin-permissions-to-manage-customer)

我们建议根据每个组代表客户执行的任务将角色分配给 MSP 技术人员组。 例如，技术支持技术人员可能只需读取客户租户数据或重置用户密码。 相反，升级工程师可能需要采取更多纠正措施来更新客户租户安全设置。 最佳做法是分配完成任务所需的最小权限角色，以便客户和合作伙伴数据保持安全。 如果需要，Privileged Identity Management (PIM) 启用对全局管理员角色的时作用域访问。 向过多用户提供全局访问是一种安全风险，我们建议尽可能限制它。 若要详细了解如何启用 PIM，请参阅设置 [PIM Azure AD PIM。](m365-lighthouse-configure-portal-security.md#set-up-azure-ad-privileged-identity-management-pim)

下一节中的表介绍了哪些 GDAP 角色授予读取客户数据的权限，以及对位于 Lighthouse 的客户租户采取操作的权限。 有关 [管理](#permissions-in-the-partner-tenant) Lighthouse 实体所需的其他角色，请参阅本文中的合作伙伴租户中的权限 (例如，标签和 Lighthouse 服务请求) 。

> [!NOTE]
>GDAP 目前处于公共[](/partner-center/announcements/2022-february#6) (预览版) ，以允许合作伙伴在 GDAP 公开发布之前分配具体权限。 如果您在 [Lighthouse](m365-lighthouse-known-issues.md) 中访问或执行操作时遇到问题，请检查已知问题。

## <a name="example-msp-service-tiers-and-recommended-gdap-roles"></a>示例 MSP 服务层和推荐的 GDAP 角色

下表列出了一些示例 MSP 服务层的建议 GDAP 角色，以及这些角色可以在不同的 Lighthouse 页面上执行的操作。

|| AccountManagers&nbsp;| ServiceDeskTechnician&nbsp;&nbsp; |SystemAdministrators&nbsp; | EscalationEngineers&nbsp;|
|---|---|---|---|---|
| **建议的 GDAP 角色** |<ul><li>帮助台管理员</li></ul> |<ul><li>安全信息读取者<br>+</li><li>帮助台管理员</li></ul> |<ul><li>全局读取者<br>+</li><li>用户管理员<br>+</li><li>身份验证管理员</li></ul> |<ul><li>全局读取者<br>+</li><li>用户管理员<br>+</li><li>Intune管理员<br>+</li><li>安全管理员</li></ul>|
|**Lighthousepageallowedactions&nbsp;&nbsp;+&nbsp;&nbsp;**  |
| **主页**  | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | 
| **Tenants**     | <ul><li>查看租户列表</li><li>更新客户联系人和网站</li><li>查看部署计划</li></ul>  | <ul><li>查看租户列表</li><li>更新客户联系人和网站</li><li>查看部署计划</li></ul>   |  <ul><li>查看租户列表</li><li>更新客户联系人和网站</li><li>查看部署计划</li><li>查看Microsoft 365服务使用情况</li></ul> | <ul><li>查看租户列表</li><li>更新客户联系人和网站</li><li>查看部署计划</li><li>查看Microsoft 365服务使用情况</li></ul>  |
| **用户**   | <ul><li>查看租户级别 (特定于用户的数据) 级别</li><li>跨租户搜索用户帐户</li><li>重置非管理员的密码*</li></ul>  | <ul><li>查看所有特定于用户的数据</li><li>跨租户搜索用户帐户</li><li>重置非管理员的密码*</li></ul>|  <ul><li>查看所有特定于用户的数据</li><li>跨租户搜索用户帐户</li><li>重置非管理员的密码*</i><li>阻止登录</li></ul>  | <ul><li>查看所有特定于用户的数据</li><li>跨租户搜索用户帐户</li><li>重置非管理员的密码*</li><li>阻止登录</li><li>确认受到威胁的用户</li><li>消除用户风险</li></ul> |
| **Devices**    | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li><li>同步设备</li><li>重启设备</li><li>收集诊断</li></ul>|
| **威胁管理**  | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li><li>运行完全扫描</li><li>运行快速扫描</li><li>更新防病毒保护</li><li>重新启动设备</li></ul>|
| **基线**    | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul>  | <ul><li>查看所有数据</li></ul> |
| **Windows 365** | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> |
| **服务运行状况****|  
|**审核日志****|

* [有关列出为客户租户](/azure/active-directory/roles/permissions-reference#password-reset-permissions) 管理员重置密码所需的角色的表，请参阅密码重置权限。

**查看服务运行状况和审核日志需要其他角色和权限。 有关详细信息，请参阅 [合作伙伴租户中的权限](#permissions-in-the-partner-tenant)。

> [!NOTE]
> 如果在 Lighthouse 收到一条消息，指出您无权查看或编辑信息，则分配给您的角色没有执行此操作的适当权限。 你需要联系合作伙伴租户中的管理员，该管理员可以针对你尝试执行的操作分配适当的角色。

## <a name="delegated-admin-privileges-dap-in-lighthouse"></a>Lighthouse 的 DAP (委派) 权限

GDAP 最终将取代 DAP 作为配置客户租户委派访问权限的主要方法。 但是，如果尚未设置 GDAP，MSP 技术人员仍可以通过使用通过 DAP 授予的支持人员代理或管理员代理角色访问 Lighthouse。 对于 GDAP 和 DAP 共存的客户，通过 GDAP 授予 MSP 技术人员的角色优先。 有关 GDAP 或 DAP 弃用状态的信息，请参阅 [GDAP](/partner-center/gdap-faq) 常见问题或合作伙伴中心 [公告了解日期](/partner-center/announcements/2022-march#15) 和日程表。

对于具有 DAP 且没有 GDAP 的客户，管理员代理角色授予查看所有租户数据的权限，以及是否对 Lighthouse (请参阅下文，了解还需要合作伙伴租户) 中的角色的其他操作。

支持人员代理角色授予查看所有租户数据的权限，以及执行 Lighthouse 中的有限操作，例如重置用户密码、阻止用户登录和更新客户联系信息和网站。

鉴于授予具有 DAP 角色的合作伙伴用户的广泛权限，我们建议尽快采用 GDAP。 

## <a name="permissions-in-the-partner-tenant"></a>合作伙伴租户中的权限

对于 Lighthouse 中的某些操作，需要合作伙伴租户中的角色分配。 下表列出了合作伙伴租户角色及其关联权限。

| 合作伙伴租户角色 | Permissions |
|--|--|
| 合作伙伴租户的全局管理员 | <ul><li>在"百年一号"中注册Microsoft 365 管理中心。</li><li>在首次运行体验期间接受合作伙伴合同修正。</li><li>激活和停用租户。</li><li>创建、更新和删除标记。</li><li>分配和删除客户租户中的标记。</li></ul> |
| 分配了至少一个角色Azure AD以下属性集的合作伙伴租户成员：<br>**microsoft.office365.supportTickets/allEntities/allTasks**<br> (有关角色Azure AD列表，请参阅Azure AD[角色](/azure/active-directory/roles/permissions-reference)。)  | 创建 Lighthouse 服务请求。 |
| 满足以下两 *个要求的合作伙伴* 租户成员： <ul><li>至少分配有Azure AD一个角色，并具有以下属性集：<br>**microsoft.office365.serviceHealth/allEntities/allTasks**<br> (有关角色Azure AD列表，请参阅Azure AD[角色](/azure/active-directory/roles/permissions-reference)。) </li><li>至少分配有一个 DAP 委派角色 (管理员代理或支持) </li></ul> | 查看服务运行状况信息。 |

## <a name="related-content"></a>相关内容

[本文Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (要求)   
[DAP (委派管理) 常见问题](/partner-center/dap-faq) (文章)   
[向用户分配角色和权限](/partner-center/permissions-overview) (本文)   
[本文Microsoft 365 Lighthouse](m365-lighthouse-overview.md) (概述)   
[注册Microsoft 365 Lighthouse (](m365-lighthouse-sign-up.md)注册)   
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 
