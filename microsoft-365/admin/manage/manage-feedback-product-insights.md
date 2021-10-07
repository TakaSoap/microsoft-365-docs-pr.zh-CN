---
title: Microsoft 产品 NPS 反馈和组织的见解
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 使用最终用户的 (NPS) ，查看他们对 Microsoft 产品和服务的感觉。
ms.openlocfilehash: afde0abf85cca682a5cda3206fa78d24cafc8cb8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168118"
---
# <a name="microsoft-product-nps-feedback-and-insights-for-your-organization"></a>Microsoft 产品 NPS 反馈和组织的见解

作为组织管理员Microsoft 365，你现在可以看到组织中用户生成的见解和数据。

NPS (的) 高分调查收集用户反馈，并衡量用户说出他们向好友和同事推荐产品和服务的可能性。 此数据可用于组织级别，以确定采用和推出策略。

我们使用来自最终用户的 NPS 调查和反馈，提供有关 Microsoft 产品和服务的见解。 此信息可帮助您了解组织中最终用户使用哪些产品和服务，还可以帮助您识别问题并快速解决问题。 使用此信息，您可以：

<!--See location of users who have submitted feedback-->
- 查看他们使用的操作系统或平台
- 使用关键字筛选产品、平台和搜索
- 请参阅最终用户对主要产品和问题的评论
- 将反馈和调查信息导出到 CSV 文件以进一步调查

## <a name="before-you-begin"></a>准备工作

您需要是管理员 [才能](../add-users/about-admin-roles.md) 查看和阅读调查报告。 您的组织需要打开反馈调查以查看和阅读调查报告。 有关详细信息 [，请查看管理组织的 Microsoft](manage-feedback-ms-org.md) 反馈。

## <a name="survey-insights"></a>调查见解

1. 在管理中心，转到运行状况产品  >  **反馈**  >  **NPS 调查见解**。
2. 从 **NPS 调查见解** 页面，导航到该页面以查看与组织的 NPS 相关的调查见解。

:::image type="content" source="../../media/prosight-product-feedback.png" alt-text="屏幕截图：Microsoft 365 Nps 调查见解":::

### <a name="chart-information"></a>图表信息

**总** 反馈显示最终用户提交的 NPS 反馈回复总数，包括带评论和不带评论的 NPS 反馈。

**注释** 显示最终用户提交的包含评论的 NPS 反馈响应的总数。

**按应用程序批量** 显示按应用程序表示的 NPS 反馈响应量总数。

**按月的反馈量** 按月显示 NPS 反馈响应量总数。

:::image type="content" source="../../media/prosight-charts-area.png" alt-text="屏幕截图：Microsoft 365调查见解":::

### <a name="top-topic-filters"></a>热门主题筛选器

主题是机器学习模型，可帮助分析 NPS 调查反馈的评论、短语和详细内容，从而提供对顶级最常见主题的访问。 顶部主题筛选器显示最详细的反馈的前 5 个主题。

:::image type="content" source="../../media/prosight-top-topic-filters-2.png" alt-text="Screenshot： Top topic filters on NPS survey data":::

> [!NOTE]
> 只有在符合与主题专家合作设定的最低质量标准后，我们才发布智能主题。 精度和调用指标用于确定相同。

**Verbatim 精度** 是本主题中分类的一个详细内容正确的可能性。

**Verbatim Recall** 是本主题中对与本主题相关的详细内容进行分类的可能性。

当前提供的主题如下所示：

**导航** 包括客户有关应用导航和可用性的评论。

- Verbatim Precision- 93%
- Verbatim Recall- 98%

**协作** 是指用户发现使用 Microsoft 应用进行协作有多简单。

- Verbatim Precision- 92%
- Verbatim Recall-91%

**值** 是指客户对定价和付款首选项等主题的感知。

- Verbatim Precision- 86%
- Verbatim Recall- 100%

**可靠性** 包括客户有关应用和系统行为的评论，导致意外终止。

- Verbatim Precision- 97%
- Verbatim Recall- 94%

**性能** 是指客户评论，这些评论解决了与用户在使用 Microsoft 产品时所体验的操作速度相关的问题。 本主题不介绍崩溃或更广泛的可靠性问题。

- Verbatim Precision- 92%
- Verbatim Recall- 98%

**用户教育** 反馈包括客户对帮助文档、教程、指南和其他产品内或在线学习内容的评论。

- Verbatim Precision- 83%
- Verbatim Recall- 87%

**复杂性** 是指客户对应用是复杂还是直接使用的反馈。

- Verbatim Precision- 92%
- Verbatim Recall- 89%

**常规表扬** 是指具有积极情绪且不适合任何其他主题的客户评论。

- Verbatim Precision- 93%
- Verbatim Recall- 98%

### <a name="export-to-csv-and-search"></a>导出到 CSV 和搜索

可以使用"导出到 CSV"功能导出原始数据以进一步分析。

> [!NOTE]
> 原始数据包括所有类型的反馈，包括非 NPS 反馈。

### <a name="filters"></a>筛选器

你可以按 **频道、产品****、****平台和反馈类型****进行筛选**。

**频道** 是一种供组织选择为用户获取功能更新Office。 有关详细信息，[请通过 Overview of update channels for Microsoft 365 应用版](/deployoffice/overview-update-channels)。 此筛选器允许你筛选到从特定频道上的用户提交的反馈

可以在各种平台（如 Android、iOS、Mac 和 Windows）上提交Windows。  此筛选器允许你基于提交它的平台筛选反馈。

大多数适用于 **Microsoft 365产品都可以** 在此筛选器下找到。 使用此筛选器选择已提交反馈的产品。

使用 **"** 反馈 (仅设置为 NPS 反馈) 可以筛选我们收集的反馈。

:::image type="content" source="../../media/prosight-filters.png" alt-text="屏幕截图：Microsoft 365 NPS 调查见解筛选器":::
