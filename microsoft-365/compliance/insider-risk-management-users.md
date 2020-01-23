---
title: 内幕风险管理用户（预览）
description: 了解 Microsoft 365 中的内部人员风险管理用户
keywords: Microsoft 365，内幕风险管理，风险管理，合规性
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 5688d1554bc48632c3dca40dd33c65b4ea41ee20
ms.sourcegitcommit: ca06ee52dec472d3827983d67b049847ec2fdfc1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2020
ms.locfileid: "41256647"
---
# <a name="insider-risk-management-users-preview"></a>内幕风险管理用户（预览）

内幕风险管理用户是组织中包含在一个或多个内幕风险管理策略中的员工。 使用**用户仪表板**快速查看有关员工的风险信息，并将员工添加到现有的内幕风险管理策略中。 内幕风险管理策略中包含的每个用户在**用户仪表板**上显示以下信息：

- **Users**：用户的用户名。
- **风险级别**： 
- **主动警报**：针对所有策略的活动警报数。
- 已**确认冲突**：针对用户确认的已*确认策略冲突*的案例数。
- **案例**：用户的当前活动事例。

![内幕风险管理用户仪表板](media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a>查看用户详细信息

若要查看有关某个用户的风险活动的更多详细信息，请双击用户**仪表板**中的用户以打开用户详细信息窗格。 在 "详细信息" 窗格中，您可以查看以下信息：

- **用户配置文件**选项卡
    - **名称和标题**：用户的姓名和职位职务。
    - **用户电子邮件**：用户的电子邮件地址。
    - **别名**：用户的网络别名。
    - **组织或部门**：用户的组织或部门。

- **用户活动**选项卡
    - **最近用户活动的历史记录**：列出触发事件的策略和用户活动的风险指示器。 触发事件可能是接受辞职日期或员工上次计划的工作日期。 风险指标是确定为具有风险的元素且与包含用户的策略相匹配的活动。 列出了 "事件" 和 "风险" 活动，其中最新项最先列出。

## <a name="add-a-user-to-a-policy"></a>将用户添加到策略

若要将用户添加到内部风险管理策略，您将使用 "新建策略" 向导或 "Microsoft 365 合规性中心" 中的 "**内幕风险管理**" 解决方案中的 "**用户**" 选项卡。

完成以下步骤以将用户添加到现有内幕风险策略：

1. 在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**用户**" 选项卡。
2. 选择 "在工具栏上**向策略添加用户**"。
3. 在 "**添加新用户**" 对话框中，开始在 "**用户**" 字段中键入用户名。 选择要添加到策略中的用户。
4. 选择 "**策略**" 字段的下拉箭头以显示配置的 "内幕风险管理策略"。 选择要将用户添加到的策略。
5. 使用 "**监视窗口**" 滑块控件定义 .。。"监视" 窗口的范围是5到30天。
6. 选择 "**添加**"，然后**确认**将该用户添加到策略中。
