---
title: Microsoft 365 Lighthouse中的权限概述
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
description: 对于使用 Microsoft 365 Lighthouse 的托管服务提供商 (MSP) ，请详细了解 Lighthouse 权限要求。
ms.openlocfilehash: 1ab22fa48bb04673beb8f2b91cbbbaba2cd97804
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64822750"
---
# <a name="overview-of-permissions-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse中的权限概述

托管服务提供商需要委派对客户租户的访问权限， (MSP) 才能使用Microsoft 365 Lighthouse。 粒度委派的管理员权限 (GDAP) 通过[Azure Active Directory (Azure AD) 内置角色](/azure/active-directory/roles/permissions-reference)为客户提供访问权限，从而为 MSP 提供高度的控制和灵活性。 通过 GDAP 向 MSP 技术人员分配任务中特权最低的角色可降低 MSP 和客户的安全风险。 有关任务中最低特权角色的详细信息，请参阅最低[特权角色 - 合作伙伴中心](/partner-center/gdap-least-privileged-roles-by-task)和[最小特权角色（按任务在Azure Active Directory中）](/azure/active-directory/roles/delegate-by-task)。 有关设置与客户租户的 GDAP 关系的详细信息，请参阅 [获取管理客户服务的精细管理员权限 - 合作伙伴中心。](/partner-center/gdap-obtain-admin-permissions-to-manage-customer)

