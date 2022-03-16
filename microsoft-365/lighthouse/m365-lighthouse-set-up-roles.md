---
title: 设置角色以管理客户租户
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
description: 对于托管服务提供商 (MSP) 使用 Microsoft 365 Lighthouse，了解如何设置角色以管理客户租户。
ms.openlocfilehash: 948e6909f0fc8d743c84662de6c8a2d9c0bc88e3
ms.sourcegitcommit: a216617d6ff27fe7d3089a047fbeaac5d72fd25c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "63512236"
---
# <a name="set-up-roles-to-manage-customer-tenants"></a>设置角色以管理客户租户

托管服务提供商 (MSP) 可能会通过配置合作伙伴中心中的粒度委派管理员权限 (GDAP) ，在 Microsoft 365 Lighthouse 中启用客户租户的细化和时间访问权限。 GDAP 通过内置角色提供客户访问，为 MSP [Azure Active Directory (Azure AD) 高级控制和灵活性](/azure/active-directory/roles/permissions-reference)。 通过 GDAP 将最低特权角色按任务分配给 MSP 技术人员可降低 MSP 和客户的安全风险。[](/azure/active-directory/roles/delegate-by-task) 使 GDAP 能够向使用 Lighthouse 的技术人员分配更精细的角色，并跨客户租户采用最小特权安全方法。

如果 MSP 技术人员仍使用通过委派管理员权限 (DAP) 授予的支持人员代理或管理员代理角色访问客户环境，请参阅本文的 [位于 Lighthouse 中的 DAP](#dap-in-lighthouse) 。 如果 GDAP 和 DAP 共存，则通过 GDAP 授予用户的角色优先于已建立 GDAP 关系的客户。

## <a name="set-up-gdap-in-lighthouse"></a>在 Lighthouse 中设置 GDAP

> [!NOTE]
> GDAP 目前处于公共[](/partner-center/announcements/2022-february#6) (预览版) ，以允许合作伙伴在 GDAP 公开发布之前分配具体权限。

若要与客户建立 GDAP 关系，需要执行下面的高级步骤。 有关 GDAP 详细信息，请参阅 [GDAP](/partner-center/gdap-introduction) (委派管理员权限) 。

1. [将用户分类到](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members)合作伙伴租户的安全Azure AD。

2. [创建 GDAP 关系请求并将其发送给](/partner-center/gdap-obtain-admin-permissions-to-manage-customer) 客户。

3. 确保客户 [批准 GDAP 关系请求](/partner-center/gdap-customer-approval)。

4. [将相关安全组](/partner-center/gdap-assign-azure-ad-roles#grant-permissions-to-security-groups) 分配给 GDAP 关系。

5. 将相应的[Azure Active Directory角色分配给](/azure/active-directory/roles/permissions-reference)与客户管理一致的"Lighthouse"安全组。

我们建议根据 MSP 技术人员在 Lighthouse 中处理的任务命名安全组。 例如，您可以为技术支持人员、系统管理员和上报工程师创建安全组。 我们建议使用下表中列出的角色来管理 Lighthouse。

### <a name="example-security-groups"></a>示例安全组

||技术支持人员 |系统管理员 |升级工程师|
|--------------------|-------------|-------------|------------|
|**建议的 GDAP 角色** |<ul><li>帮助台管理员</li><li>安全读取者</li></ul>   |<ul><li>用户管理员</li><li>身份验证管理员</li><li>全局读取者</li><li>Intune 管理员</li><li>安全管理员</li></ul>   |全局管理员  |
|**Tasks** |在 Lighthouse 中读取客户信息， (，例如重置用户密码或更新联系人)    |通过采取纠正措施在 Lighthouse (维护客户安全，例如，重新启动) 。   |根据需要执行特权操作来保护客户租户 (例如，阻止遭到入侵的管理员登录) 。  |

有关特定权限的说明，请参阅Azure AD[角色。](/azure/active-directory/roles/permissions-reference) 有关特定于合作伙伴的角色和任务，请参阅 [最小特权角色](/partner-center/gdap-least-privileged-roles-by-task)。

## <a name="dap-in-lighthouse"></a>Lighthouse 中的 DAP

DAP 限制具有两个角色的 Lighthouse 客户的访问权限：管理员代理和技术支持代理。 可以在"所有组"页上查看安全组成员身份，检查合作伙伴租户中哪些用户具有管理员代理或支持代理角色Azure AD[组](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups)成员身份。 若要查看哪些客户仍有 DAP，请参阅监视 [管理关系和自助服务 DAP 删除](/partner-center/dap-monitor-self-serve-removal)。

对于具有 DAP 且没有 GDAP 的客户，管理员代理角色授予查看所有租户信息的权限，并有权在 Lighthouse (查看下文，了解还需要合作伙伴租户) 中的角色的其他操作。 

技术支持代理角色授予查看所有租户信息的权限，以及执行 Lighthouse (中的有限操作，例如重置用户密码、阻止用户登录以及更新客户联系信息和) 。

鉴于向使用 DAP 的合作伙伴用户授予的广泛权限，我们建议尽快采用 GDAP。 两种模型共存，但 GDAP 最终将替换 DAP，在转换期间，GDAP 权限优先于 DAP 权限。 有关详细信息，请参阅 [GDAP 常见问题](/partner-center/gdap-faq)。

## <a name="other-roles-and-permissions"></a>其他角色和权限

对于 Lighthouse 中的某些操作，需要合作伙伴租户中的角色分配。 下表列出了合作伙伴租户角色及其关联权限。<br><br>

| 合作伙伴租户角色 | 权限 |
|--|--|
| 合作伙伴租户的全局管理员 | <ul><li>在"百年一号"中注册Microsoft 365 管理中心。</li><li>在首次运行体验期间接受合作伙伴合同修正。</li><li>激活和停用租户。</li><li>创建、更新和删除标记。</li><li>分配和删除客户租户中的标记。</li></ul> |
| 分配了至少一个角色Azure AD以下属性集的合作伙伴租户成员：**microsoft.office365.supportTickets/allEntities/allTasks**<br> (有关角色Azure AD列表，请参阅Azure AD[角色](/azure/active-directory/roles/permissions-reference)。 | 创建 Lighthouse 服务请求。 |
| 满足以下两 *个要求的合作伙伴* 租户成员： <ul><li>具有至少一个Azure AD以下属性集分配的角色：**microsoft.office365.serviceHealth/allEntities/allTasks**<br> (有关角色Azure AD列表，请参阅Azure AD[内置角色](/azure/active-directory/roles/permissions-reference)</li><li>至少分配有一个 DAP 委派角色 (管理员代理或支持) </li></ul> | 查看服务运行状况信息。 |

## <a name="next-steps"></a>后续步骤

创建角色后，必须设置其他 Lighthouse 门户安全性，特别是 MFA (多重身份验证) （可选）Azure AD Identity Management (PIM) 。 有关详细信息，请参阅配置Microsoft 365 Lighthouse[门户安全性](m365-lighthouse-configure-portal-security.md)。

## <a name="related-content"></a>相关内容

[按任务分配的权限最低 (](/partner-center/gdap-least-privileged-roles-by-task?branch=pr-en-us-2577) 文章)   
[DAP (委派管理) 常见问题](/partner-center/dap-faq) (文章)   
[向用户分配角色和权限](/partner-center/permissions-overview) (本文)   
[本文Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (要求)   
[本文Microsoft 365 Lighthouse](m365-lighthouse-overview.md) (概述)   
[注册Microsoft 365 Lighthouse (](m365-lighthouse-sign-up.md)注册)   
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 
