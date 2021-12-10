---
title: Microsoft Defender for Endpoint 中的威胁防护报告
description: 使用威胁防护报告跟踪警报检测、类别和严重性
keywords: 警报检测， 来源， 警报按类别， 警报严重性， 警报分类， 确定
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 84893d7f015ec354bc27ac706c00e864705a42e5
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61165662"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中的威胁防护报告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)。

威胁防护报告提供有关在组织中生成的警报的高级别信息。 该报告包括趋势信息，显示检测源、类别、严重性、状态、分类以及警报的确定。

仪表板分为两个部分：

![威胁防护报告的图像。](images/threat-protection-reports.png)

节|说明
---|---
1|警报趋势
2|警报摘要

## <a name="alert-trends"></a>警报趋势
默认情况下，警报趋势显示以最后一整天结尾的 30 天时段的警报信息。 为了更好地了解组织中发生的趋势，您可以通过调整所显示的时间段来微调报告期间。 若要调整时间段，请从下拉列表选项中选择一个时间范围：

- 30 天
- 3 个月
- 6 个月
- 自定义警报

> [!NOTE]
> 这些筛选器仅适用于警报趋势部分。 它不会影响警报摘要部分。

## <a name="alert-summary"></a>警报摘要

虽然警报趋势显示趋势警报信息，但警报摘要显示范围为当天的警报信息。

 警报摘要允许您向下钻取到应用了相应筛选器的特定警报队列。 例如，单击"检测EDR"卡片中的"警报"栏，将进入警报队列，其中仅显示从检测结果EDR警报。

> [!NOTE]
> 摘要部分反映的数据的范围为当前日期之前的 180 天。 例如，如果今天的日期为 2019 年 11 月 5 日，则摘要部分的数据将反映从 2019 年 5 月 5 日到 2019 年 11 月 5 日的数字。
>
> 对"趋势"部分应用的筛选器不会应用于摘要节。

## <a name="alert-attributes"></a>警报属性

报告由显示以下警报属性的卡片决定：

- **检测源**：显示有关传感器和检测技术的信息，这些传感器和检测技术提供 Microsoft Defender for Endpoint 用于触发警报的数据。
- **威胁类别**：显示触发警报的威胁或攻击活动类型，指示安全操作可能重点关注的区域。
- **严重性**：显示警报的严重性级别，指示威胁对组织的潜在共同影响以及解决这些威胁所需的响应级别。
- **状态**：显示警报的解析状态，指示手动警报响应的效率以及自动修正 (如果已启用) 。
- 分类 **&** 确定：显示如何在解决时对警报进行分类，是将它们分类为实际威胁 (真正的警报) 还是错误检测 (错误警报) 。 这些卡片还显示已解决警报的确定，提供其他见解，如找到的实际威胁类型或错误检测到的合法活动。

## <a name="filter-data"></a>筛选数据

使用提供的筛选器包含或排除具有特定属性的警报。

> [!NOTE]
> 这些筛选器适用于 **报告中** 的所有卡片。

例如，若要显示有关高严重性警报的数据，请仅：

1. 在 **"事件&警报** 筛选器 \>  \> **">严重性"下，** 选择"高 **"。**
2. 确保已取消选择"严重性 **"下的** 所有其他选项。
3. 选择“**应用**”。

## <a name="related-topic"></a>相关主题

- [设备运行状况和合规性报告](machine-reports.md)
