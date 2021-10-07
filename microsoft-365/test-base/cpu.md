---
title: CPU 回归分析
description: 了解 CPU 消耗的回归结果和指标
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 935781e929c159918f8a0aec3b4a551ab974480f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60180611"
---
# <a name="intelligent-cpu-regression-analysis"></a>智能 CPU 回归分析

CPU 使用率可以指示应用程序是否受操作系统更新的影响。 

Microsoft 365 测试基础为软件开发人员提供了 CPU 性能回归的见解，当其应用程序在即将推出的 Windows 操作系统 (操作系统更新的不同版本上运行时) 回归。 

这些 CPU 回归使开发人员 (在广泛部署操作系统更新) 并解决应用程序问题，从而防止最终用户遇到不良体验。


### <a name="how-cpu-regression-analysis-works"></a>CPU 回归分析的工作原理 ###

作为测试基础用户，你可以将应用程序的二进制文件 (上载到单个 .zip 文件) 以及关联的测试脚本，并选择你要在 Azure 上的测试基础门户上测试应用程序的 Windows 操作系统版本。 

然后，测试基础服务运行测试脚本并执行 CPU **回归分析**。 

该服务检查目标操作系统更新的预发布版本上的应用程序的 CPU 使用率是否与已发布版本的操作系统的 CPU 使用率一起。 

CPU 使用率不是 100% 的类似比较，因为操作系统的两个版本上运行的进程可能完全匹配，也可能不完全匹配，因为操作系统版本不同;但是，测试基础执行的分析可以显示应用程序的 CPU 使用率是否受即将推出的操作系统更新的影响，特别是哪些进程已从以前的测试运行中进行了回归。

在下面的快照中，有两个操作系统版本针对这两个操作系统版本比较同一应用程序的 CPU 使用率。 
-   "CPU 使用率"选项卡分别显示两个发行版的使用率的上限和下限（分别为第 90 个和 10 个百分点）。 
-   图中显示了 CPU 使用率的时间系列以及平均使用率。 

客户现在可以使用该功能来确定其应用程序的 CPU 使用率是否受操作系统更新的影响，特别是哪些进程已从以前的执行中回归。


![CPU 回归分析。](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a>相关流程标识 ###

下面我们将讨论如何在应用程序中标识已回归进程。 

分析性能回归需要跟踪测试运行期间在虚拟机上运行的每种进程不同类型的性能计数器。 

此类分析为给定应用程序的很多进程捕获大量变量。 并非所有进程都与一个运行或应用程序关联。 为了应对这一挑战，应用了一种使用概率和信息理论上的相互信息排名算法，以找出与给定应用程序最相关的过程。 

当进程被视为另一种离散随机变量时，应用程序可被视为一种类型的离散随机变量。 使用相关性的条件概率测量两个随机变量的关联。 

然后，进程按其与每个应用程序的相关性顺序显示。 还可以收藏默认情况下可监视的一部分进程，以及用于 CPU 回归分析的相关进程。 一旦检测到回归分析器，就可以下载Windows分析器工具包并分析 CPU 性能回归的原因。 

Windows Performance Analyzer 将事件跟踪日志 (ETL) 作为输入，并且这些 .etl 文件在日志文件中可用，可在门户上下载用于测试运行。 如果您想了解有关调试 CPU 性能的更多信息，请参阅 Windows Performance Analyzer 文档。

