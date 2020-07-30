---
title: Microsoft 威胁防护中的自动调查遵循的补救措施
description: 获取遵循 Microsoft 威胁防护中的自动调查的修正操作概述
keywords: 自动化, 调查, 警报, 触发器, 操作, 修正
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502933"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Microsoft 威胁防护中的自动调查遵循的补救措施

**适用于：**
- Microsoft 威胁防护


## <a name="remediation-actions"></a>修正操作

在 Microsoft 威胁防护的自动调查过程中和之后，会为恶意项目或可疑项目标识修正操作。 对设备（也称为终结点）执行某些类型的修正操作。 对电子邮件内容执行其他补救措施。 在执行、批准或拒绝补救措施之后，自动调查完成。

下表汇总了 Microsoft 威胁防护当前支持的补救措施： 

|设备（终结点）修正操作  |电子邮件修正操作  |
|---------|---------|
|-收集调查包 <br/>-隔离设备（可以撤消此操作）<br/>-分离 machine <br/>-释放代码执行 <br/>-从隔离区发布 <br/>-请求示例 <br/>-限制代码执行（可以撤消此操作） <br/>-运行防病毒扫描 <br/>-停止和隔离      |-阻止 URL （单击时间）<br/>-软删除电子邮件或群集<br/>-隔离电子邮件<br/>-隔离电子邮件附件<br/>-关闭外部邮件转发          |

在[操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)中，可以查看更正操作（无论是等待审批还是已完成）。

## <a name="remediation-actions-follow-automated-investigations"></a>补救措施遵循自动调查

当自动调查完成时，将达到涉及的每条证据的结论，并确定修正操作。 在某些情况下，将自动执行更正操作;在其他情况下，补救措施等待审批。 下表列出了可能的 verdicts 和结果：

|Verdict    |区域    |结果|
|------|------|------|
|恶意    |设备（终结点）    |将自动执行更正操作|
|恶意    |电子邮件内容（Url 或附件） | 建议的修正操作处于待审批状态|
|引入    |设备或电子邮件内容 |建议的修正操作处于待审批状态|
|未发现威胁    |设备或电子邮件内容    |不需要任何修正操作|

[在操作中心中查看挂起的操作](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> 如果你认为在 Microsoft 威胁防护中，自动调查和响应功能已丢失或错误地检测到了某些内容，请告诉我们！ [报告误报/否定](mtp-autoir-report-false-positives-negatives.md)。

## <a name="next-steps"></a>后续步骤

- [批准或拒绝操作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [详细了解操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
