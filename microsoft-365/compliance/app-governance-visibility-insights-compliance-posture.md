---
title: 确定你的应用合规性状况
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
description: 确定你的应用合规性状况。
ms.openlocfilehash: 01225c167a1293dd849848da1b641b48a53d7f0d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189533"
---
# <a name="determine-your-app-compliance-posture"></a>确定你的应用合规性状况

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

Microsoft 应用治理允许你从 Microsoft 365 合规中心的应用治理概述页面快速评估第三方应用的合规状况及其对 Microsoft 365 租户中数据的访问。

![Microsoft 365 合规中心的应用治理概述页面。](..\media\manage-app-protection-governance\mapg-cc-overview.png)

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

  - 租户中的应用在当前和前三个日历月内通过 Graph API 访问的数据总计。 （目前仅包括邮件和文件上传和下载使用情况）
  - 当前和前三个日历月内的数据使用情况，按资源类型细分。 （目前仅包括邮件和文件上传和下载使用情况）

  根据此信息，你可以确定对 Microsoft 365 租户中数据的访问是否存在异常峰值。
