---
title: 电池洞察力
description: ''
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 434f62d5ddfc8bc75c54de422aafc8c6325c4086
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170592"
---
# <a name="battery-insights"></a>电池洞察力
此视图提供 Microsoft 托管桌面设备的电源、电池和应用使用指标。 出于这些目的，如果应用程序正在运行且处于焦点，则会被视为 "正在使用中"。

若要查看使用率数据，请选择 "**电池**" 选项卡。

![电池窗格：左上角的每设备型号预测电池使用寿命（按应用）在底部右侧的 insights 表格中。 右上部的文档链接。](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>预测电池寿命

在**预测电池寿命**区域，我们根据设备型号对设备的预期电池寿命提供预测。

> [!NOTE]
> 此数据源自 Microsoft 托管桌面部署中随机<em>选择</em>的设备（也报告数据）中的采样能源使用、使用时间和电池容量。

该表提供了预计的电池寿命（以小时为单位）、其他 Microsoft 托管桌面部署中相同型号的平均电池寿命以及在您的环境中报告此数据的设备数量。 通过选择列标题对数据进行排序。



## <a name="top-energy-consumers"></a>热门能源消费者

在 "**热门能源使用者**" 区域中，你将发现环境中的应用程序在 milliWatt 小时（mWh）内消耗最多能源。 显示的应用程序以每个特定设备为依据，在左侧的**预测电池寿命**部分中选择。 例如，若要查看 Microsoft Surface Book 2 设备的每应用程序的消耗量，请在电池寿命区域中选择该行。 如果不选择任何模型，则显示的应用程序使用数据适用于我们具有共同数据的所有应用程序。

 对于每个应用程序，彩色网段显示了应用在这些类别中的能源使用情况：

- CPU
- 显示
- 网络
- 其他

"其他" 可能包括各种源（如磁盘活动、移动宽带使用）和对内部电阻断电的能源消耗。 

您可以使用右上角的菜单筛选此视图，以仅显示前台应用程序、后台应用程序或两者。 前台应用是指在最近28天内具有用户交互的应用程序，例如，使用鼠标选择一些内容。

## <a name="insights"></a>见解

**Insights**区域显示 CPU 和网络类别中的前三个能源使用者。 与所有 Microsoft 托管桌面部署相比，这些项目的能源消耗高于平均能源。 不显示 "显示" 资源，因为它严重依赖于设备使用时间和屏幕亮度设置。 

有关详细信息，请选择 "**详细**信息" 列中的列表。

## <a name="battery-optimization"></a>电池优化

Windows 10 提供了大量[设备设置](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)，以提高电源使用并延长 Microsoft 托管桌面设备的电池使用寿命。 其中一些设置可能会降低其他 Windows 功能，因此您还必须考虑其他因素，如组织中设备的角色。 Windows 支持维护这些[电池保存提示](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)的列表。

用户无需进行管理员提升或支持，即可自行调整某些设置。 其他设置需要贵组织的 IT 管理员提供支持。
