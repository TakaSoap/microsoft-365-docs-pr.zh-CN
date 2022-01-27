---
title: '在 Microsoft Defender for Business 预览版中查看 (事件) '
description: 了解如何查看警报&、响应威胁、管理设备和查看修正操作
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 01/06/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365initiative-defender-business
ms.openlocfilehash: ad0b7a3aa9f68c44a594a9a27906f2fb765bd121
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62244843"
---
# <a name="view-and-manage-incidents-in-microsoft-defender-for-business-preview"></a>在 Microsoft Defender for Business 预览版中查看 (事件) 

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求[](https://aka.ms/mdb-preview)它的客户和 IT 合作伙伴推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

当检测到威胁并触发警报时，将创建事件。 公司的安全团队可以在安全门户中查看Microsoft 365 Defender事件。

**本文包括**：

- [如何监视事件和警报](#monitor-your-incidents--alerts)
- [警报严重性](#alert-severity)
- [后续步骤](#next-steps)

>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="monitor-your-incidents--alerts"></a>监视事件&警报

1. 在"Microsoft 365 Defender" () "导航窗格中，选择 [https://security.microsoft.com](https://security.microsoft.com) "**事件"。** 已创建的任何事件都列在页面上。

   :::image type="content" source="../../media/defender-business/mdb-incidents-list.png" alt-text="&quot;事件&quot;列表的屏幕截图":::

2. 选择警报以打开其飞出窗格，可在其中了解有关警报的详细信息。 

   :::image type="content" source="../../media/defender-business/mdb-incident-flyout.png" alt-text="通过打开飞出线选择的事件的屏幕截图":::

3. 在飞出窗格中，你可以看到警报标题、查看受影响的 (如终结点或用户帐户) 的资产列表、采取可用操作，以及使用链接查看详细信息，甚至打开所选警报的详细信息页面。 

> [!TIP]
> Microsoft Defender for Business (预览) 旨在通过提供建议操作来帮助你解决检测到的威胁。 查看警报时，请查找要采取的建议操作。 还要注意警报严重性，该严重性不仅根据威胁严重性确定，还根据公司的风险级别确定。 

## <a name="alert-severity"></a>警报严重性

当Microsoft Defender 防病毒根据检测到的威胁 () 恶意软件的绝对严重性以及单个终结点的潜在风险（如果受感染 (，) ）分配警报严重性。
Microsoft Defender for Business (预览版) 根据检测到的行为的严重性、终结点 (设备) 的实际风险以及更重要的是，为公司带来潜在风险来分配警报严重性。 下表列出了一些示例： <br/><br/>

| 应用场景 | 警报严重性 | Reason |
|:---|:---|:---|
| Microsoft Defender 防病毒威胁之前检测并停止威胁。 | 信息 | 威胁在损坏完成之前已停止。 |
| Microsoft Defender 防病毒检测在公司内执行的恶意软件。 恶意软件已停止并修复。 | 低 | 尽管可能已经对单个终结点造成一些损坏，但恶意软件现在不会对你的公司带来任何威胁。 |
| 正在执行的恶意软件由 Microsoft Defender for Business 预览版 (检测) 。 恶意软件几乎会立即被阻止。 | 中或高 | 恶意软件会向各个终结点和公司带来威胁。 |
| 检测到可疑行为，但尚未执行修正操作。 | 低、中或高 | 严重性取决于行为对公司的威胁程度。 |

## <a name="next-steps"></a>后续步骤

- [响应和缓解 Microsoft Defender for Business 预览版 (中的威胁) ](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)

- [在 Microsoft Defender for Business 预览版中查看 (编辑设备) ](mdb-view-edit-policies.md)