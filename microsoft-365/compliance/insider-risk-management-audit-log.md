---
title: 内部风险管理审核日志
description: 了解企业内部风险管理审核日志Microsoft 365
keywords: Microsoft 365- 预览体验计划风险管理、风险管理、合规性
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 2bf453e8856f69e9ddb8c7c7a9264267ef77b4f0
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60662536"
---
# <a name="insider-risk-management-audit-log"></a>内部风险管理审核日志

通过内部风险管理审核日志，你可以及时了解对内部风险管理功能采取的操作。 此日志允许独立查看分配给一个或多个内部风险管理角色组的用户所采取的操作。 内部风险管理审核日志在组织中自动启用，并且无法禁用。

![内部风险管理审核日志。](../media/insider-risk-audit-log.png)

每当审核日志活动时，都会自动更新并立即更新活动，日志将活动信息保留 180 天 (大约六个月) 。 180 天后，活动的数据将从日志中永久删除。

活动监视中包含的区域包括：

- 策略
- 案例
- 警报
- 设置
- 用户
- 通知模板

若要查看和导出数据，审核日志内部风险管理或内部风险管理审核 *员* 角色组。  若要详细了解内部风险管理角色组，请参阅内部风险管理入门步骤 [1：启用权限](insider-risk-management-configure.md#step-1-required-enable-permissions-for-insider-risk-management)。

> [!NOTE]
> 内部风险管理审核日志与组织无关，它们Microsoft 365 审核日志独立审核系统，并捕获有关单独活动的信息。 禁用Microsoft 365审核不会影响内部风险管理中的活动审核。

## <a name="view-activity-in-the-insider-risk-audit-log"></a>查看内部风险中心审核日志

若要查看针对内部风险管理监视的功能活动，请导航到任何内部风险管理审核日志右上方区域中的"预览体验成员风险报告"链接。默认情况下，你将看到针对内部风险管理活动显示的以下信息：

- **活动：** 用户在内部风险管理解决方案中执行的活动的说明。
- **类别：** 执行活动的一个或多个区域。 例如， *执行策略更改* 活动时，你将看到"策略"类别。
- **由：** 执行活动的用户的用户名。
- **日期：** 执行活动的日期和时间。 日期和时间是组织的本地日期和时间。

有关记录的活动的详细信息，请选择活动以显示活动详细信息窗格。 此窗格包含有关活动的其他信息。

## <a name="columns-and-filtering"></a>列和筛选

为了便于审核员查看记录的活动，预览体验成员风险中心支持 **审核日志。** 对于基本筛选，队列列可以添加到视图中，以提供文件和邮件的不同透视。 可以按"类别 **"、"日期范围"和"** 由字段 **执行的活动"来筛选** 活动。

若要为活动队列添加或删除列标题，请使用 **"** 自定义列"控件并从列选项中进行选择。 这些列映射到预览体验成员风险计划支持的审核日志本文稍后将列出。

## <a name="audit-log-export"></a>审核日志导出

分配给内部风险管理或内部风险管理审核员角色组的用户可以通过选择"预览体验成员风险 审核日志"页上的"导出"，将 审核日志 中所有活动导出到 .csv (逗号分隔值) **文件中。**  根据活动的不同，活动某些字段可能不适用于活动，这些字段将在导出的文件中显示为空白。

该文件包含以下字段的活动信息：

- **由：** 修改项目值的用户的用户名。 此处列出的用户被分配到以下一个或多个角色内部风险管理角色组 *：Insider Risk Management、Insider* Risk *Management Admins、Insider* *Risk Management Analysts、Insider* *Risk Management访问人员*。 [](insider-risk-management-configure.md#step-1-required-enable-permissions-for-insider-risk-management) 每个角色组具有不同的权限级别来管理内部风险功能。
- **活动：** 对项目执行的活动。 值为 *Viewed、Deleted、Added、Edited policy、Case、User、Alert* 和 *设置。*
- **添加**：在活动期间添加的对象，如用户、文件类型或域。
- **警报量**：内部风险管理设置中定义的警报量级别。
- **金额**：当前选定的策略自定义指示器金额。
- **资产 ID：** 执行活动的优先级物理资产的资产 ID。
- **类别：** 修改的项目的类别。 值为 *Policies、Cases、Users、Alerts、设置 和* Notice *模板。*
- **日期：** 日期和时间，在组织的本地日期和时间中列出。
- **说明**：用户为要处理的对象（如策略 (优先级用户组）输入的说明) 。
- **DLP 策略**：已选择" (DLP) 策略，以触发包含到内部风险管理策略中。
- **指示器**：在内部风险设置中，活动在 (（如添加或删除指示器）中的) 。
- **通知模板**：执行活动的通知模板。
- **天数：** 在内部风险设置中定义的策略激活窗口。
- **文件数**：在内部风险管理设置中定义的文件数量限制。
- **策略模板**：指示器所操作的策略模板属于该模板。
- **以前的金额**：以前选择的自定义指标策略金额。
- **优先级用户组**：执行活动的优先级用户组。
- **已删除**：活动期间删除的对象，如用户、文件类型或域。
- **发件人**：活动执行通知模板的发件人字段。
- **目标策略**：活动在用户 (，例如向用户添加用户或删除用户) 。
- **模板邮件正文**：执行活动的通知模板的邮件正文。
- **模板主题**：执行活动的通知模板的主题字段。
- **用户：** 执行活动的用户。
