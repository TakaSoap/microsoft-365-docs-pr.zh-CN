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
localization_priority: Normal
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
ms.openlocfilehash: 7894a9aa38239bf661c809cce96ea2a2a96c3725
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904124"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>在管理中查看和管理Office 365

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

由于自动调查电子邮件&协作内容会导致裁定（如恶意或可疑）时，会创建某些修正操作。 在 Microsoft Defender for Office 365 中，修正操作可能包括：

- 阻止 URL (单击时) 
- 软删除电子邮件或群集
- 隔离电子邮件或电子邮件附件
- 关闭外部邮件转发

除非安全运营团队批准这些修正操作，否则不会执行这些修正操作。 我们建议尽快审阅和批准任何挂起的操作，以便自动调查及时完成。 在某些情况下，您可以撤消修正操作。

## <a name="approve-or-reject-pending-actions"></a>批准 (或拒绝) 挂起的操作

1. 转到"Microsoft 365 Defender <https://security.microsoft.com> () 并登录。
2. 在导航窗格中，选择操作 **中心**。
3. 在 **"挂起** "选项卡上，查看等待审批的操作列表。
4. 选择列表项。 将打开其飞出窗格。 
5. 查看飞出窗格中的信息，然后执行以下步骤之一：
   - 选择 **"打开调查"** 页以查看有关调查的更多详细信息。
   - 选择 **"批准** "以启动挂起的操作。
   - 选择 **"** 拒绝"以防止执行挂起的操作。

## <a name="change-or-undo-one-remediation-action"></a>更改或撤消一个修正操作

1. 转到操作中心 <https://security.microsoft.com/action-center> () 并登录。
2. 在 **"历史记录** "选项卡上，选择要更改或撤消的操作。
3. 在屏幕右侧窗格中，选择"撤消 **"。**

## <a name="change-or-undo-multiple-remediation-actions"></a>更改或撤消多个修正操作

1. 转到操作中心 <https://security.microsoft.com/action-center> () 并登录。
2. 在 **"历史记录** "选项卡上，选择要更改或撤消的操作。 确保选择操作类型相同的项目。 将打开一个飞出窗格。
3. 在飞出窗格中，选择"撤消"。

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>跨多个设备从隔离中删除文件

1. 转到操作中心 <https://security.microsoft.com/action-center> () 并登录。
2. 在" **历史记录"** 选项卡上，选择操作类型为"隔离 **文件"的文件**。
3. 在屏幕右侧窗格中，选择"应用到此文件的 **X** 更多实例"，然后选择"撤消 **"。**

## <a name="next-steps"></a>后续步骤

- [使用威胁资源管理器](threat-explorer.md)
- [如何在自动调查和响应功能中报告误报/负面影响](air-report-false-positives-negatives.md)

## <a name="see-also"></a>另请参阅

- [查看自动调查的详细信息和Office 365](air-view-investigation-results.md)
