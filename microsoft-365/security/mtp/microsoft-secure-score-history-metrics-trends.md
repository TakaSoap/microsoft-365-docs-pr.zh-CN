---
title: 跟踪你的 Microsoft 安全分数历史记录并实现目标
description: 深入了解已影响你的 Microsoft 安全分数的活动。 发现趋势并设置目标。
keywords: microsoft 安全分数，安全分数，office 365 安全分数，microsoft 安全分数，microsoft 365 安全中心，改进操作
ms.prod: microsoft-365-enterprise
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
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 4dfe1c9595db869a59474a030a5dd8673cf7db24
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769240"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>跟踪你的 Microsoft 安全分数历史记录并实现目标

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


[Microsoft 安全分数](microsoft-secure-score.md) 是组织的安全状态的度量，数字越大，表明执行了更多改进操作。 可在 https://security.microsoft.com/securescore [Microsoft 365 安全中心](overview-security-center.md)中找到。

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>深入了解已影响你得分的活动

在 " **历史记录** " 选项卡中查看组织的分数在一段时间内的关系图。

图下方是所选时间范围内执行的所有操作的列表及其属性，如结果点和类别。 您可以自定义日期范围并按类别进行筛选。

![活动历史记录](../../media/secure-score/secure-score-history-activity.png)

如果选择与某一活动相关联的 "改进" 操作，则将显示完整的 "改进操作" 浮出控件。

若要查看该特定 "改进" 操作的所有历史记录，请在浮出控件中选择 "历史记录" 链接。

![改进操作历史记录](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>发现趋势并设置目标

在 " **指标 & 趋势** " 选项卡中，有几个图表和图表可让您更好地了解趋势和设置目标。 您可以为整个可视化页设置日期范围。 可视化效果包括：

* **您的安全分数区域** -根据组织的目标和 "良好"、"好" 和 "差" 得分范围的定义进行自定义。
* **回归趋势** -由于配置、用户或设备更改而 regressed 的点的时间线。  
* **比较趋势** -组织的安全分数与其他人的对比情况。 此视图可包含表示具有类似座位计数的组织的平均分数和可设置的自定义比较视图的行。
* **风险接受趋势** -标记为 "风险已接受" 的 "改进" 操作的时间线。
* **分数变化** -指定的日期范围内已实现的点数，点 regressed，以及后续得分的变化。

### <a name="compare-your-score-to-organizations-like-yours"></a>比较你的成绩与你的组织（如你的组织）

有两个位置可查看您的分数如何与类似于您的组织进行比较。 在这两个图表中，您可以选择 " **管理比较** " 以查看和编辑您的组织的信息。 您还可以创建基于行业、组织规模、许可证和地区的自定义比较。

#### <a name="comparison-bar-chart"></a>比较条形图

比较条形图是 " **概述** " 选项卡。将鼠标悬停在图表上以查看分数和分数机会。 比较数据是匿名，因此我们不知道组合中的其他租户。

![相似组织分数的条形图](../../media/secure-score/secure-score-comparison-bar.png)

- **像你这样的组织** ：我们为你提供了其他 (租户的平均分数，如果我们至少有5个或更多租户可用于比较符合以下条件的) ：
    1. 同一行业
    2. 相同的组织规模
    3. 所有区域
    4. 使用的 Microsoft 产品是80% 相似的
    5. 在来自租户的20% 范围内，当前许可证) 可实现的商机 (最大分数

- **自定义比较** ：只有在找到5个或更多租户) 基于以下条件时，才需要先通过选择 " **管理比较** " (进行安装：
    1. 选定的行业 (s) 
    2. 选定的组织大小 (s) 
    3.  (s 的选定区域) 
    4. 选定的许可证 (s) 
    5. 使用的 Microsoft 产品是80% 相似的
    6. 在来自租户的20% 范围内，当前许可证) 可实现的商机 (最大分数

如果您未选择自定义选择结果导致的其他租户小于5个其他租户，则会看到 "由于数据有限而不可用"。

#### <a name="comparison-trend"></a>比较趋势

在 " **指标 & 趋势** " 选项卡中，查看组织的安全分数与其他时间的对比情况。

![一段时间内相似组织分数的线形图](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>我们希望收到你的来信

如果你有任何问题，请通过在 [安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社区中发布来告知我们。 我们正在监视社区，并将提供帮助。

## <a name="related-resources"></a>相关资源

- [Microsoft 安全评分概述](microsoft-secure-score.md)
- [评估你的安全状况](microsoft-secure-score-improvement-actions.md)
- [即将推出的功能](microsoft-secure-score-whats-coming.md)
- [新增功能](microsoft-secure-score-whats-new.md)
