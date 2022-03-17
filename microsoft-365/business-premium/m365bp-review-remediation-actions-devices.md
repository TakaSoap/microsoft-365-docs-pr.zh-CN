---
title: 查看修复方法中的Microsoft 365 商业高级版
description: 了解如何在操作中心查看自动采取的修正或等待审批的修正
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 160cef2ec7691fbc9debad809b20461a0d3efe23
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526632"
---
# <a name="review-remediation-actions-in-microsoft-365-business-premium"></a>查看修复方法中的Microsoft 365 商业高级版

检测到威胁时，修正操作将生效。 根据特定威胁和安全设置的配置方式，可能会自动执行修正操作，或仅在获得批准后执行修正操作。 修正操作的示例包括将文件发送到隔离区、阻止进程运行以及删除计划任务。 所有修正操作都跟踪在操作中心中，位于 。[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)

:::image type="content" source="../media/defender-business/mdb-actioncenter.png" alt-text="M365 中操作中心的屏幕截图。":::

**本文介绍**：

- [如何使用操作中心](#how-to-use-your-action-center)

- [修正操作的类型](#types-of-remediation-actions)


## <a name="how-to-use-your-action-center"></a>如何使用操作中心

1. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。

2. 在“导航”窗格中，选择“操作中心”。

3. 选择" **挂起** "选项卡以查看和批准 (或拒绝) 挂起的操作。 此类操作可能源自防病毒/反恶意软件保护、自动调查、手动响应活动或实时响应会话。

4. 选择 **"历史记录** "选项卡以查看已完成操作的列表。 

## <a name="types-of-remediation-actions"></a>修正操作的类型

你的订阅包括多种不同类型的针对检测到的威胁的修正操作。 这些操作包括手动响应操作、自动调查后的操作和实时响应操作。

下表列出了可用的修正操作：

| Source  | 操作  |
|---------|---------|
| [自动调查](../security/defender-endpoint/automated-investigations.md)      | - 隔离文件 <br/>- 删除注册表项 <br/>- 终止进程 <br/>- 停止服务 <br/>- 禁用驱动程序 <br/>- 删除计划任务        |
| [手动响应操作](../security/defender-endpoint/respond-machine-alerts.md)   | - 运行防病毒扫描 <br/>- 隔离设备 <br/>- 停止和隔离 <br/>- 添加指示器以阻止或允许文件       |
| [实时响应](../security/defender-endpoint/live-response.md)   | - 收集取证数据 <br/>- 分析文件 <br/>- 运行脚本 <br/>- 将可疑实体发送到 Microsoft 进行分析 <br/>- 修正文件 <br/>- 主动搜寻威胁         |
