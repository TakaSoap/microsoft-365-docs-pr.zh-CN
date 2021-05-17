---
title: Windows 安全更新见解
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941437"
---
# <a name="windows-security-update-insights"></a>Windows 安全更新见解
此视图概述了你的移动设备的安全更新Microsoft 托管桌面状态。 

若要查看使用率数据，请选择"Windows<strong>安全更新"</strong>选项卡。

![Windows安全更新窗格：左侧列中设备状态和更新版本的条形图、在中央列中更新部署进度、按部署组更新活动设备的百分比，以及右列中达到 95% 部署目标所经过的天数。](../../media/update-insights.jpg)

## <a name="device-status"></a>设备状态

若要通过 Windows 更新来更新设备，设备必须连接到 Internet，并且至少不要休眠六个小时，其中两小时必须持续。 尽管可能会更新不满足这些要求的设备，但满足这些要求的设备更新的可能性最大。 

我们使用以下条款在更新Windows设备活动进行分类：

- <strong>活动：</strong>满足最低活动条件的设备 (六小时，连续两) 更新版本，并且至少每五天使用 Microsoft Intune签入一次
- <strong>已同步：</strong> 过去 28 天内使用 Intune 签入的设备
- <strong>不同步：</strong>过去 28 天内未使用 Intune 签入的设备<i></i>




## <a name="update-version-status"></a>更新版本状态

Microsoft 每月的第二个星期二发布安全更新。 每个版本都会添加已知安全漏洞的重要更新。 Microsoft 托管桌面确保其 95% 的托管设备每月更新最新的可用安全更新。 有时在其他时间发布安全更新，以紧急应对新威胁。 Microsoft 托管桌面部署这些更新的方式类似。

我们使用以下条款对安全更新版本的状态进行分类：

- <strong>当前：</strong> 运行本月发布的更新的设备
- <strong>上一个：</strong> 运行上个月发布的更新的设备
- <strong>较旧：</strong> 运行上个月之前发布的任何安全更新的设备

你应该看到"较旧"类别中的<strong></strong>很少设备-一个较大或不断增加群体可能指示你应向用户报告一个Microsoft 托管桌面问题，以便我们可以进行调查。


## <a name="deployment-progress"></a>部署进度

在每个安全更新发布周期开始时，Microsoft 托管桌面获取设备总体的快照，并设置其部署目标为该总体的 95%。 部署 <strong>进度</strong> 区域显示历史趋势，每日更新，跟踪更新部署在每个版本中达到此目标的进度。 此图只显示具有活动状态的设备。

可以使用右上角的下拉菜单查看上一次更新周期的数据。 在此菜单中选择的时间段适用于整个页面上的所有信息。

通过<strong>显示每个部署</strong>组更新安装的进度，"按部署组更新的活动设备"区域提供Microsoft 托管桌面视图。

" <strong>到达目标天数</strong> "区域显示使用当前安全更新更新总设备数的 95% 所用时间。 部署正在进行时，此区域会显示"仍在<strong></strong>更新"，直到达到所选更新的 95% 目标。

## <a name="device-details-area"></a>设备详细信息区域

仪表板底部是一个表格，其中显示设备的详细信息，包括设备[状态](#device-status)[和更新版本状态](#update-version-status)。 可以搜索此列表或按任何列出的值进行筛选。


![设备详细信息表显示设备名称、分配的用户、设备状态、更新版本、操作系统版本以及设备上次同步日期的列。](../../media/security-update-insights-device-table-sterile.png)
