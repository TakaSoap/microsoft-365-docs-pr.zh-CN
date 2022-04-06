---
title: Microsoft Defender for Endpoint 中的设备运行状况和合规性报告
description: 使用设备运行状况和合规性报告跟踪Windows 10运行状况检测、防病毒状态、操作系统平台和版本
keywords: 运行状况状态， 防病毒， 操作系统平台， windows 10 版本， 版本， 运行状况， 合规性， 状态
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
ms.openlocfilehash: bf89c0e57cbe14980b15ecf6f5a88f6db2b83e84
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474016"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中的设备运行状况和合规性报告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

设备状态报告提供有关组织中设备的高级别信息。 该报告包括显示传感器运行状况状态、防病毒状态、操作系统平台以及Windows 10 (和Windows 11) 的信息。

仪表板分为两个部分：

:::image type="content" source="images/device-reports.png" alt-text="设备报告" lightbox="images/device-reports.png":::


<br>

****

|节|说明|
|---|---|
|1|设备趋势|
|2|设备摘要 (当天) |
|||

## <a name="device-trends"></a>设备趋势

默认情况下，设备趋势显示从最后一整天结束的 30 天期间的设备信息。 为了更好地了解组织中发生的趋势，您可以通过调整所显示的时间段来微调报告期间。 若要调整时间段，请从下拉列表选项中选择一个时间范围：

- 30 天
- 三个月
- 6 个月
- 自定义警报

> [!NOTE]
> 这些筛选器仅应用于设备趋势部分。 它不会影响设备摘要部分。

## <a name="device-summary"></a>设备摘要

虽然设备趋势显示趋势设备信息，但设备摘要显示范围为当天的设备信息。

> [!NOTE]
> 摘要部分反映的数据的范围为当前日期之前的 180 天。 例如，如果今天的日期为 2019 年 3 月 27 日，则摘要部分的数据将反映从 2018 年 9 月 28 日到 2019 年 3 月 27 日的数字。
>
> 对"趋势"部分应用的筛选器不会应用于摘要节。

通过"设备趋势"部分，你可以向下钻取到应用了相应筛选器的设备列表。 例如，单击"传感器运行状况状态卡"中的"非活动"栏将打开设备列表，其中仅显示其传感器状态处于非活动状态的设备。

## <a name="device-attributes"></a>设备属性

报告由显示以下设备属性的卡片所决定：

- **运行状况：** 显示有关设备上传感器状态的信息，提供活动、通信受损、非活动或未看到传感器数据的设备的聚合视图。
- **活动Windows 10防病毒状态**：显示设备数量和Microsoft Defender 防病毒。
- **操作系统** 平台：显示组织内部存在的操作系统平台的分布。
- **Windows 10版本**：显示组织中Windows 10设备及其版本的分布。

## <a name="filter-data"></a>筛选数据

使用提供的筛选器包含或排除具有特定属性的设备。

你可以从设备属性中选择多个要应用筛选器。

> [!NOTE]
> 这些筛选器适用于 **报告中** 的所有卡片。

例如，若要显示有关Windows 10传感器运行状况状态的设备的数据：

1. 在 **"筛选器>""传感器运行状况">活动"**。
2. 然后选择操作系统 **平台> Windows 10**。
3. 选择“**应用**”。

## <a name="related-topic"></a>相关主题

- [威胁防护报告](threat-protection-reports.md)
