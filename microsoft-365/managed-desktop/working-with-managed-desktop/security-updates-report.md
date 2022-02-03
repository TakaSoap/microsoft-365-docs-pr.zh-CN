---
title: Windows 安全更新报告
description: 说明此报告中显示的信息
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: d20a10fa1fb645763f6eec20f52b4c9e4fe294a1
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322417"
---
# <a name="windows-security-updates-report"></a>Windows 安全更新报告

此报告概述了针对你的 Microsoft 托管桌面 设备的给定 Windows 安全更新的部署进度。

在每个安全更新发布周期开始时，Microsoft 托管桌面所有已注册设备的快照。 部署目标设置为该总体中活动 **设备的** 95%。 此图显示与平均发布日期相比所选发布日期Microsoft 托管桌面进度。

当我们关注活动群体时，还可以透视此报表以显示你的 **活动 + 同步** 和不同 **步** 设备填充。 可以通过更改可用筛选器查看早期版本的部署进度，但设备级别详细信息仅适用于当前版本。 还可导出图表后表中的设备信息，以用于脱机分析。

:::image type="content" source="../../media/mmd-security-updates.png" alt-text="显示左上方一段时间的更新安装进度的报告、右上方的筛选器（带生成报告的按钮）以及底部报告详细信息表":::

通常情况下，Microsoft 每月的第二个星期二发布安全更新。 但是，可根据需要在其他时间发布它们。 每个版本都会添加已知安全漏洞的重要更新

Microsoft 托管桌面确保每月 95% 的活动设备更新最新可用安全更新。 当安全更新程序发布后，为了紧急应对新威胁，Microsoft 托管桌面以类似方式部署这些更新。

## <a name="status-categories"></a>状态类别

我们按以下条款对安全更新版本的状态进行分类：

| 安全更新状态 | 说明 |
| ------ | ------ |
| Current | 运行本月发布的更新的设备。 |
| Previous | 运行上个月发布的更新的设备。 |
| 较旧 | 运行上个月之前发布的任何安全更新的设备。 |

> [!NOTE]
> "旧"类别中应该 **只有一些** 设备。 较大或增长的 **较早** 群体可能表示一个缺陷问题，你应该向Microsoft 托管桌面调查。
