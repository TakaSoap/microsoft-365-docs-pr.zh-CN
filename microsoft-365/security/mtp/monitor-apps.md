---
title: 应用监视&报告 - 安全中心
description: 了解如何在组织中深入了解云应用使用。 包括不同类型的应用、其风险级别和警报。
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， 监视， 报告， 应用
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930518"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Microsoft 365 安全中心中的应用监视和报告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


这些报告提供有关云应用在组织中如何使用的更多见解。 包括不同类型的应用、其风险级别和警报。

## <a name="monitor-email-accounts-at-risk"></a>监视有风险的电子邮件帐户

**电子邮件保护** 显示处于风险之中的电子邮件帐户。 可以选择在 Microsoft Defender 安全中心中进一步调查的帐户。

![电子邮件保护卡](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>监视用户授予的应用权限

**Cloud App Security - OAuth 应用** 列出云应用安全发现的应用，这些应用已由用户授予权限。 Cloud App Security 的风险目录包括超过 16，000 个应用，这些应用使用 70 多种风险因素进行评估。

风险因素从常规信息（如应用发布者）开始。 然后，它移至安全措施和控件，例如应用是支持静态加密还是提供审核日志活动。

![Cloud App Security OAuth 应用卡](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>监视云应用用户帐户

**用于查看的云应用帐户** 列出了可能需要关注的帐户。

![用于查看卡片的云应用帐户](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>了解使用哪些云应用

**发现的云 (类别)** 显示组织中使用的应用类型。 它链接到 Cloud App Security 中的云发现仪表板。 有关详细信息，请参阅快速 [入门：使用发现的应用](https://docs.microsoft.com/cloud-app-security/discovered-apps)。  

![发现的云应用类别卡片](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>监视用户访问云应用的地方

**云应用活动位置** 显示用户访问云应用的位置。

![云应用活动位置卡](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>监视基础结构工作负荷的运行状况

**基础结构运行状况** 显示 Azure Defender 中基础结构工作负荷的运行状况警报。

Azure Defender 跨本地和云工作负载为 Office 365 提供统一的安全管理和 Defender。 你可以收集、搜索和分析不同来源的安全数据，包括防火墙和其他合作伙伴解决方案。

有关详细信息，请参阅 [Azure Defender 文档](https://docs.microsoft.com/azure/security-center/)。

![基础结构运行状况卡](../../media/infrastructure-health.png)
