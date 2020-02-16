---
title: 在 Microsoft 托管桌面中部署可配置的设置
description: 在 Microsoft 托管桌面中部署和跟踪可配置的设置更改。
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档，部署，暂存部署，可配置的设置
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e6946c138cb6fde15e35374b447038d5c302187e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085745"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>部署和跟踪可配置的设置-Microsoft 托管桌面

在更改设置类别并暂存部署后，"部署状态" 页允许您开始将设置部署到组。 此页面显示每个可配置设置的摘要。 通过打开设置类别，您可以将设置部署到组，并跟踪这些部署的进度。

## <a name="deployment-statuses"></a>部署状态 

这些是你将看到的每个部署的状态。

状态  | 说明 
--- | --- 
部署 | 您的更改正在等待部署到此组。
进行中 | 正在将更改应用到此组中的活动设备。 
完全 | 此组中所有活动设备上的更改已完成。 
Failed | 此更改在组中的10% 的活动设备上失败，因此部署已停止。<br><br> 将使用 Microsoft 托管桌面操作自动打开支持请求，以排除部署故障。 
回复 | 更改已还原为已成功部署到所有部署组的最后更改。

## <a name="deploy-changes"></a>部署更改

我们将在这些说明中显示桌面背景图片。 暂存部署后，从 "部署状态" 页部署更改。 

**部署更改**

1. 登录到[Microsoft 托管桌面管理门户](https://aka.ms/mwaasportal)
2. 在 "**设置**" 下，选择 "**可配置**"。
3. 在 "**部署状态**" 工作区中，选择要部署的设置，然后选择要部署的暂存部署。
4. 选择 "**部署**" 以将更改部署到其中一个部署组。

> [!NOTE] 
> 橙色警告图标表示有一个可供部署的以前的组，因此建议按顺序执行。 

![部署状态工作区。 右侧的 "受信任的网站" 窗格。 "部署组" 部分包含三列：部署组、设备和状态。 在 "状态" 列中，突出显示 "部署"。](../../media/1deployedit.png)
我们建议按以下顺序部署到部署组： Test、First、Fast 和广义。 

当每个组中的更改完成后，状态将更改为 "**完成**"。

![包含日期更新、版本、测试、首、快速和广泛的列的部署状态工作区。 将展开代理行，并在四个部署组中显示标记为 "complete" 的日期设置。](../../media/2completeedit.png)

## <a name="revert-deployment"></a>还原部署

部署更改后，可以从**部署状态**恢复。 还原正在**进行**或已**完成**的更改时，当前部署将停止。 设置将还原为所有组部署的最后一个版本。 

我们将显示使用桌面背景图片作为示例还原更改的步骤。 

**还原更改**
1. 登录到[Microsoft 托管桌面管理门户](https://aka.ms/mwaasportal)
2. 在 "**设置**" 下，选择 "**可配置**"。
3. 在 "**部署状态**" 工作区中，选择要还原的设置，然后选择要还原的暂存部署。
4. 在 "**需要还原此更改？**" 下，选择 "**还原部署**"。

![部署状态工作区。 "浏览器起始页" 已选中，在右侧打开一个窗格，其中包含有关已提交的更改及其状态的数据。 底部是 "需要还原此更改" 区域，可在其中选择 "还原部署"。](../../media/3revert.png) 

## <a name="additional-resources"></a>其他资源
- [可配置的设置概述](config-setting-overview.md)
- [可配置设置参考](config-setting-ref.md) 
