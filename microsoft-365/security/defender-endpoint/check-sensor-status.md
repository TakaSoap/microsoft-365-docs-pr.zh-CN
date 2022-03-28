---
title: 在 Microsoft Defender for Endpoint 中检查传感器的运行状况
description: 检查设备的传感器运行状况，以确定哪些设备配置不正确、处于非活动状态或未报告传感器数据。
keywords: 传感器， 传感器运行状况， 错误配置， 非活动， 无传感器数据， 传感器数据， 通信受损， 通信
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: bba5fde870b2916501f4154c6ff628a0d2e3ff1f
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465442"
---
# <a name="check-sensor-health-state-at-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中检查传感器的运行状况

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-checksensor-abovefoldlink)。

" **具有传感器问题的设备"** 磁贴位于安全操作仪表板上。 此磁贴提供有关单个设备提供传感器数据并与 Defender for Endpoint 服务通信的能力的信息。 它报告需要关注的设备数、帮助识别有问题的设备，并采取措施更正已知问题。

磁贴上有两个状态指示器，它们提供有关未正确向服务报告的设备数量的信息：

- **配置错误** - 这些设备可能部分向 Defender for Endpoint 服务报告传感器数据，并且可能有需要更正的配置错误。
- **非** 活动 - 在过去一个月内停止向 Defender for Endpoint 服务报告超过七天的设备。

单击任何组将你引导到 **"设备"列表**，该列表根据你的选择进行筛选。

:::image type="content" source="images/atp-devices-with-sensor-issues-tile.png" alt-text="具有传感器问题的设备图块" lightbox="images/atp-devices-with-sensor-issues-tile.png":::

在 **"设备"** 列表中，可以按以下状态筛选运行状况列表：

- **Active** - 主动向 Defender for Endpoint 服务报告的设备。
- **错误配置** - 这些设备可能部分向 Defender for Endpoint 服务报告传感器数据，但具有需要更正的配置错误。 配置错误的设备可能具有下列问题之一或多个问题组合：
  - **无传感器数据** - 设备已停止发送传感器数据。 设备可能会触发有限的警报。
  - **通信受损** - 与设备通信的能力受损。 发送文件进行深度分析、阻止文件、从网络隔离设备以及其他需要与设备通信的操作可能工作不正常。
- **非** 活动 - 停止向 Defender for Endpoint 服务报告的设备。

您还可以使用导出功能以 CSV 格式下载 **整个** 列表。 有关筛选器详细信息，请参阅 [查看和组织设备列表](machines-view-overview.md)。

> [!NOTE]
> 导出 CSV 格式的列表以显示未筛选的数据。 CSV 文件将包含组织的所有设备，而不考虑视图本身应用的任何筛选，并且可能需要大量时间来下载，具体取决于组织的大小。

:::image type="content" source="images/atp-devices-list-page.png" alt-text="&quot;设备&quot;列表页中的&quot;导出&quot;选项卡" lightbox="images/atp-devices-list-page.png":::

单击错误配置或不活动的设备时，可以查看设备详细信息。

## <a name="see-also"></a>另请参阅

- [修复 Defender for Endpoint 中的不正常传感器](fix-unhealthy-sensors.md)
- [客户端分析器概述](overview-client-analyzer.md)
- [下载并运行分析器](download-client-analyzer.md)
- [在 Windows 上运行客户端分析器](run-analyzer-windows.md)
- [在 macOS 或 Linux 上运行客户端分析器](run-analyzer-macos-linux.md)
- [用于在 Windows 上进行高级故障排除的数据收集](data-collection-analyzer.md)
