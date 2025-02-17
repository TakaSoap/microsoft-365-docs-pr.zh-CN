---
title: 查看 Microsoft Defender for Business 中的修正操作
description: 查看自动采取的修正或在操作中心等待审批的修正
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 03/10/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: b5bb61d4a0b8f3cb0732633463fbf2c96ec258e9
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525510"
---
# <a name="review-remediation-actions-in-the-action-center"></a>查看操作中心中的修正操作

> [!IMPORTANT]
> 从 2022 年 3 [月](../../business-premium/index.md) 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

检测到威胁时，修正操作将生效。 根据特定威胁和安全设置的配置方式，可能会自动执行修正操作，或仅在获得批准后执行修正操作。 修正操作的示例包括将文件发送到隔离区、阻止进程运行以及删除计划任务。 所有修正操作在操作中心进行跟踪。

:::image type="content" source="../../media/defender-business/mdb-actioncenter.png" alt-text="操作中心的屏幕截图":::

**本文介绍**：

- [如何使用操作中心](#how-to-use-the-action-center)

- [修正操作](#remediation-actions)

>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="how-to-use-the-action-center"></a>如何使用操作中心

1. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。

2. 在“导航”窗格中，选择“操作中心”。

3. 选择" **挂起** "选项卡以查看和批准 (或拒绝) 挂起的操作。 此类操作可能源自防病毒/反恶意软件保护、自动调查、手动响应活动或实时响应会话。

4. 选择 **"历史记录** "选项卡以查看已完成操作的列表。 

## <a name="remediation-actions"></a>修正操作

Microsoft Defender for Business 包括若干修正操作。 这些操作包括手动响应操作、自动调查后的操作和实时响应操作。

下表列出了可用的修正操作：

| Source  | 操作  |
|---------|---------|
| [自动调查](../defender-endpoint/automated-investigations.md)      | - 隔离文件 <br/>- 删除注册表项 <br/>- 终止进程 <br/>- 停止服务 <br/>- 禁用驱动程序 <br/>- 删除计划任务        |
| [手动响应操作](../defender-endpoint/respond-machine-alerts.md)   | - 运行防病毒扫描 <br/>- 隔离设备 <br/>- 停止和隔离 <br/>- 添加指示器以阻止或允许文件       |
| [实时响应](../defender-endpoint/live-response.md)   | - 收集取证数据 <br/>- 分析文件 <br/>- 运行脚本 <br/>- 将可疑实体发送到 Microsoft 进行分析 <br/>- 修正文件 <br/>- 主动搜寻威胁         |

## <a name="next-steps"></a>后续步骤

- [响应和缓解 Microsoft Defender for Business 中的威胁](mdb-respond-mitigate-threats.md)

- [在 Microsoft Defender for Business 中管理设备](mdb-manage-devices.md)