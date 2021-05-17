---
title: 电池见解
description: 显示有关预计电池使用时间以及最高功率消耗者的数据的报告
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579706"
---
# <a name="battery-insights"></a>电池见解
此视图为 Microsoft 托管桌面设备提供电源、电池以及应用使用情况指标。 出于这些目的，如果应用正在运行且具有焦点，则该应用将被视为"使用中"。

若要查看使用情况数据，请选择" **电池"** 选项卡。

![电池窗格：预测左上角每个设备型号的电池使用时间，顶部能耗 (按应用) 右上角的见解表显示。 右上方的文档链接](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>预计电池使用时间

在 **"预测电池使用时间** "区域中，我们按设备模型组织，提供设备的预期电池使用时间预测。

> [!NOTE]
> 此数据派生自 Microsoft 托管桌面部署中同时报告数据的随机选择设备的采样能耗<em></em>、使用时间和电池容量。

该表提供预计的电池使用时间 (小时) 、其他 Microsoft 托管桌面部署中相同型号的平均电池使用时间，以及环境中报告此数据的设备数量。 通过选择列标题对数据进行排序。



## <a name="top-energy-consumers"></a>顶级能源使用者

在 **主要能源** 使用者区域中，你将发现环境中消耗最多能耗的应用以每千米 (mWh) 。 显示的应用是按特定设备显示的，你在左侧的"预测电池使用 **时间"部分中** 选择这些应用。 例如，若要查看 Microsoft Surface Book 2 设备每应用消耗，请在电池使用时间区域中选择该行。 如果未选择任何模型，则显示的应用使用数据适用于我们具有共同数据的所有应用。

 对于每个应用，彩色分段显示应用在以下类别中的能耗使用分布：

- CPU
- 显示器
- 网络
- 其他

"其他"可能包括各种来源的能耗，如磁盘活动、移动宽带使用情况和内部抵制消耗的能耗。 

可以使用右上角的菜单筛选此视图以仅显示前台应用和/或后台应用。 前台应用是过去 28 天内具有用户交互的应用，例如使用鼠标选择内容。

## <a name="insights"></a>见解

**Insights** 区域显示了 CPU 和网络类别中前三个能源使用者。 与所有 Microsoft 托管桌面部署相比，这些项目消耗的能耗高于平均能耗。 我们不显示显示资源，因为它很大程度上取决于设备使用时间和屏幕亮度设置。 

有关详细信息，请选择" **详细信息"** 列中的一览。

## <a name="battery-optimization"></a>电池优化

Windows 10 提供 [大量设备设置](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) ，以改进电源使用并提高 Microsoft 托管桌面设备的电池使用时间。 其中某些设置可能会降低其他 Windows 功能，因此你还必须考虑其他因素，例如设备在组织中的角色。 Windows 支持人员维护这些电池节省 [提示的列表](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)。

用户可以自行调整某些设置，而无需管理员提升或支持。 其他设置需要组织的 IT 管理员提供支持。
