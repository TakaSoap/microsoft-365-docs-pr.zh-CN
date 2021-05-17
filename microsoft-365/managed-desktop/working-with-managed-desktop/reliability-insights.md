---
title: 可靠性见解
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950338"
---
# <a name="reliability-insights"></a>可靠性见解

此视图提供了托管设备的运行状况摘要。 若要查看可靠性数据，请选择"可靠性 **"** 选项卡。


![可靠性窗格：左上方设备的可靠性、右上角的时间图的可靠性、底部顶部问题表。 右下角的帮助和反馈按钮。](../../media/insights_reliability.png)

" **跨设备** 的可靠性"部分通过报告被视为"正常运行"的设备百分比和自上次报告故障以来观察到的平均值，提供过去 14 天内部署的快速运行状况摘要。 

 
右侧 **"时间可靠性** "图报告具有严重错误的设备数以及随着时间的推移观察到的关键错误总数。

" **主要问题** "部分详细介绍了检测到的特定问题，这些问题会影响至少 5% 的托管设备。 报告的详细信息包括：

- 问题类型
    - 应用程序崩溃，导致应用停止运行或意外停止
    - 应用程序挂起，其中应用程序停止响应输入
    - 严重错误，当 Windows 遇到无法恢复的问题时发生
- 受同一问题影响的设备数量
- 数字表示的托管设备的百分比
- 特定问题的总发生次数
- 似乎是问题源的软件组件
- 检测到的问题的类别：
    - 浏览器 (Edge、Chrome、IE) 
    - 未知 (非 Microsoft 组件) 
    - 驱动程序 (音频、图形或其他驱动程序) 
    - Productivity (Slack、G-Suites、Microsoft Office 及其加载项或扩展、Teams) 
    - 媒体 (图像、音乐或视频应用
    - 安全 (Windows 安全组件) 
- Microsoft 托管桌面操作调查和修正问题的当前状态

