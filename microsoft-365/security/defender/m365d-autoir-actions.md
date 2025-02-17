---
title: 在操作中心查看和管理操作
description: 使用操作中心查看和管理修正操作
keywords: 操作, 中心, autoair, 自动化, 调查, 响应, 修正
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 43c48081a86e33cd918bc4de8f01859bc1107583
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666825"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>在操作中心查看和管理操作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

Microsoft 365 Defender中的威胁防护功能可能会导致某些修正操作。 下面是一些示例：

- [自动调查](m365d-autoir.md) 可能导致自动执行或等待批准的修正操作。
- 防病毒、反恶意软件和其他威胁防护功能可能导致修正操作，例如阻止文件、URL 或进程，或将项目发送到隔离区。
- 安全运营团队可以手动执行修正操作，例如在 [高级搜寻](advanced-hunting-overview.md) 期间或调查 [警报](investigate-alerts.md) 或 [事件](investigate-incidents.md)期间。

> [!NOTE]
> 必须具有[相应的权限](m365d-action-center.md#required-permissions-for-action-center-tasks)才能批准或拒绝修正操作。 有关详细信息，请参阅 [先决条件](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。

## <a name="review-pending-actions-in-the-action-center"></a>在操作中心查看挂起的操作

应尽快批准（或拒绝）挂起的操作，以便自动调查可以继续并及时完成。 

1. 转到<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>并登录。 

2. 在“导航”窗格中，选择“操作中心”。 

3. 在操作中心中的 **"挂起"** 选项卡上，选择列表中的项。 其浮出窗格随即打开。 下面是一个示例。

   :::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="批准或拒绝操作的选项" lightbox="../../media/air-actioncenter-itemselected.png":::

4. 查看浮出窗格中的信息，然后执行以下步骤之一：
   - 选择 **"打开调查"页** 可查看有关调查的更多详细信息。
   - 选择 **"批准** "以启动挂起的操作。
   - 选择 **"拒绝** "可防止执行挂起的操作。
   - 选择 **"去狩猎** "以进入 [高级搜寻](advanced-hunting-overview.md)。 

## <a name="undo-completed-actions"></a>撤消已完成的操作

如果确定设备或文件不是威胁，则可以撤消已执行的修正操作，无论这些操作是自动执行还是手动执行。 在"操作中心"的 **"历史记录** "选项卡上，可以撤消以下任何操作：  

| 操作源 | 支持的操作 |
|:---|:---|
| - 自动调查 <br/>- Microsoft Defender 防病毒 <br/>- 手动响应操作 | - 隔离设备 <br/>- 限制代码执行 <br/>- 隔离文件 <br/>- 删除注册表项 <br/>- 停止服务 <br/>- 禁用驱动程序 <br/>- 删除计划的任务 |

### <a name="undo-one-remediation-action"></a>撤消一个修正操作

1. 转到操作中心 () [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 并登录。

2. 在" **历史记录** "选项卡上，选择要撤消的操作。

3. 在屏幕右侧的窗格中，选择 **"撤消**"。

### <a name="undo-multiple-remediation-actions"></a>撤消多个修正操作

1. 转到操作中心 (https://security.microsoft.com/action-center) 并登录。

2. 在 **"历史记录** "选项卡上，选择要撤消的操作。 请确保选择具有相同操作类型的项。 随即打开浮出窗格。

3. 在浮出窗格中，选择 **"撤消**"。

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>跨多个设备从隔离区中删除文件 

1. 转到操作中心 () [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 并登录。

2. 在" **历史记录** "选项卡上，选择一个具有 **隔离文件** 操作类型的文件。

3. 在屏幕右侧的窗格中，选择 **"应用到此文件的 X 更多实例**"，然后选择 **"撤消**"。

## <a name="next-steps"></a>后续步骤

- [查看自动调查的详细信息和结果](m365d-autoir-results.md)
- [解决误报或误报](m365d-autoir-report-false-positives-negatives.md)
