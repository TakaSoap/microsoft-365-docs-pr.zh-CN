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
description: 对于托管服务提供商 (MSP) ，Microsoft 365 Lighthouse查看审核日志。
ms.openlocfilehash: a2c9efe88930ad0aae197a5cac26cf06b1386a53
ms.sourcegitcommit: e3bff611439354e6339bb666a88682078f32ec13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2022
ms.locfileid: "62354932"
---
# <a name="review-audit-logs"></a>查看审核日志

> [!NOTE]
> 本文中所述的功能为预览版，可能会更改，并且仅对满足要求的合作伙伴 [可用](m365-lighthouse-requirements.md)。 如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。

Microsoft 365 Lighthouse审核日志记录在 Lighthouse 或其他服务中生成更改Microsoft 365操作。 创建、编辑、删除、分配和远程操作都将创建审核事件，你可以查看这些事件。 默认为所有客户启用审核功能。 该功能无法禁用。

## <a name="before-you-begin"></a>准备工作

若要查看审核日志，您必须具有以下权限之一：

- Azure AD角色 - 合作伙伴租户的全局管理员

- 合作伙伴中心角色 - 管理员代理

## <a name="review-logs"></a>查看日志

1. In the left navigation pane in Lighthouse， select **Audit logs**.

    > [!NOTE]
    > 查看新日志可能需要 1 小时。 转到相应的服务以查看最新更改。

2. 若要筛选日志，请通过以下选项优化列表：

    - **日期范围** - 上一个月、周或日。
    - **租户** - 租户标记或客户租户名称。
    - **Activity** - Microsoft 365所采取操作对应的活动类型。 有关详细信息，请参阅活动类型表。
    - **由** - Who启动操作。

3. 从列表中选择日志以查看包括请求正文在内的 **完整** 详细信息。

选择 **"** 导出"，将日志数据导出到逗号分隔值 (.csv) 文件中。

## <a name="activity-types"></a>活动类型

下表列出了在 Lighthouse 审核日志中捕获的活动类型。 当创建新操作时，列表可能会更改。 可以使用活动活动值审核日志操作已启动。

| 活动名称    | Microsoft 365 Lighthouse | 已启动的操作  | 服务受到影响           |
|------------------|----------------------------------|-------------------|----------------------------|
|**apply**                                   | 租户                          | 应用部署计划                                           | Azure AD、Microsoft Endpoint Manager                   |
|**assignTag**                                | 租户                          | 应用来自客户的标记                                      | Microsoft 365 Lighthouse   |
|**changeDeploymentStatus**                   | 租户                          | 部署计划的行动计划状态                        | Microsoft 365 Lighthouse   |
|**offboardTenant**                            | 租户                          | 停用客户                                          | Microsoft 365 Lighthouse   |
|**resetTenantOnboardingStatus**              | 租户                          | 反应客户                                              | Microsoft 365 Lighthouse   |
|**tenantTags**                               | 租户                          | 创建或删除标记                                           | Microsoft 365 Lighthouse   |
|**tenantCustomizedInformation**              | 租户                          | 创建、更新或删除客户网站或联系人信息 | Microsoft 365 Lighthouse   |
|**unassignTag**                              | 租户                          | 从客户中删除标记                                    | Microsoft 365 Lighthouse   |
| **blockUserSignin**                          | 用户                            | 阻止登录                                                     | Azure AD                   |
| **confirmUsersComprom一**                  | 用户                            | 确认用户遭到入侵                                        | Azure AD                   |
| **dismissUsersRisk**                         | 用户                            | 消除用户风险                                                | Azure AD                   |
| **resetUserPassword**                        | 用户                            | 重置密码                                                   | Azure AD                   |
| **setCustomerSecurityDefaultsEnabledStatus** | 用户                            | 启用具有安全性默认值的 MFA                               | Azure AD                   |
|**restartDevice**                            | 设备                          | Restart                                                          | Microsoft Endpoint Manager |
| **syncDevice**                               | 设备                          | 同步                                                             | Microsoft Endpoint Manager |
| **rebootNow**                                | 威胁管理                | 重新启动                                                           | Microsoft Endpoint Manager |
| **reprovision**                              | 租户                          | 重试预配                                               | Windows 365                |
| **windowsDefenderScanFull**                  | 威胁管理                | 完全扫描                                                       | Microsoft Endpoint Manager |
| **windowsDefenderScan**                      | 威胁管理                | 快速扫描                                                       | Microsoft Endpoint Manager |
| **windowsDefenderUpdateSignatures**          | 威胁管理                | 更新防病毒                                                | Microsoft Endpoint Manager |

## <a name="next-steps"></a>后续步骤

如果需要更多信息，可以使用 Microsoft Graph API 访问更多审核事件。 有关详细信息，请参阅 [Overview for multi-tenant management using the Microsoft 365 Lighthouse API](/graph/managedtenants-concept-overview)。

## <a name="related-content"></a>相关内容

[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) 
