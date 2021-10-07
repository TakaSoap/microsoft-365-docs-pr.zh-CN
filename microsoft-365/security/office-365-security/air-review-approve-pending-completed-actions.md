---
title: 查看和管理 Microsoft Defender for Office 365
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
description: 了解 Microsoft Defender for Office 365 计划 2 中的自动调查和响应功能中的修正操作。
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 4d81fe5e2baa4146136d7e55461290a31ef2462b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196617"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>在管理中查看和管理Office 365

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](defender-for-office-365.md)

由于自动调查电子邮件&协作内容会导致裁定（如恶意或可疑）时，会创建某些修正操作。 在 Microsoft Defender for Office 365 中，修正操作可能包括：

- 软删除电子邮件或群集
- 关闭外部邮件转发

除非安全运营团队批准这些修正操作，否则不会执行这些修正操作。 我们建议尽快审阅和批准任何挂起的操作，以便自动调查及时完成。 在某些情况下，你可以重新思考提交的操作。  在采取任何操作之前，你需要&清除角色的一部分。

## <a name="approve-or-reject-pending-actions"></a>批准 (或拒绝) 挂起的操作
有四种不同的方法可查找和执行自动调查操作：

- [事件队列](https://security.microsoft.com/incidents)
- [操作中心](https://security.microsoft.com/action-center/pending)
- 调查本身 (事件或警报报告访问) 
- [调查和修正调查队列](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>事件队列

1. 打开Microsoft 365 Defender门户 <https://security.microsoft.com> () 并登录。
2. 在导航窗格中，选择"事件 **&事件>警报"。**
3. 选择事件名称以打开其摘要页面。
4. 选择" **证据和响应"** 选项卡。
5. 选择列表项。 其侧窗格将打开。
6. 在侧窗格中，执行批准或拒绝操作。

## <a name="investigation-queue"></a>调查队列

1. 打开Microsoft 365 Defender门户 <https://security.microsoft.com> () 并登录。
2. 从警报/事件页面导航。
3. 在"调查"页上，转到" **挂起的操作"** 选项卡。
4. 选择列表项。 其侧窗格将打开。
5. 在侧窗格中，执行批准或拒绝操作。

## <a name="action-center"></a>操作中心

1. 打开Microsoft 365 Defender门户 <https://security.microsoft.com> () 并登录。
2. 在导航窗格中，选择操作 **中心**。
3. 在 **"挂起** "选项卡上，查看等待审批的操作列表。
   - 选择 **"打开调查"** 页以查看有关调查的更多详细信息。
   - 选择 **"批准** "以启动挂起的操作。
   - 选择 **"** 拒绝"以防止执行挂起的操作。

## <a name="investigation-and-remediation-investigations-queue"></a>调查和修正调查队列

1. 打开Microsoft 365 Defender门户 <https://security.microsoft.com> () 并登录。
2. 打开待定调查。
3. 在"调查"页上，转到" **挂起的操作"** 选项卡。
4. 选择列表项。 其侧窗格将打开。
5. 在侧窗格中，执行批准或拒绝操作。

## <a name="change-or-undo-one-remediation-action"></a>更改或撤消一个修正操作

有两种不同的方法可以重新考虑提交的操作：

- 通过统 [一操作中心](https://security.microsoft.com/action-center)。
- 但是[，Office操作中心](https://security.microsoft.com/threatincidents)。

## <a name="change-or-undo-through-the-unified-action-center"></a>通过统一操作中心更改或撤消

1. 转到统 [一操作中心](https://security.microsoft.com/action-center) 并登录。
2. 在 **"历史记录** "选项卡上，选择要更改或撤消的操作。
3. 在屏幕右侧窗格中，选择相应的操作 (移动到 **收件箱**、移动到垃圾邮件、移动到已删除项目、软删除或硬) 。   

## <a name="change-or-undo-through-the-office-action-center"></a>通过操作中心Office或撤消

1. 转到Office[中心](https://security.microsoft.com/threatincidents)并登录。
2. 选择适当的修正。
3. 在侧窗格中，单击邮件提交条目并等待列表加载。
4. 等待顶部的"操作"按钮启用并选择"操作"按钮以更改操作类型。
5. 这将创建相应的操作。

## <a name="next-steps"></a>后续步骤

- [使用威胁资源管理器](threat-explorer.md)
- [管理员/手动操作](remediate-malicious-email-delivered-office-365.md)
- [如何在自动调查和响应功能中报告误报/负面影响](air-report-false-positives-negatives.md)

## <a name="see-also"></a>另请参阅

- [查看自动调查的详细信息和Office 365](air-view-investigation-results.md)
