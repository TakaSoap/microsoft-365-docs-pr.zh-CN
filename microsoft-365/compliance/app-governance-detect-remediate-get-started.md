---
title: 开始使用应用威胁检测和修正
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: 开始使用应用威胁检测和修正。
ms.openlocfilehash: 7bf3e716bfa84161503ad656264ada82adc2bd6b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188369"
---
# <a name="get-started-with-app-threat-detection-and-remediation"></a>开始使用应用威胁检测和修正

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

Microsoft 应用治理会收集基于恶意应用活动的内置应用治理检测方法生成的威胁警报以及你创建的活动应用策略生成的基于策略的警报。

首先从位于 [https://aka.ms/appgovernance](https://aka.ms/appgovernance) 的应用治理仪表板查看应用警报。

![Microsoft 365 合规中心内的应用治理概述页面，其中突出显示了“检测和策略警报”部分。](..\media\manage-app-protection-governance\mapg-cc-overview-alerts.png)

此概述页面的“**检测和策略警报**”部分会列出最新的警报。 你可以使用它来快速查看租户的当前应用警报活动。

若要查看所有警报，请选择“**警报**”标签。

## <a name="whats-available-on-the-alerts-page"></a>警报页面上提供的内容

“**警报**”页面会列出针对租户的所有基于应用治理的警报。

![Microsoft 365 合规中心内的应用治理警报摘要页面。](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

列出的每个警报都包含以下信息：

- **警报名称**：异常行为的类型。
- **应用名称**：生成警报的应用。
- **严重性**：应用治理为其创建的警报分配的严重性或生成警报的应用策略的严重性。
- **来源**：警报的来源，可以是策略（用户创建的策略）、检测（内置检测策略）或 MCAS 的结果。
- **状态**：“**新**”表示尚未分配状态的警报。 分配后，状态为“**正在进行**”表示正在调查的警报，“**已解决**”表示已通过自动或手动修正解决的警报。
- **创建日期**：应用治理检测或应用策略生成警报的日期。 所有日期均按照 Microsoft 365 合规中心的本地时区显示。
- **上次活动**：上次更改警报状态的日期。 所有日期均按照 Microsoft 365 合规中心的本地时区显示。

默认情况下，警报列表按 **创建日期** 排序。 要按其他属性对列表排序，请选择对应的属性名称。

还可以将当前警报列表导出到逗号分隔值 (CSV) 文件。 例如，你可以在 Microsoft Excel 中打开 CVS 文件，然后按“**严重性**”和“**创建日期**”对警报列表进行排序。

## <a name="next-step"></a>后续步骤

[调查异常检测警报](app-governance-anomaly-detection-alerts.md)
