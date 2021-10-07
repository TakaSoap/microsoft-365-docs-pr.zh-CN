---
title: 规划组和组织的组织和生命周期Microsoft 365和Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: 与协作工具的生命周期管理选项Microsoft 365
ms.openlocfilehash: c1389b7dd787df6b4aab4cd5bb00377e05b99ff6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199269"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>规划组和组织的组织和生命周期Microsoft 365和Microsoft Teams

Microsoft 365组具有一组丰富的工具来实施组织所需的管理功能。 

下一节介绍这些功能、建议最佳实践并提供指导，以提出正确的问题以确定管理要求以及如何满足这些要求。

## <a name="control-who-can-create-microsoft-365-groups"></a>控制哪些人可以创建Microsoft 365组

最终用户可以从多个终点创建组，包括Outlook、SharePoint Teams和其他环境。

![图像 desc。](../media/04.png)

我们强烈建议自助服务，为组所有者提供能力并帮助用户更轻松地完成工作。 限制组和团队创建可能会降低用户的工作效率，因为许多Microsoft 365服务需要创建组，服务才能正常运行。

考虑以下组创建管理选项：

- 若要限制组移动，请使用 [组过期策略](microsoft-365-groups-expiration-policy.md) 自动删除不使用的组。
- 将组创建限制为包含动态成员身份[](/azure/active-directory/users-groups-roles/groups-create-rule)（例如，所有全职员工）的安全组的成员。
- 将组创建限制为安全组，并要求用户完成组织组使用策略的培训，以便成为安全组的成员。

如果要限制可以创建组的人，请参阅管理[哪些人可以创建Microsoft 365组，](manage-creation-of-groups.md)了解如何配置此组。

## <a name="group-delete-restore-and-archiving"></a>组删除、还原和存档

删除Microsoft 365组时，默认情况下该组将保留 30 天。 这 30 天时间被称为"软删除"，因为仍然可以对组进行还原。 30 天后，组和相关内容将永久删除且无法还原。

如果已制定保留策略来保留聊天、文件或邮件，则删除组后将保留这些项目。 有关详细信息 [，请参阅了解](../compliance/retention.md) 保留策略。

如果要删除组，但保留一个或多个已连接组的服务[中](end-life-cycle-groups-teams-sites-yammer.md)的内容，请参阅存档组、团队和Yammer获取信息。

## <a name="group-naming-policy"></a>组命名策略

组命名策略可以通过两种方式帮助您管理组：

- 前缀/后缀命名策略可用于在组名称及其关联电子邮件地址的开头或结尾强制执行固定字符串或 Azure AD 属性。 通过执行此操作，可以确保在组名称中加入部门名称或区域等。
- 阻止的词语策略可以确保某些词语（如主管的姓名）不会用于组名。

从任何组连接的服务创建组时，将应用命名策略。

如果你决定对组使用命名策略，请参阅Microsoft 365[组命名策略。](groups-naming-policy.md)

## <a name="group-expiration-policy"></a>组过期策略

你可以指定过期期限，达到该期限到期且未续订的任何组都将被删除。 过期期限从组创建时或上次续订日期开始。

将组设置为过期后：
- 当过期时间即将到期时，将通知组的所有者续订组。
- 自动续订活动组。
- 任何未续订的组都将被删除。
- 任何已删除的组都可以在 30 天内由组所有者或管理员还原。

过期策略是一种通过确保删除不再使用的组来限制组过期的一个好方法。 如果要创建组过期策略，请参阅Microsoft 365[过期策略。](microsoft-365-groups-expiration-policy.md)

## <a name="related-topics"></a>相关主题

[协作治理规划分步规划](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作管理计划](collaboration-governance-first.md)

[删除以前的员工和安全数据](/microsoft-365/admin/add-users/remove-former-employee)
