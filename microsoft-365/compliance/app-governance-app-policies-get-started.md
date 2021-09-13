---
title: 开始使用应用策略
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 开始了解应用策略。
ms.openlocfilehash: 2f22e56195b94f07a6b8499bd69c60d65f37cce8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59171093"
---
# <a name="get-started-with-app-policies"></a>开始使用应用策略

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

Microsoft 应用治理的应用策略是实施更主动或被动的条件，以创建警报或自动修正来满足组织中针对应用合规性的特定需求的方式。

要查看当前应用策略的列表，请转到“**Microsoft 365 合规中心”>“应用治理”>“策略**”。

![Microsoft 365 合规中心内的 MAPG 策略摘要页面。](..\media\manage-app-protection-governance\mapg-cc-policies.png)

## <a name="whats-available-on-the-app-policies-dashboard"></a>应用策略仪表板上提供的内容

你可以查看活动、非活动和审核策略的数量，以及每个策略的以下信息：

- **策略名称**
- **状态**

  - **活动**：所有策略评估和操作均处于活动状态。
  - **无效**：所有策略评估和操作均已禁用。
  - **审核模式**：策略评估处于活动状态（将触发警报），但策略操作处于禁用状态。

- **严重性**：在由于此策略被评估为 true 而触发的任何警报上设置的严重性级别，这是策略配置的一部分。
- **活动警报数**：由策略生成的具有“**正在进行**”或“**新建**”状态的警报。
- **警报总数**：此策略的活动警报和已解决警报。
- **上次警报日期**：上次由于此策略而生成警报的日期。
- **上次修改日期**：上次更改此策略的日期。

默认情况下，策略列表按 **上次修改日期** 排序。 要按其他属性对列表排序，请选择对应的属性名称。

选择一个策略时，会获得包含以下附加详细信息的详细的策略窗格：

- **说明**：有关策略用途的更详细说明。
- **创建者**：创建策略的帐户的用户主体名称 (UPN)。
- 此策略生成的警报总数和活动警报的列表。

可以通过在详细策略窗格中选择“**编辑**”或“**删除**”，或者在策略列表中选择策略的垂直省略号来编辑或删除应用策略。

还可以执行以下操作：

- 创建新策略。你可以从应用使用策略或权限策略开始。
- 将策略列表导出为逗号分隔值 (CSV) 文件。例如，你可以在 Microsoft Excel 中打开 CSV 文件，并按 **严重性** 对策略进行排序，然后按 **警报总数**”排序。
- 搜索策略列表。

## <a name="next-step"></a>后续步骤

[创建应用策略。](app-governance-app-policies-create.md)
