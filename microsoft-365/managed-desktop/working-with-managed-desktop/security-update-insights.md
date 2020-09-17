---
title: Windows 安全更新见解
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 772d1d52e977a067ff9bc3517de9cb2ae6c8c9a3
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950363"
---
# <a name="windows-security-update-insights"></a>Windows 安全更新见解
此视图概述了 Microsoft 托管桌面设备的安全更新状态。 

若要查看使用率数据，请选择 " <strong>Windows 安全更新</strong> " 选项卡。

![Windows 安全更新窗格： "设备状态的条形图" 和 "更新版本" 在左栏中，"更新在中间一段时间内的部署进度" 和 "按部署组排列的活动设备百分比" 以及 "在右列中到达95% 部署目标所需的天数"。](../../media/update-insights.jpg)

## <a name="device-status"></a>设备状态

对于要通过 Windows 更新进行更新的设备，必须将其连接到 Internet，且不能至少在6小时内休眠，其中两个必须是连续的。 只要设备已连接且不处于休眠状态，就认为 "正在使用"。 尽管可能会更新不符合这些要求的设备，但满足它们的设备的更新可能性最高。 

我们使用以下术语在 Windows Update 的上下文中对设备活动进行分类：

- <strong>Active：</strong> 满足最小使用标准的设备 (6 小时，两个连续) 用于最新的安全更新版本，并在 Microsoft Intune 中至少每五天签入一次
- 已<strong>同步：</strong>在最近28天内使用 Intune 签入的设备
- 不<strong>同步：</strong>最近28天内<i>未</i>使用 Intune 签入的设备




## <a name="update-version-status"></a>更新版本状态

Microsoft 每月的第二个星期二发布安全更新。 每个版本都添加了已知安全漏洞的重要更新。 Microsoft 托管桌面可确保每月使用最新的可用安全更新更新95% 的托管设备。 有时会在其他时间发布安全更新，以迫切解决新威胁。 Microsoft 托管桌面以类似的方式部署这些更新。

我们将安全更新版本的状态分类为以下术语：

- <strong>Current：</strong> 运行当前月发布的更新的设备
- <strong>上一个：</strong> 运行上个月发布的更新的设备
- <strong>较旧：</strong> 运行上个月之前发布的任何安全更新的设备

您应该会看到 <strong>较旧</strong> 类别中的几个设备-较大或增加的总体可能表示系统问题，您应报告给 Microsoft 托管桌面，以便我们可以进行调查。


## <a name="deployment-progress"></a>部署进度

在每个安全更新发布周期开始时，Microsoft 托管桌面将获取设备填充的快照，并将其部署目标设置为该总体的95%。 <strong>部署进度</strong>区域显示一个历史趋势，每日更新一次，跟踪更新部署满足每个版本的此目标的程度。 此图仅显示具有活动状态的设备。

您可以使用右上角的下拉菜单查看以前的更新周期的此数据。 您在此菜单中选择的时间段适用于整个页面上的所有信息。

" <strong>按部署更新的活动设备" 组</strong> 区域通过显示每个 Microsoft 托管桌面部署组的更新安装进度，提供了一个不同的视图。

<strong>到达目标</strong>区域的天数显示要使用当前安全更新更新的设备总数的95% 所花的时间。 在部署过程中，此区域显示 <strong>更新</strong> ，直到达到选定更新的95% 目标为止。

## <a name="device-details-area"></a>设备详细信息区域

仪表板的底部是显示设备的详细信息的表格，其中包括 [设备状态](#device-status) 和 [更新版本状态](#update-version-status)。 您可以搜索此列表，也可以按任何列出的值对其进行筛选。


![显示设备名称、分配的用户、设备状态、更新版本、操作系统版本以及设备上次同步日期的列的设备详细信息表。](../../media/security-update-insights-device-table-sterile.png)
