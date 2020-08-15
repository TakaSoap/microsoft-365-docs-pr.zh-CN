---
title: Contoso Windows 10 企业版部署
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft Endpoint Configuration Manager 来部署 Windows 10 企业版的就地升级。
ms.openlocfilehash: a100eb07408053fd270c26f388265696549fff9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686414"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Contoso Windows 10 企业版部署

在 Microsoft 365 for enterprise 的广泛部署之前，Contoso 拥有运行 Windows 7 (10% ) 的 Windows 兼容的电脑和设备，Windows 8.1 (65% ) 和 Windows 10 (25% ) 。Contoso 希望升级其适用于 Windows 10 企业版的电脑，利用高级安全措施，并通过自动部署更新降低 IT 开销。 

在评估其基础结构和业务需求之后，Contoso 确定了这些部署的关键要求：

- 应有尽可能多的电脑和设备运行 Windows 10 企业版
- 就地升级的推广利用了现有的 Configuration Manager 基础结构
- 控制哪些版本的 Windows 10 企业版的部署和更新是通过环来完成的
- 电脑和设备应保持最新的更新、使用最低的 IT 管理成本，并尽量减少对最终用户带来的影响

最新更新定义为满足 Contoso 业务需求的受支持的 Windows 10 企业版，这可能不同于使所有 Windows 兼容的电脑运行最新版本的 Windows 10 企业版。

## <a name="deployment-tools"></a>部署工具

在 Windows 10 企业版就地升级之前和升级期间，Contoso 使用下列 Windows Analytics 解决方案：

- 升级就绪情况  

  收集系统、应用程序和驱动程序数据进行分析，然后识别可能阻止升级的兼容性问题，并建议修复 Microsoft 已知问题。

- 更新合规性  

  显示有关 Windows 更新的设备状态，以便你可以根据需要确保它们位于最新的更新中。

- 设备运行状况  

  识别由于经常崩溃而可能需要重新生成或替换的设备以及导致设备崩溃的设备驱动程序，还包括有关这些驱动程序的可减少崩溃次数的替代版本建议。 提供 Windows 信息保护错误配置的通知，向最终用户发送相关提示。
 
Contoso 具有一个现有的 Configuration Manager (Current Branch) 基础结构。Configuration Manager 针对大型环境进行扩展，并在安装、更新和设置过程中提供广泛的控制。它还具有内置功能，能够更为轻松和高效地部署和管理 Windows 10 企业版。

## <a name="planning-process"></a>规划过程

在部署之前，Contoso 定义以下环：

- 进行验证和部署暂存的三个环 
  - 一个用于预览版本 
  - 一个用于新发布版本
  - 一个用于以前的版本 
- 一个环基于验证环中的数据，用于广泛部署 Windows 10 企业版

此外，Contoso 还使用 Windows Analytics 的升级就绪情况解决方案来确定安装的应用集及其与 Windows 10 企业版的兼容性。

## <a name="deployment-process"></a>部署过程

若要完成 Windows 10 企业版的就地升级部署，Contoso 实施了以下过程，其中包括来自 Microsoft 的最佳做法建议：

1. 为 Configuration Manager 启用对等缓存。
2. 基于来自批量许可服务中心的图像创建自定义 Windows 程序包。
3. Configuration Manager 用于跨网络向分发点部署 Windows 包，并向三个验证和部署暂存环部署内部版本。
4. 使用 Windows Analytics 的设备运行状况和更新合规性解决方案，为三个验证和部署暂存环中的电脑和设备执行成功评估。
5. 基于 Windows Analytics 信息，Contoso 已确定 Windows 10 企业版将部署到广泛部署环的版本。
6. 运行 Configuration Manager 部署任务序列，将选定的 Windows 包部署到广泛部署环中。
7. 使用可解决问题的设备运行状况和更新合规性解决方案来监视广泛部署环中的电脑和设备。

下面是 Contoso 的就地升级和持续更新部署体系结构。

![Contoso 的 Windows 10 企业版部署基础结构](../media/contoso-win10/contoso-win10-fig1.png)

此基础结构的组成部分：

- Configuration Manager：
  - 从 Microsoft 网络的 Microsoft 批量许可中心获取 Windows 10 企业版包的图像。
  - 是用于部署包的集中管理点。
- 通常位于 Contoso 区域中心办事处的区域分发点。
- 不同位置的 Windows 电脑和设备接收和安装部署包，用于就地升级或基于环成员的持续更新。

## <a name="next-step"></a>后续步骤

[了解](contoso-o365pp.md) Contoso 如何利用其 Configuration Manager 基础结构在组织中部署 Microsoft 365 企业应用版并使之保持最新。 

## <a name="see-also"></a>另请参阅

[Windows 10 企业版](https://docs.microsoft.com/windows/deployment/)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)
