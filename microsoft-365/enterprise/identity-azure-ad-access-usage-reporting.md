---
title: 步骤 13：监控租户和登录活动
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置 Azure AD 访问和使用情况报告。
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865385"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a>步骤 13：监控租户和登录活动

** 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步骤中，将使用 Azure AD 报告查看审核日志和登录活动。有两种类型的报告可用。

**** 审核日志活动报告 - 记录在 Azure AD 租户中执行的每项任务的历史记录。此报告可回答如下问题：

- 谁将某人添加到管理员组？
- 哪些用户将登录到特定应用？
- 发生多少密码重置？

**** 登录活动报告 - 记录谁执行了审核日志报告所报告的任务。此报告可回答如下问题：

- 对于调查中的特定用户，其登录模式是什么？
- 我每天、每周或每月的登录量是多少？
- 多少次登录尝试失败及其相关帐户？

有关报告以及如何进行访问的详细信息，请参阅 [Azure Active Directory 报告](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)。

通过此步骤，你将认识这些报告并了解如何使用它们洞察 Azure AD 事件和活动，以用于规划和安全目的。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [允许用户创建和管理自己的组](identity-self-service-group-management.md) |
