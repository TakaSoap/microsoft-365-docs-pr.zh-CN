---
title: Microsoft Defender for Endpoint 中的设备运行状况和合规性报告
description: 使用设备运行状况和符合性报告跟踪设备运行状况状态检测、防病毒状态、OS 平台和Windows 10版本
keywords: 运行状况状态、防病毒、os 平台、Windows 10 版本、版本、运行状况、符合性、状态
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
ms.openlocfilehash: d171db0d5009cc32c34c3bf95da907221f275410
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789263"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中的设备运行状况和合规性报告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒 

**平台**
- Windows
- Mac OS
- Linux
- iOS
- Android

希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

设备状态报告提供有关组织中设备的高级信息。 该报告包括显示传感器运行状况状态、防病毒状态、OS 平台以及Windows 10 (和Windows 11) 版本的趋势信息。

仪表板分为两个部分：

:::image type="content" source="images/device-reports.png" alt-text="设备报表" lightbox="images/device-reports.png":::


<br>

****

|节|说明|
|---|---|
|1|设备趋势|
|2|设备摘要 (当前) |
|||

## <a name="device-trends"></a>设备趋势

默认情况下，设备趋势显示以最新全天结束的 30 天时间段内的设备信息。 若要更好地了解组织中出现的趋势，可以通过调整显示的时间段来微调报告周期。 若要调整时间段，请从下拉选项中选择时间范围：

- 30 天
- 三个月
- 6 个月
- 自定义警报

> [!NOTE]
> 这些筛选器仅应用于设备趋势部分。 它不会影响设备摘要部分。

## <a name="device-summary"></a>设备摘要

当设备趋势显示趋势设备信息时，设备摘要显示范围为当前的设备信息。

> [!NOTE]
> 摘要部分中反映的数据范围为当前日期之前的 180 天。 例如，如果今天的日期是 2019 年 3 月 27 日，摘要部分上的数据将反映从 2018 年 9 月 28 日到 2019 年 3 月 27 日的数字。
>
> 对趋势部分应用的筛选器不会应用于摘要部分。

设备趋势部分允许向下钻取到应用相应筛选器的设备列表。 例如，单击传感器运行状况状态卡中的“非活动”栏将显示设备列表，结果仅显示传感器状态处于非活动状态的设备。

## <a name="device-attributes"></a>设备属性

报表由显示以下设备属性的卡组成：

- **运行状况状态**：显示有关设备上的传感器状态的信息，提供处于活动状态、通信受损、处于非活动状态或看不到传感器数据的设备的聚合视图。
- **活动Windows 10设备的防病毒状态**：显示设备数和Microsoft Defender 防病毒状态。
- **OS 平台**：显示组织中存在的 OS 平台的分布。
- **Windows 10版本**：显示组织中Windows 10设备及其版本的分布。

## <a name="filter-data"></a>筛选数据

使用提供的筛选器包括或排除具有特定属性的设备。

可以选择要从设备属性中应用的多个筛选器。

> [!NOTE]
> 这些筛选器适用于报表中 **的所有** 卡片。

例如，若要显示有关具有活动传感器运行状况状态的Windows 10设备的数据：

1. 在 **“筛选器”下>传感器运行状况状态>活动** 状态。
2. 然后 **> Windows 10选择 OS 平台**。
3. 选择“**应用**”。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="related-topic"></a>相关主题

- [威胁防护报告](threat-protection-reports.md)
