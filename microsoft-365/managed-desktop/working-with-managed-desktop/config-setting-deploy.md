---
title: 在 Microsoft 托管桌面中部署可配置的设置
description: 在 Microsoft 托管桌面中部署和跟踪可配置的设置更改。
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档, 部署, 暂存部署, 可配置的设置
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 62a17c95f5dc6b11f446a27684c507d7aaa95b7b
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414162"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>部署和跟踪可配置的设置-Microsoft 托管桌面

在更改设置类别并暂存部署后, 您可以部署和跟踪部署状态的部署进度。 此页面显示每个可配置设置的摘要。 打开设置类别以查看每个部署及其详细信息, 以部署更改。 

## <a name="deployment-statuses"></a>部署状态 

这些是你将看到的每个部署的 statues。

Status  | 说明 
--- | --- 
部署 | 您所做的更改正在等待部署到此环。
进行中 | 正在将更改应用到此环中的活动设备。 
完全 | 此环中所有活动设备上的更改已完成。 
Failed | 更改在环中的 10% 活动设备上失败, 因此部署已停止。<br><br> 将使用 Microsoft 托管桌面操作自动打开支持请求, 以排除部署故障。 
回复 | 更改已恢复为已成功部署到所有部署环的最后一次更改。

## <a name="deploy-changes"></a>部署更改

我们将在这些说明中显示桌面背景图片。 暂存部署后, 从部署状态部署更改。 

**部署更改**

1. 登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)
2. 在 "**设置**" 下, 选择 "**可配置**"。
3. 在 "**部署状态**" 工作区中, 选择要部署的设置, 然后选择要部署的暂存部署。
4. 选择 "**部署**" 以将更改部署到某个部署环中。

![可配置的设置部署状态概述](images/deploy-cs-overview.png)

Microsoft 托管桌面建议按此顺序部署到部署环: Test、First、Fast 和广义。 

当每个环中的更改完成时, 状态将更改为 "**完成**"。

![可配置的设置部署完成](images/config-setting-complete.png)

## <a name="revert-deployment"></a>还原部署

我们将在这些说明中显示桌面背景图片。 

部署更改后, 可以从**部署状态**恢复。 还原正在**进行**或已**完成**的更改时, 当前部署将停止。 设置将还原为所有环部署的最后一个版本。 

**还原更改**
1. 登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)
2. 在 "**设置**" 下, 选择 "**可配置**"。
3. 在 "**部署状态**" 工作区中, 选择要还原的设置, 然后选择要还原的暂存部署。
4. 在 "**需要还原此更改**" 下, 选择 "**还原部署**"。

![可配置的设置部署还原](images/config-setting-revert.png) 

## <a name="additional-resources"></a>其他资源
- [可配置的设置概述](config-setting-overview.md)
- [可配置的设置参考](config-setting-ref.md) 