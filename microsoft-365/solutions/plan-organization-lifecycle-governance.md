---
title: 为 Microsoft 365 组和 Microsoft 团队规划组织和生命周期管理
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 有关 Microsoft 365 中的协作工具的生命周期管理选项的精益
ms.openlocfilehash: 706f1aaecf22c4088d4539c208fef68320c5e710
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377183"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>为 Microsoft 365 组和 Microsoft 团队规划组织和生命周期管理

Microsoft 365 组提供了一组丰富的工具来实施您的组织所需的治理功能。 

下一节介绍了功能、建议最佳做法，并提供了指导以确定对调控的要求以及如何满足这些要求的指导。

## <a name="control-who-can-create-microsoft-365-groups"></a>控制可以创建 Microsoft 365 组的用户

最终用户可以从多个终结点（包括 Outlook、SharePoint、团队和其他环境）创建组。

![图像 desc](../media/04.png)

强烈建议使用自助服务所有者，并帮助用户更轻松地完成其工作。 限制组和团队创建会降低用户工作效率，因为许多 Microsoft 365 服务都需要创建组才能使服务正常工作。

考虑用于创建组的以下管理选项：

- 若要限制组的数量增加，请使用 [组过期策略](microsoft-365-groups-expiration-policy.md) 自动删除未使用的组。
- 将组创建限制为包含 [动态成员身份的安全组](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) 的成员，例如，所有全职员工。
- 将组创建限制为安全组，并要求用户在组织的组使用策略中完成培训，以便成为安全组的成员。

如果要限制可以创建组的用户，请参阅 [管理可创建 Microsoft 365 组的用户](manage-creation-of-groups.md) ，以了解有关如何配置此操作的信息。

## <a name="group-delete-restore-and-archiving"></a>组删除、还原和存档

删除 Microsoft 365 组时，默认情况下它将保留30天。 这 30 天时间被称为"软删除"，因为仍然可以对组进行还原。 30 天后，组和相关内容将永久删除且无法还原。

如果保留了保留策略以保留聊天、文件或邮件，则在删除组后将保留这些项目。 有关详细信息，请参阅 [了解保留策略](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 。

如果要删除一个组，但保留一个或多个组连接服务的内容，请参阅 [存档组、团队和 Yammer](end-life-cycle-groups-teams-sites-yammer.md) 获取信息。

## <a name="group-naming-policy"></a>组命名策略

组命名策略可帮助您以两种方式管理组：

- 可以使用前缀/后缀命名策略在组名称的开头或结尾强制实施固定字符串或 Azure AD 属性及其关联的电子邮件地址。 通过执行此操作，可以确保包含，例如，部门名称或组名称中的区域。
- 阻止的词策略可确保在组名称中不使用某些词（例如，行政人员姓名）。

当从任何组连接服务创建组时，将应用命名策略。

如果决定使用组的命名策略，请参阅 [Microsoft 365 组命名策略](groups-naming-policy.md)。

## <a name="group-expiration-policy"></a>组过期策略

您可以指定过期期限和任何到达该时间段结束的组，并且不会被更新。 过期时间是在创建组时开始，或在上次续订日期时开始。

将组设置为过期后：
- 在临近过期时，会通知组的所有者续订组。
- 自动续订活动组。
- 任何未续订的组都将被删除。
- 可以通过组所有者或管理员在30天内恢复删除的任何组。

过期策略是通过确保删除不再使用的组来限制组数量剧增的一种有效方式。 如果要创建组过期策略，请参阅 [Microsoft 365 组过期策略](microsoft-365-groups-expiration-policy.md)。
