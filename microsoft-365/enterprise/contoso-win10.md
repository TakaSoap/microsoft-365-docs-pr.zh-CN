---
title: Contoso Windows 10 企业版部署
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft Endpoint Configuration Manager 来部署 Windows 10 企业版的就地升级。
ms.openlocfilehash: 7fe6efd176e156b75337ba79db6c1db839b0ed03
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208309"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Contoso Windows 10 企业版部署

在广泛推出 Microsoft 365 企业版之前，Contoso 具有混合运行 Windows 7 (10%) 、Windows 8.1 (65%) 和 Windows 10 (25%) 的 Windows 兼容电脑和设备。 Contoso 希望升级其电脑Windows 10 企业版利用高级安全性并降低自动部署更新的 IT 开销。 

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

Contoso 使用 Windows Analytics 中的升级就绪情况来确定已安装的应用集及其与 Windows 10 企业版 的兼容性。

## <a name="deployment-process"></a>部署过程

若要完成 Windows 10 企业版的就地升级部署，Contoso 实施了以下过程，其中包括来自 Microsoft 的最佳做法建议：

1. 为 Configuration Manager 启用对等缓存。
2. 基于来自批量许可服务中心的图像创建自定义 Windows 程序包。
3. 使用 Configuration Manager 将 Windows 包部署到跨其网络的分发点，将内部版本部署到三个验证和部署暂存组。
4. 使用 Windows Analytics 的设备运行状况和更新合规性解决方案，为三个验证和部署暂存环中的电脑和设备执行成功评估。
5. 基于 Windows 分析信息，Contoso 确定了Windows 10 企业版广泛部署组部署的版本。
6. 运行 Configuration Manager 部署任务序列，将Windows包部署到广泛部署组。
7. 使用设备运行状况和更新合规性解决方案来解决问题，监视广泛部署组中电脑和设备。

下面是 Contoso 的就地升级和持续更新部署体系结构。

![Contoso Windows 10 企业版基础结构。](../media/contoso-win10/contoso-win10-fig1.png)

此基础结构的组成部分：

- Configuration Manager：
  - 从 Microsoft 网络的 Microsoft 批量许可中心获取 Windows 10 企业版包的图像。
  - 是用于部署包的集中管理点。
- 通常位于 Contoso 区域中心办事处的区域分发点。
- Windows不同位置接收和安装部署包（基于组成员身份进行就地升级或持续更新）的 PC 和设备。

## <a name="next-step"></a>后续步骤

了解 Contoso 如何利用其 Configuration Manager[](contoso-o365pp.md)基础结构在整个组织中部署Microsoft 365 企业应用版保持最新状态。 

## <a name="see-also"></a>另请参阅

[Windows 10 企业版](/windows/deployment/)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)