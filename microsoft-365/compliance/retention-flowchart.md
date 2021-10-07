---
title: 用于确定何时保留或永久删除项的流程图
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 使用流程图确定项具有多个保留策略或保留标签和保留策略时的结果
ms.openlocfilehash: b99f54178adc05987249f05c0f2d1c00194f0db0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159762"
---
# <a name="flowchart-to-determine-when-an-item-will-be-retained-or-permanently-deleted"></a>用于确定何时保留或永久删除项的流程图

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

使用以下流程图将 [保留策略](retention.md#the-principles-of-retention-or-what-takes-precedence) 应用于项，以确定系统因保留标签或保留策略是将其保留还是永久删除。

当下列任一条件适用时，此逻辑流用于项：

- 应用了多个保留策略
- 存在一个保留标签和一个或多个保留策略

当某个项受电子数据展示保留约束时，它将始终保留在保留策略和保留标签的决策流之前。

如果不熟悉此流程图中使用的任何术语，请参阅 [了解保留策略和保留标签](retention.md)。


   ![用于确定何时保留或永久删除项的流程图。](../media/retention-flowchart.svg)

> [!NOTE]
> 请务必区分项的最长保留期与保留策略或标签中指定的最长指定期。 同样，务必区分项的最短过期日期与保留策略中的最短指定期。
> 
> 有关详细信息，请参阅 [保留原则](retention.md#the-principles-of-retention-or-what-takes-precedence) 部分中图形后面的说明。
