---
title: 在 Microsoft Defender for Business 中查看和管理事件
description: 了解如何查看警报&、响应威胁、管理设备和查看修正操作
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 2e6edf09c781302c61e44a82e9f2d21c5ab2bc15
ms.sourcegitcommit: a216617d6ff27fe7d3089a047fbeaac5d72fd25c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "63513014"
---
# <a name="view-and-manage-incidents-in-microsoft-defender-for-business"></a>在 Microsoft Defender for Business 中查看和管理事件

> [!IMPORTANT]
> 从 2022 年 3 [月](../../business-premium/index.md) 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

当检测到威胁并触发警报时，将创建事件。 公司的安全团队可以在安全门户中查看和管理Microsoft 365 Defender事件。

**本文包括**：

- [如何监视事件和警报](#monitor-your-incidents--alerts)

- [警报严重性](#alert-severity)

- [后续步骤](#next-steps)

>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="monitor-your-incidents--alerts"></a>监视事件&警报

1. 在Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com)) 导航窗格中，选择"**事件"**。 已创建的任何事件都列在页面上。

   :::image type="content" source="../../media/defender-business/mdb-incidents-list.png" alt-text="&quot;事件&quot;列表的屏幕截图":::

2. 选择警报以打开其飞出窗格，可在其中了解有关警报的详细信息。 

   :::image type="content" source="../../media/defender-business/mdb-incident-flyout.png" alt-text="通过打开飞出线选择的事件的屏幕截图":::

3. 在飞出窗格中，你可以看到警报标题、查看受影响的终结点或用户帐户 (（如终结点或用户帐户) ）列表、采取可用操作，以及使用链接查看详细信息，甚至打开所选警报的详细信息页面。 

> [!TIP]
> Microsoft Defender for Business 旨在通过提供建议操作来帮助你解决检测到的威胁。 查看警报时，请查找要采取的建议操作。 还要注意警报严重性，该严重性不仅根据威胁严重性确定，还根据公司的风险级别确定。 

## <a name="alert-severity"></a>警报严重性

当Microsoft Defender 防病毒根据检测到的威胁 (恶意软件的绝对严重性) 以及受到感染的单个终结点的潜在风险 (警报严重性) 。
Microsoft Defender for Business 根据检测到的行为的严重性、终结点 (设备) 的实际风险以及更重要的是，为公司带来潜在风险来分配警报严重性。 下表列出了一些示例： <br/><br/>

| 应用场景 | 警报严重性 | Reason |
|:---|:---|:---|
| Microsoft Defender 防病毒威胁之前检测并停止威胁。 | 信息 | 威胁在损坏完成之前已停止。 |
| Microsoft Defender 防病毒检测在公司内执行的恶意软件。 恶意软件已停止并修复。 | 低 | 尽管可能已经对单个终结点造成一些损坏，但恶意软件现在不会对你的公司带来任何威胁。 |
| Microsoft Defender for Business 检测到正在执行的恶意软件。 恶意软件几乎会立即被阻止。 | 中或高 | 恶意软件会向各个终结点和公司带来威胁。 |
| 检测到可疑行为，但尚未执行修正操作。 | 低、中或高 | 严重性取决于行为对公司的威胁程度。 |

## <a name="next-steps"></a>后续步骤

- [响应和缓解 Microsoft Defender for Business 中的威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)

- [在 Microsoft Defender for Business 中查看或编辑设备策略](mdb-view-edit-policies.md)