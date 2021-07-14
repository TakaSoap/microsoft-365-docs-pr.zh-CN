---
title: 了解应用策略
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 了解应用策略。
ms.openlocfilehash: 6d4ff23ca0e09f5e410d32d6ced144afc0c4bb15
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420046"
---
# <a name="learn-about-app-policies"></a>了解应用策略

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

Microsoft 应用治理可检测 Microsoft 365 租户中的异常应用行为，并生成你可以查看、调查和解决的警报。 除了此内置检测功能外，你还可以使用一组默认模板，创建自己的应用策略来生成其他警报。

这些针对应用和用户模式及行为的策略可以防止用户使用不合规或恶意的应用，并限制有风险的应用访问你的租户数据。

以下是对应用策略管理所需的管理员角色的快速回顾。

| 角色 | 读取策略 | 创建、更新或删除策略 |
|:-------|:-----|:-------|
| 合规管理员 | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |
| 合规信息读取者 | ![复选标记](..\media\checkmark.png) |  |
| 全局管理员 | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |
| 全局读取者  | ![复选标记](..\media\checkmark.png) |  |
| 安全管理员 | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |
| 安全信息读取者  | ![复选标记](..\media\checkmark.png) |  |
| 安全操作员 | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |
||||

<!--
How app policies are the method by which MAPG detects app anomolies resulting in detection (alerts) and remediation (manual or automatic) 


CFA #2 Scenario 1: As an admin, I can quickly set up policies to govern M365 apps in my tenant using MAPG out-of-the-box templates
CFA #2 Scenario 2: As an admin, I can create customized policies to govern M365 apps in my tenant to meet my organizations requirements.
CFA #2 Scenario 3: As an admin or policy reviewer, I can view all policies created in my environment and quickly see which policies have associated alerts. 
CFA #2 Scenario 4: As an admin, I can adjust policies efficiently to meet changing needs.

App policy templates

- Basic info
- Policy settings and conditions
- Actions
- Status

--> 

## <a name="next-step"></a>后续步骤

[开始使用应用策略。](app-governance-app-policies-get-started.md)
