---
title: 在 Microsoft Defender for Office 365
keywords: AIR， autoIR， Microsoft Defender for Endpoint， 自动化， 调查， 响应， 修正， 威胁， 高级， 威胁， 保护
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: 了解 Microsoft Defender for Office 365 计划 2 中的自动调查和响应功能中的修正操作。
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: bc8c99a547e4f30e10575e8353afd6ca02bf233b
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61932769"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>在管理中查看和管理Office 365

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](defender-for-office-365.md)

由于自动调查电子邮件&协作内容会导致裁定（如恶意或可疑）时，会创建某些修正操作。 在 Microsoft Defender for Office 365中，修正操作可能包括：

- 软删除电子邮件或群集
- 关闭外部邮件转发

除非安全运营团队批准这些修正操作，否则不会执行这些修正操作。 我们建议尽快审阅和批准任何挂起的操作，以便自动调查及时完成。 在某些情况下，你可以重新思考提交的操作。  在采取任何操作之前，你需要&清除角色的一部分。

## <a name="approve-or-reject-pending-actions"></a>批准 (或拒绝) 挂起的操作

有四种不同的方法可查找和执行自动调查操作：

- [事件队列](https://security.microsoft.com/incidents)
- 调查本身 (事件或警报报告访问) 
- [操作中心](https://security.microsoft.com/action-center/pending)
- [调查和修正调查队列](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>事件队列

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com> ， go to the **Incidents** page at **Incidents & alerts** \> **Incidents**. 若要直接转到" **事件"页面** ，请使用 <https://security.microsoft.com/incidents> 。
2. 在 **"事件"** 页上，选择事件名称以打开其摘要页面。
3. 选择" **证据和响应"** 选项卡。
4. 选择列表项。 其侧窗格将打开。
5. 在侧窗格中，执行批准或拒绝操作。

## <a name="action-center"></a>操作中心

1. 在 Microsoft 365 Defender门户 <https://security.microsoft.com> 中，选择"操作 **中心**"转到"操作中心 **"页面**。 若要直接转到操作 **中心页面** ，请使用 <https://security.microsoft.com/action-center/pending> 。
2. 在"**操作中心**"页上，确认"挂起"选项卡已选中，然后查看等待审批的操作列表。
   - 选择 **"打开调查"** 页以查看有关调查的更多详细信息。
   - 选择 **"批准** "以启动挂起的操作。
   - 选择 **"** 拒绝"以防止执行挂起的操作。

## <a name="investigation-and-remediation-investigations-queue"></a>调查和修正调查队列

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com> ， go to the Threat **investigation** page at Email **& collaboration** \> **Investigations**. 若要直接转到威胁 **调查页面，** 请使用 <https://security.microsoft.com/airinvestigation> 。
2. 在" **威胁调查** "页面上，从列表中查找状态为"挂起" **操作 的项目**。
3. 单击 ![ "在新建窗口图标中打开"。](../../media/m365-cc-sc-open-icon.png) **在列表时间的新** 窗口中打开， (**ID** 和 **状态**) 。
4. 在打开的页面中，执行批准或拒绝操作。

## <a name="change-or-undo-one-remediation-action"></a>更改或撤消一个修正操作

有两种不同的方法可以重新考虑提交的操作：

- 通过统 [一操作中心](https://security.microsoft.com/action-center)。
- 但是[，Office操作中心](https://security.microsoft.com/threatincidents)。

## <a name="change-or-undo-through-the-unified-action-center"></a>通过统一操作中心更改或撤消

1. 在 Microsoft 365 Defender门户中，通过选择"操作中心"转到 <https://security.microsoft.com> 统一 **操作中心**。 若要直接转到统一操作中心，请使用 <https://security.microsoft.com/action-center/> 。
2. 在" **操作中心"** 页上，选择 **"历史记录** "选项卡，然后选择要更改或撤消的操作。
3. **在屏幕** 右侧窗格中，选择相应的操作 (移动到收件箱、移动到垃圾邮件、移动到已删除项目、软删除或硬删除) 。   

## <a name="change-or-undo-through-the-office-action-center"></a>通过操作中心Office或撤消

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com> ， go to the Office action center at Email & **collaboration** \> **Review** \> **Action center**. 若要直接转到操作Office中心，请使用 <https://security.microsoft.com/threatincidents> 。
2. 在" **操作中心"** 页上，选择适当的修正。
3. 在侧面板中，单击邮件提交条目并等待列表加载。
4. 等待顶部的"操作"按钮启用并选择"操作"按钮以更改操作类型。
5. 这将创建相应的操作。

## <a name="next-steps"></a>后续步骤

- [使用威胁资源管理器](threat-explorer.md)
- [管理员/手动操作](remediate-malicious-email-delivered-office-365.md)
- [如何在自动调查和响应功能中报告误报/负面影响](air-report-false-positives-negatives.md)

## <a name="see-also"></a>另请参阅

- [查看自动调查的详细信息和结果Office 365](air-view-investigation-results.md)
