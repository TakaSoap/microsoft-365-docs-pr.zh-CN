---
title: 跟踪 Microsoft 安全分数历史记录并实现目标
description: 深入了解影响 Microsoft 安全分数的活动。 发现趋势并设定目标。
keywords: microsoft 安全分数， 安全分数， office 365 安全分数， Microsoft 安全分数， microsoft 365 安全中心， 改进操作
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
ms.openlocfilehash: ed937c90bbc6875ee3d72f710d5ac11d4069cbb6
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/29/2020
ms.locfileid: "49738039"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>跟踪 Microsoft 安全分数历史记录并实现目标

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft 安全](microsoft-secure-score.md) 分数是组织安全状况的度量，较高的数字表示采取更多改进措施。 可以在 https://security.microsoft.com/securescore [Microsoft 365 安全中心找到它](overview-security-center.md)。

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>深入了解影响分数的活动

在"历史记录"选项卡中查看组织一段时间的 **分数** 图。

下图是选定时间范围内执行的所有操作及其属性的列表，如生成的点和类别。 您可以自定义日期范围，并按类别进行筛选。

![活动历史记录](../../media/secure-score/secure-score-history-activity.png)

如果选择与活动关联的改进操作，将显示完整的改进操作飞出图。

若要查看该特定改进操作的所有历史记录，请在飞出中选择历史记录链接。

![改进操作历史记录](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>发现趋势并设定目标

在 **"指标&** 趋势"选项卡中，有几个图表可让你进一步查看趋势和设定目标。 你可以为整个可视化页面设置日期范围。 可视化包括：

* **安全分数区域** - 根据组织目标和良好、正常和差分范围的定义进行自定义。
* **回归趋势** - 由于配置、用户或设备更改而已回归的点的时间线。  
* **比较趋势** - 组织的安全分数如何与其他人的一段时间进行比较。 此视图可以包含表示具有相似席位计数的组织得分平均值的行和您可以设置的自定义比较视图。
* **风险接受趋势** - 标记为"接受风险"的改进措施日程表。
* **分数更改** - 获得分数、已回归分数以及指定日期范围内分数的更改。

### <a name="compare-your-score-to-organizations-like-yours"></a>将你的分数与像你这样的组织进行比较

有两处可了解分数与你类似的组织的比较方式。 在这两个图表中，都可以选择" **管理比较** "以查看和编辑组织的信息。 您还可以根据行业、组织规模、许可证和地区创建自定义比较。

#### <a name="comparison-bar-chart"></a>比较条形图

比较条形图是"概述 **"** 选项卡。将鼠标悬停在图表上可查看得分和得分机会。 对比较数据进行匿名处理，因此我们不确切知道哪些其他租户位于混合中。

![相似组织分数的条形图](../../media/secure-score/secure-score-comparison-bar.png)

- **组织（如你** 组织）：如果我们至少有五个或五 (个租户来比较符合以下条件) 租户的平均分数：
    1. 同一行业
    2. 组织规模相同
    3. 所有区域
    4. 使用的 Microsoft 产品有 80% 相似
    5. 机会 (租户 20% 范围内的当前许可证) 达到的最大得分

- **自定义比较**：需要根据以下条件选择"管理 **比较"进行** 设置：
    1. 选定的行业 () 
    2. 所选组织规模 () 
    3. 所选 (区域) 
    4. 所选许可证 () 
    5. 使用的 Microsoft 产品有 80% 相似
    6. 机会 (租户 20% 范围内的当前许可证) 达到的最大得分

如果你已进行自定义选择，但结果少于五个我们可以与之比较的其他租户，你将看到"由于数据有限，不可用"。

#### <a name="comparison-trend"></a>比较趋势

在 **"指标&** 趋势"选项卡中，查看组织的安全分数如何与其他人的一段时间进行比较。

![随着时间的推移，相似组织的分数的直线图](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>欢迎提出宝贵意见

如果有任何问题，请通过发布到安全、隐私和合规社区& [告知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 我们。 We're monitoring the community and will provide help.

## <a name="related-resources"></a>相关资源

- [Microsoft 安全分数概述](microsoft-secure-score.md)
- [评估你的安全状况](microsoft-secure-score-improvement-actions.md)
- [即将推出的功能](microsoft-secure-score-whats-coming.md)
- [新增功能](microsoft-secure-score-whats-new.md)
