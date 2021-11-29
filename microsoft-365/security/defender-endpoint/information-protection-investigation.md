---
title: 使用敏感度标签确定事件响应的优先级
description: 了解如何使用敏感度标签确定事件的优先级并调查事件
keywords: 信息， 保护， 数据， 丢失， 防护， 标签， dlp， 事件， 调查， 调查
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
ms.technology: mde
ms.openlocfilehash: 8a1cafe4cd54b7313e0555127221173e23a41bbf
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/29/2021
ms.locfileid: "61217706"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a>使用敏感度标签确定事件响应的优先级

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

典型的高级永久性威胁生命周期涉及数据外接。 在安全事件中，必须能够优先考虑敏感文件可能受到威胁的调查，以便保护公司数据和信息。

Defender for Endpoint 使用敏感度标签可帮助简化安全事件的优先顺序。 敏感度标签可快速识别可能涉及包含敏感信息（如机密信息）的设备的事件。

## <a name="investigate-incidents-that-involve-sensitive-data"></a>调查涉及敏感数据的事件

了解如何使用数据敏感度标签确定事件调查的优先级。

> [!NOTE]
> 检测到标签Windows 10 版本 1809或更高版本，Windows 11。

1. 在Microsoft 365 Defender门户中，选择"**事件&事件** \> **"。**

2. 滚动到右侧以查看" **数据敏感度"** 列。 此列反映与事件相关的设备上观察到的敏感度标签，用于指示敏感文件是否受事件影响。

    ![数据敏感度列的图像。](images/data-sensitivity-column.png)

    还可以根据数据敏感度 **进行筛选**

    ![数据敏感度筛选器的图像。](images/data-sensitivity-filter.png)

3. 打开事件页面以进一步调查。

    ![事件页面详细信息的图像。](images/incident-page.png)

4. 选择 **"设备"** 选项卡以标识使用敏感度标签存储文件的设备。

    ![设备选项卡的图像。](images/investigate-devices-tab.png)

5. 选择存储敏感数据的设备，并搜索时间线以确定哪些文件可能会受到影响，然后采取相应的措施以确保数据受到保护。

   可以通过搜索数据敏感度标签来缩小设备时间线上显示的事件范围。 执行此操作将只显示与已说出标签名称的文件关联的事件。

    ![设备时间线的图像，根据标签缩小搜索结果范围。](images/machine-timeline-labels.png)

> [!TIP]
> 这些数据点还通过高级搜寻中的"DeviceFileEvents"公开，从而允许高级查询和计划检测考虑敏感度标签和文件保护状态。
