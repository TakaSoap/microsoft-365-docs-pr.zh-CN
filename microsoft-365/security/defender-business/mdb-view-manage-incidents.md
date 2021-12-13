---
title: '在 Microsoft Defender for Business 预览版中查看 (事件) '
description: 了解如何查看警报&、响应威胁、管理设备和查看修正操作
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 48d50e3f1d661dfb96792688b6ff167cc7473044
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423487"
---
# <a name="view-and-manage-incidents-in-microsoft-defender-for-business-preview"></a>在 Microsoft Defender for Business 预览版中查看 (事件) 

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本文包含指向联机内容的链接，这些链接可能介绍 Microsoft Defender for Business 预览版中未 (一些) 。

当检测到威胁并触发警报时，将创建事件。 贵公司的安全团队可以在安全门户中查看和管理Microsoft 365 Defender事件。

**本文包括**：

- [如何监视事件和警报](#monitor-your-incidents--alerts)
- [警报严重性](#alert-severity)
- [后续步骤](#next-steps)

## <a name="monitor-your-incidents--alerts"></a>监视事件&警报

1. 在Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () 导航窗格中，选择"**事件"。** 已创建的任何事件都列在页面上。

   :::image type="content" source="../../media/defender-business/mdb-incidents-list.png" alt-text="&quot;事件&quot;列表的屏幕截图":::

2. 选择警报以打开其飞出窗格，可在其中了解有关警报的详细信息。 

   :::image type="content" source="../../media/defender-business/mdb-incident-flyout.png" alt-text="通过打开飞出线选择的事件的屏幕截图":::

3. 在飞出窗格中，你可以看到警报标题、查看受影响的 (如终结点或用户帐户) 的资产列表、采取可用操作，以及使用链接查看详细信息，甚至打开所选警报的详细信息页面。 

> [!TIP]
> Microsoft Defender for Business (预览) 旨在通过提供建议操作来帮助你解决检测到的威胁。 查看警报时，请查找要采取的建议操作。 还要注意警报严重性，该严重性不仅根据威胁严重性确定，还根据公司的风险级别确定。 

## <a name="alert-severity"></a>警报严重性

当Microsoft Defender 防病毒根据检测到的威胁 (恶意软件的绝对严重性) 以及单个终结点受到感染时对单个终结点 (的) 。
Microsoft Defender for Business (预览版) 根据检测到的行为的严重性、终结点 (设备) 的实际风险以及更重要的是，为公司带来潜在风险来分配警报严重性。 下表列出了一些示例： <br/><br/>

| 应用场景 | 警报严重性 | Reason |
|:---|:---|:---|
| Microsoft Defender 防病毒威胁之前检测并停止威胁。 | 信息 | 威胁在损坏完成之前已停止。 |
| Microsoft Defender 防病毒检测在公司内执行的恶意软件。 恶意软件已停止并修复。 | 低 | 尽管可能已经对单个终结点造成一些损坏，但恶意软件现在不会对你的公司带来任何威胁。 |
| 正在执行的恶意软件由 Microsoft Defender for Business 预览版 (检测) 。 恶意软件几乎会立即被阻止。 | 中或高 | 恶意软件会向各个终结点和公司带来威胁。 |
| 检测到可疑行为，但尚未执行修正操作。 | 低、中或高 | 严重性取决于行为对公司的威胁程度。 |

## <a name="next-steps"></a>后续步骤

- [在 Microsoft Defender for Business 预览版中响应 (缓解) ](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)

- [在 Microsoft Defender for Business 预览版中查看 (编辑设备) ](mdb-view-edit-policies.md)