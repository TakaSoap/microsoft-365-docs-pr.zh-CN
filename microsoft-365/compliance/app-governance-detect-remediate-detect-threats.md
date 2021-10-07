---
title: 修正应用威胁
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
description: 修正应用威胁。
ms.openlocfilehash: 05106b9aaf790f92e8b69bfe14b393c45c934862
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193359"
---
# <a name="remediate-app-threats"></a>修正应用威胁

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

你可以通过 Microsoft 365 合规中心 Microsoft 应用治理部分的“**警报**”页面修正对 Microsoft 365 租户的应用威胁。

![Microsoft 365 合规中心内的应用治理警报摘要页面。](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

默认情况下，“**警报**”页面会列出由应用治理生成的新威胁警报以及由活动应用策略生成的基于策略的警报。 你可以选择特定警报来查看其详细信息，这会打开一个警报窗格，其中包含附加警报信息，并且可以更改警报的状态。

![Microsoft 365 合规中心内的应用治理警报详细信息页面。](..\media\manage-app-protection-governance\mapg-cc-alerts-alert.png)

在此窗格中，你可以获得以下附加信息：

- “**说明**”字段中有关警报的其他详细信息。
- 从“**策略名称**”字段生成警报的应用策略的名称。 你还可以选择“**查看策略**”以转到生成警报的应用策略。

在“**操作**”中为自动修正配置的应用策略的状态为“**已解决**”。

你可以通过以下步骤修正应用警报：

1. 调查：检查警报中的信息并将其状态更改为“**标记为正在进行**”。
2. 解决方案：在你调查并根据需要确定租户中的应用策略更改或持续应用支持后，将其状态更改为“**已解决**”。

根据应用警报模式，你可以更新相应的应用策略并更改其“**操作**”设置以执行自动修复。 这样就无需调查和手动解决应用策略未来生成的警报。 有关详细信息，请参阅[管理你的应用策略](app-governance-app-policies-manage.md)。
