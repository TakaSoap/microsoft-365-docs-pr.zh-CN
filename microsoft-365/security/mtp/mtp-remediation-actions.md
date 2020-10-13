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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 5106ef34f11cb43d74fa993fcdb820d6a5dce86f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429464"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Microsoft 威胁防护中的自动调查遵循的补救措施

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护


## <a name="remediation-actions"></a>修正操作

在 Microsoft 威胁防护的自动调查过程中和之后，会为恶意项目或可疑项目标识修正操作。 对设备（也称为终结点）执行某些类型的修正操作。 对电子邮件内容执行其他补救措施。 在执行、批准或拒绝补救措施之后，自动调查完成。

下表汇总了 Microsoft 威胁防护当前支持的补救措施： 

|设备 (终结点) 修正操作  |电子邮件修正操作  |
|---------|---------|
|-收集调查包 <br/>-隔离设备 (可以撤消此操作) <br/>-分离 machine <br/>-释放代码执行 <br/>-从隔离区发布 <br/>-请求示例 <br/>-限制代码执行 (可以撤消此操作)  <br/>-运行防病毒扫描 <br/>-停止和隔离      |-阻止 URL (单击时间) <br/>-软删除电子邮件或群集<br/>-隔离电子邮件<br/>-隔离电子邮件附件<br/>-关闭外部邮件转发          |

在 [操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)中，可以查看更正操作（无论是待批准还是已完成）。

## <a name="remediation-actions-follow-automated-investigations"></a>补救措施遵循自动调查

当自动调查完成时，涉及的每条证据都将达到一个结论。 根据判定的具体情况，将确定修正操作。 在某些情况下，将自动执行更正操作;在其他情况下，补救措施等待审批。 这一切都取决于如何 [配置自动调查和响应](mtp-configure-auto-investigation-response.md)。

下表列出了可能的 verdicts 和结果：

|Verdict    |区域    |结果|
|------|------|------|
|恶意    |设备 (终结点)     |如果您的组织的 [设备组](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) 自动设置为 **完全修正的威胁** ，则会自动执行更正操作 () |
|恶意    | (Url 或附件的电子邮件内容)  | 建议的修正操作处于待审批状态|
|引入    |设备或电子邮件内容 |建议的修正操作处于待审批状态|
|未发现威胁    |设备或电子邮件内容    |不需要任何修正操作|

> [!IMPORTANT]
> 是否自动执行更正操作，或仅在批准操作时才会依赖某些设置，如组织的设备组策略。 若要了解详细信息，请参阅以下文章：
> - [在 Microsoft 威胁防护中配置自动调查和响应功能](mtp-configure-auto-investigation-response.md)
> - [如何修正设备上的威胁](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a>后续步骤

- [访问操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [批准或拒绝挂起的操作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [处理自动调查和响应功能中的误报/否定](mtp-autoir-report-false-positives-negatives.md)
