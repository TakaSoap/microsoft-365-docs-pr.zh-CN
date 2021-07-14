---
title: 确定你的应用合规性状况
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
description: 确定你的应用合规性状况。
ms.openlocfilehash: 3d7cac319c31bac40a3aad2f6b9a4c16303f6a20
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420027"
---
# <a name="determine-your-app-compliance-posture"></a>确定你的应用合规性状况

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

Microsoft 应用治理允许你从 [Microsoft 365 合规中心](https://compliance.microsoft.com/appgovernance)的应用治理概述页面快速评估第三方应用的合规状况及其对 Microsoft 365 租户中数据的访问。

![Microsoft 365 合规中心内的应用治理概述页面](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> 若要查看应用治理数据，你的登录帐户必须具有[这些角色](app-governance-get-started.md#administrator-roles)中的一个。
>

从该页面，你可以看到：

- 对于使用 Microsoft Graph API 且已启用 OAuth 的应用：

  - 你的租户中此类应用的数量
  - 享有过度特权的应用数
  - 享有高级特权的应用数

  根据此信息，你可以确定过度特权和高级特权应用对你的组织造成的风险级别。

- 对于警报：

  - 你的租户的活动警报数
  - 基于应用治理检测的警报（**威胁警报**）数量
  - 基于你制定的应用策略的警报（**策略警报**）数量
  - 最近 10 条警报

  根据此信息，你可以确定生成警报的速度以及检测到的和基于策略的警报的相对数量。

- 对于数据和资源访问：

  - 过去 90 天内的应用 API 数据访问
  - 热门资源过去 90 天内的使用情况

  根据此信息，你可以确定对 Microsoft 365 租户中数据的访问是否存在异常峰值。
