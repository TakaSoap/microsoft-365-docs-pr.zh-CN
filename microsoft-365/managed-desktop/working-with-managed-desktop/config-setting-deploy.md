---
title: 在部署中部署可Microsoft 托管桌面
description: 部署和跟踪 Microsoft 托管桌面 中的可配置Microsoft 托管桌面。
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、部署、分步部署、可配置设置
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 4950afb8446eb9b687749fc657a6826bb1eb7768
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035434"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>部署和跟踪可配置设置 - Microsoft 托管桌面

对设置类别进行更改并部署后，"部署状态"页允许您开始将设置部署到组。 此页面显示每个可配置设置的摘要。 通过打开设置类别，可以将设置部署到组并跟踪这些部署的进度。

## <a name="deployment-statuses"></a>部署状态

这些状态将针对每个部署显示。

Status | 说明
--- | ---
部署 | 您的更改正在等待部署到此组。
正在进行 | 更改将应用于此组的活动设备。
完成 | 此组中所有活动设备上完成更改。
已失败 | 更改在组中 10% 的活动设备上失败，因此部署已停止。<br><br> 将自动打开支持请求，Microsoft 托管桌面操作解决部署问题。
已还原 | 更改已还原为已成功部署到所有部署组的最后一个更改。

## <a name="deploy-changes"></a>部署更改

我们将在这些说明中显示桌面背景图片。 在部署阶段后，从"部署状态"页部署更改。

**部署更改**

1. 登录 ["Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并导航到 **"设备"** 菜单
2. 查找"Microsoft 托管桌面"部分，选择 **"设置"。**
3. 在 **"部署** 状态工作区"中，选择要部署的设置，然后选择要部署的分步部署。
4. 选择 **"** 部署"将更改部署到其中一个部署组。

> [!NOTE]
> 橙色警告图标表示有上一个组可供部署，建议按顺序排列。

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

我们建议按此顺序部署到部署组：Test、First、Fast 和 Broad。 

在每个组中完成更改后，状态将更改为 **"完成"。**

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>还原部署

部署更改后，可以从部署状态 **还原**。 当还原为"正在进行"或"已完成 **"** 更改时，当前部署将停止。  该设置将恢复为部署到所有组的上一版本。

我们将以桌面背景图片为例，显示还原更改的步骤。 

**还原更改**

1. 登录 ["Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并导航到 **"设备"** 菜单
2. 查找"Microsoft 托管桌面"部分，选择 **"设置"。**
3. 在 **"部署** 状态工作区"中，选择要还原的设置，然后选择要还原的分步部署。
4. 在 **"需要还原此更改？"下，** 选择"**还原部署"。**

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>其他资源

- [可配置的设置概述](config-setting-overview.md)
- [可配置设置参考](config-setting-ref.md) 
