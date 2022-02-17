---
title: 查看审核日志
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
description: 对于托管服务提供商 (使用) 托管服务提供商Microsoft 365 Lighthouse，了解如何查看审核日志。
ms.openlocfilehash: 69eb057c0b6a7daf835ec613b7d386e1a7fbfbaa
ms.sourcegitcommit: 6e43aeff217afe97876137b1ead8df26db6e9937
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2022
ms.locfileid: "62859237"
---
# <a name="review-audit-logs"></a>查看审核日志

> [!NOTE]
> 本文中所述的功能为预览版，可能会更改，并且仅对满足要求的合作伙伴 [可用](m365-lighthouse-requirements.md)。 如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。

Microsoft 365 Lighthouse审核日志记录在 Lighthouse 或其他服务中生成更改Microsoft 365操作。 创建、编辑、删除、分配和远程操作都将创建审核事件，你可以查看这些事件。 默认为所有客户启用审核功能。 该功能无法禁用。

## <a name="before-you-begin"></a>开始之前

若要查看审核日志，您必须具有以下权限之一：

- Azure Active Directory (Azure AD) 角色 - 合作伙伴租户的全局管理员

- Microsoft 合作伙伴中心角色 - 管理员代理

## <a name="review-audit-logs"></a>查看审核日志

1. In the left navigation pane in Lighthouse， select **Audit logs**.

    > [!NOTE]
    > 查看新日志可能需要 1 小时。 转到相应的服务以查看最新更改。

2. 根据需要，使用下列选项筛选日志：

    - **日期范围** - 上一个月、周或日。
    - **租户** - 租户标记或客户租户名称。
    - **Activity** - Microsoft 365所采取操作对应的活动类型。 有关详细信息，请参阅 [Activities 表。](#activities)
    - **由** - Who启动操作。

3. 从列表中选择日志以查看完整详细信息， **包括请求正文** 。

    若要将日志数据导出到逗号分隔值 (.csv) 文件，请选择"导出 **"**。

## <a name="activities"></a>活动

下表列出了在 Lighthouse 审核日志中捕获的活动。 当创建新操作时，列表可能会更改。 您可以使用活动中列出的活动审核日志查看已启动的操作。<br><br>

| 活动名称 | 浅色市的区域 | 已启动的操作 | 服务受到影响 |
|--|--|--|--|
| **apply** | 租户 | 应用部署计划 | Azure AD、Microsoft Endpoint Manager (MEM)  |
| **assignTag** | 租户 | 应用来自客户的标记 | Lighthouse |
| **changeDeploymentStatus** | 租户 | 部署计划的行动计划状态 | Lighthouse |
| **offboardTenant** | 租户 | 停用客户 | Lighthouse |
| **resetTenantOnboardingStatus** | 租户 | 反应客户 | Lighthouse |
| **tenantTags** | 租户 | 创建或删除标记 | Lighthouse |
| **tenantCustomizedInformation** | 租户 | 创建、更新或删除客户网站或联系信息 | Lighthouse |
| **unassignTag** | 租户 | 从客户中删除标记 | Lighthouse |
| **blockUserSignin** | 用户 | 阻止登录 | Azure AD |
| **confirmUsersComprom一** | 用户 | 确认用户受到威胁 | Azure AD |
| **dismissUsersRisk** | 用户 | 消除用户风险 | Azure AD |
| **resetUserPassword** | 用户 | 重置密码 | Azure AD |
| **setCustomerSecurityDefaultsEnabledStatus** | 用户 | 使用安全默认值 (MFA) 多重身份验证 | Azure AD |
| **restartDevice** | 设备 | Restart | MEM |
| **syncDevice** | 设备 | 同步 | MEM |
| **rebootNow** | 威胁管理 | 重新启动 | MEM |
| **reprovision** | Windows 365 | 重试预配 | Windows 365 |
| **windowsDefenderScanFull** | 威胁管理 | 完全扫描 | MEM |
| **windowsDefenderScan** | 威胁管理 | 快速扫描 | MEM |
| **windowsDefenderUpdateSignatures** | 威胁管理 | 更新防病毒 | MEM |

## <a name="next-steps"></a>后续步骤

如果需要详细信息，请使用 Microsoft Graph API 访问更多审核事件。 有关详细信息，请参阅 [Overview for multi-tenant management using the Microsoft 365 Lighthouse API](/graph/managedtenants-concept-overview)。

## <a name="related-content"></a>相关内容

[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 