建议根据每个组代表客户执行的任务，将角色分配给 MSP 技术人员组。 例如，服务台技术人员可能需要读取客户租户数据或重置用户密码。 相比之下，升级工程师可能需要采取更多纠正措施来更新客户租户安全设置。 最佳做法是分配完成任务所需的最不宽松的角色，以便客户和合作伙伴数据保持安全。 如果需要，建议使用 Privileged Identity Management (PIM) 启用对全局管理员角色的时间范围访问。 为太多用户提供全局访问权限是一种安全风险，我们建议尽量限制它。 有关如何启用 PIM 的详细信息，请参阅[设置Azure AD PIM。](m365-lighthouse-configure-portal-security.md#set-up-azure-ad-privileged-identity-management-pim)

下一部分中的表描述了哪些 GDAP 角色授予读取客户数据和对 Lighthouse 中的客户租户采取行动的权限。 请参阅本文 [中的合作伙伴租户中的权限](#permissions-in-the-partner-tenant) ，了解管理 Lighthouse 实体所需的其他角色 (例如，标记和 Lighthouse 服务请求) 。

> [!NOTE]
>GDAP 目前处于 [技术预览](/partner-center/announcements/2022-february#6) (公共预览版) 允许合作伙伴在 GDAP 正式发布之前分配精细权限。 如果在 Lighthouse 中访问或执行操作时遇到问题，请检查 [已知问题](m365-lighthouse-known-issues.md) 。

## <a name="example-msp-service-tiers-recommended-gdap-roles-and-permissions"></a>示例 MSP 服务层级、建议的 GDAP 角色和权限

下表列出了某些示例 MSP 服务层级的建议 GDAP 角色。 

|| 帐户管理器| 服务台技术人员 | 系统管理员 | 升级工程师|
|---|---|---|---|---|
| **建议的 GDAP 角色** |<ul><li>帮助台管理员</li></ul> |<ul><li>安全信息读取者<br>+</li><li>帮助台管理员</li></ul> |<ul><li>全局读取者<br>+</li><li>用户管理员<br>+</li><li>身份验证管理员</li></ul> |<ul><li>全局读取者<br>+</li><li>用户管理员<br>+</li><li>Intune管理员<br>+</li><li>安全管理员</li></ul>|

下表列出了示例 MSP 服务层可在不同的 Lighthouse 页面上执行的操作，这些操作由其分配的 GDAP 角色确定 (在上表) 中指示。

| 灯塔页 | 帐户管理器允许的操作| 服务台技术人员允许的操作 |系统管理员允许的操作 | 升级工程师允许的操作|
|---|---|---|---|---|
| 家庭版  | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | 
| 租户     | <ul><li>查看租户列表</li><li>更新客户联系人和网站</li><li>查看部署计划</li></ul>  | <ul><li>查看租户列表</li><li>更新客户联系人和网站</li><li>查看部署计划</li></ul>   |  <ul><li>查看租户列表</li><li>更新客户联系人和网站</li><li>查看部署计划</li><li>查看Microsoft 365服务使用情况</li></ul> | <ul><li>查看租户列表</li><li>更新客户联系人和网站</li><li>查看部署计划</li><li>查看Microsoft 365服务使用情况</li></ul>  |
| 用户   | <ul><li>查看租户级别 (非用户特定) 数据</li><li>跨租户搜索用户帐户</li><li>重置非管理员密码*</li></ul>  | <ul><li>查看所有用户特定的数据</li><li>跨租户搜索用户帐户</li><li>重置非管理员密码*</li></ul>|  <ul><li>查看所有用户特定的数据</li><li>跨租户搜索用户帐户</li><li>重置非管理员密码*</i><li>阻止登录</li></ul>  | <ul><li>查看所有用户特定的数据</li><li>跨租户搜索用户帐户</li><li>重置非管理员密码*</li><li>阻止登录</li><li>确认遭到入侵的用户</li><li>消除用户的风险</li></ul> |
| 设备    | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li><li>同步设备</li><li>重启设备</li><li>收集诊断</li></ul>|
| 威胁管理  | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li><li>运行完全扫描</li><li>运行快速扫描</li><li>更新防病毒保护</li><li>重新启动设备</li></ul>|
| 基线    | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul>  | <ul><li>查看所有数据</li></ul> |
| Windows 365 | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> | <ul><li>查看所有数据</li></ul> |
| 服务运行状况**| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A |
| 审核日志**| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;N/A |

*查看表 [的密码重置权限](/azure/active-directory/roles/permissions-reference#password-reset-permissions) ，该表列出了重置客户租户管理员密码所需的角色。

**查看服务运行状况和审核日志需要不同的角色和权限。 有关详细信息，请参阅 [合作伙伴租户中的权限](#permissions-in-the-partner-tenant)。

> [!NOTE]
> 如果在 Lighthouse 中收到一条消息，指出您没有查看或编辑信息的权限，则会为你分配一个没有相应权限来执行操作的角色。 你需要联系合作伙伴租户中的管理员，该管理员可以为你尝试执行的操作分配适当的角色。

## <a name="delegated-admin-privileges-dap-in-lighthouse"></a>Lighthouse 中的委派管理员权限 (DAP) 

GDAP 最终将将 DAP 替换为为客户租户配置委派访问权限的主要方法。 但是，如果尚未设置 GDAP，MSP 技术人员仍可使用通过 DAP 授予的 Helpdesk 代理或管理员代理角色访问 Lighthouse。 对于 GDAP 和 DAP 共存的客户，通过 GDAP 授予 MSP 技术人员的角色优先。 有关 GDAP 或 DAP 弃用的详细信息，请参阅 [GDAP 常见问题解答](/partner-center/gdap-faq) 或有关日期和时间线 [的合作伙伴中心公告](/partner-center/announcements/2022-march#15) 。

对于具有 DAP 且没有 GDAP 的客户，管理员代理角色授予查看所有租户数据的权限，并在 Lighthouse 中执行任何操作 (对于还需要在合作伙伴租户) 中发挥作用的其他操作，请参阅下文。

Helpdesk 代理角色授予在 Lighthouse 中查看所有租户数据并采取有限操作的权限，例如重置用户密码、阻止用户登录以及更新客户联系信息和网站。

鉴于授予具有 DAP 角色的合作伙伴用户的广泛权限，建议尽快采用 GDAP。 

## <a name="permissions-in-the-partner-tenant"></a>合作伙伴租户中的权限

对于 Lighthouse 中的某些操作，需要在合作伙伴租户中分配角色。 下表列出了合作伙伴租户角色及其关联权限。

| 合作伙伴租户角色 | 权限 |
|--|--|
| 合作伙伴租户的全局管理员 | <ul><li>在Microsoft 365 管理中心中注册 Lighthouse。</li><li>在首次运行体验期间接受合作伙伴合同修订。</li><li>激活和停用租户。</li><li>创建、更新和删除标记。</li><li>从客户租户中分配和删除标记。</li></ul> |
| 使用以下属性集分配了至少一个Azure AD角色的合作伙伴租户成员：<br>**microsoft.office365.supportTickets/allEntities/allTasks**<br> (有关Azure AD角色的完整列表，请[参阅Azure AD内置角色](/azure/active-directory/roles/permissions-reference)。)  | 创建 Lighthouse 服务请求。 |
| 满足以下 *两* 项要求的合作伙伴租户成员： <ul><li>具有以下属性集至少分配了一个Azure AD角色：<br>**microsoft.office365.serviceHealth/allEntities/allTasks**<br> (有关Azure AD角色的完整列表，请[参阅Azure AD内置角色](/azure/active-directory/roles/permissions-reference)。) </li><li>至少有一个 DAP 委派角色分配 (管理员代理或 Helpdesk 代理) </li></ul> | 查看服务运行状况信息。 |

## <a name="related-content"></a>相关内容

[文章) ](m365-lighthouse-requirements.md) Microsoft 365 Lighthouse (要求  
[DAP) 常见问题解答 (文章 (委派的管理权](/partner-center/dap-faq) 限)   
[将角色和权限分配给用户](/partner-center/permissions-overview) (文章)   
[Microsoft 365 Lighthouse (](m365-lighthouse-overview.md)文章概述)   
[注册Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md) (文章)   
[Microsoft 365 Lighthouse常见问题解](m365-lighthouse-faq.yml)答 (文章) 
