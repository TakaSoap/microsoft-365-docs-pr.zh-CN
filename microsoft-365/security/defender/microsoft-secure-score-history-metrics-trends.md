---
title: 跟踪 Microsoft 安全分数历史记录并实现目标
description: 深入了解影响 Microsoft 安全分数的活动。 发现趋势并设定目标。
keywords: microsoft 安全分数、安全分数、Office 365 安全分数、microsoft 安全分数、Microsoft 365 Defender门户、改进操作
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 03a7a070d574ec18a12c3e70d5cef20d2161490b
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663745"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>跟踪 Microsoft 安全分数历史记录并实现目标

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft 安全分数](microsoft-secure-score.md) 是衡量组织安全状况的度量值，较高数字表示采取了更多改进措施。 可以在[Microsoft 365 Defender门户](microsoft-365-defender.md#the-microsoft-365-defender-portal)中找到https://security.microsoft.com/securescore它。

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>深入了解影响分数的活动

在" **历史记录** "选项卡中查看组织随时间推移的分数图。

下图列出了所选时间范围内执行的所有操作及其属性，例如生成的点和类别。 可以自定义日期范围并按类别进行筛选。

:::image type="content" source="../../media/secure-score/secure-score-history-activity.png" alt-text="描述Microsoft 365 Defender门户中的活动历史记录的页面示例" lightbox="../../media/secure-score/secure-score-history-activity.png":::

如果选择与活动关联的改进操作，则会显示完整的改进操作浮出控件。

若要查看该特定改进操作的所有历史记录，请选择浮出控件中的历史记录链接。

:::image type="content" source="../../media/secure-score/secure-score-history-flyout.png" alt-text="Microsoft 365 Defender门户中有关改进操作的历史记录窗格" lightbox="../../media/secure-score/secure-score-history-flyout.png":::

## <a name="discover-trends-and-set-goals"></a>发现趋势并设定目标

在 **"指标&趋势** "选项卡中，有多个图表和图表可让你更深入地了解趋势并设定目标。 可以为可视化效果的整页设置日期范围。 可视化效果包括：

* **安全评分区域** - 根据组织的目标和良好、良好和错误分数范围的定义进行自定义。
* **回归趋势** - 因配置、用户或设备更改而回归的点的时间线。  
* **比较趋势** - 组织的安全分数如何与其他人相比。 此视图可以包括表示具有类似席位计数的组织的分数平均值的行，以及可以设置的自定义比较视图。
* **风险接受趋势** - 标记为"接受风险"的改进操作的时间线。
* **分数更改** - 已实现的分数数、回归的分数数以及指定日期范围内的分数更改。

### <a name="compare-your-score-to-organizations-like-yours"></a>将分数与像你这样的组织进行比较

有两个位置可查看分数与与你的组织相比的方式。

#### <a name="comparison-bar-chart"></a>比较条形图

" **概述** "选项卡上提供了比较条形图。将鼠标悬停在图表上以查看分数和评分机会。 

:::image type="content" source="../../media/secure-score/secure-score-comparison-bar.png" alt-text="Microsoft 365 Defender门户中类似组织分数的条形图示例" lightbox="../../media/secure-score/secure-score-comparison-bar.png":::

比较数据是匿名的，因此我们不知道其他租户在组合中。

![类似组织分数的条形图。](../../media/secure-score/secure-score-comparison-screenshot.png)

#### <a name="comparison-trend"></a>比较趋势

在" **指标&趋势** "选项卡中，查看组织的安全分数与其他人在一段时间内的比较方式。

:::image type="content" source="../../media/secure-score/secure-score-comparison-trend.png" alt-text="Microsoft 365 Defender门户中类似组织的分数行图示例" lightbox="../../media/secure-score/secure-score-comparison-trend.png":::

## <a name="we-want-to-hear-from-you"></a>欢迎提出宝贵意见

如果有任何问题，请通过在 [安全性、隐私&合规性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社区中发布来告知我们。 我们正在监视社区，并将提供帮助。

## <a name="related-resources"></a>相关资源

- [Microsoft 安全分数概述](microsoft-secure-score.md)
- [评估安全状况](microsoft-secure-score-improvement-actions.md)
- [即将推出的功能](microsoft-secure-score-whats-coming.md)
- [新增功能](microsoft-secure-score-whats-new.md)
