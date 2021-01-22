---
title: Microsoft 365 Defender 中的修正操作
description: 获取 Microsoft 365 Defender 中自动调查后修正操作概述
keywords: 自动化, 调查, 警报, 触发器, 操作, 修正
search.appverid: met150
ms.prod: m365-security
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932846"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Microsoft 365 Defender 中的修正操作

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>修正操作

在 Microsoft 365 Defender 自动调查期间和之后，会针对恶意或可疑项目标识修正操作。 某些类型的修正操作在设备上执行，也称为终结点。 对电子邮件内容执行其他修正操作。 自动调查在采取、批准或拒绝修正操作后完成。

> [!IMPORTANT]
> 修正操作是自动执行还是仅在审批后执行取决于某些设置，如自动化级别的方式。 若要了解更多信息，请参阅以下文章：
> - [在 Microsoft 365 Defender 中配置自动调查和响应功能](mtp-configure-auto-investigation-response.md)
> - [如何在设备上修正威胁](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [针对电子邮件和协作内容的威胁&修正操作](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

下表总结了 Microsoft 365 Defender 中当前支持的修正操作： 

|设备 (终结点) 修正操作  |电子邮件修正操作  |
|---------|---------|
|- 收集调查包 <br/>- 隔离设备 (此操作可以撤消) <br/>- 载出计算机 <br/>- 发布代码执行 <br/>- 解除隔离 <br/>- 请求示例 <br/>- 限制代码 (此操作可以撤消)  <br/>- 运行防病毒扫描 <br/>- 停止和隔离      |- 在 (时阻止 URL) <br/>- 软删除电子邮件或群集<br/>- 隔离电子邮件<br/>- 隔离电子邮件附件<br/>- 关闭外部邮件转发          |

可在操作中心中查看修正操作，无论是等待审批还是 [已完成](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)。

## <a name="remediation-actions-that-follow-automated-investigations"></a>自动调查后采取的修正操作

自动调查完成后，将针对涉及的每一条证据做出裁定。 根据裁定，确定修正操作。 在某些情况下，将自动执行修正操作;其他情况下，修正操作等待审批。 这取决于自动调查和响应 [的配置方式](mtp-configure-auto-investigation-response.md)。

下表列出了可能裁定和结果：

| Verdict    | 区域    | 结果|
|------|------|------|
| 恶意    | 设备 (终结点)     | 如果组织的设备组 ("完全"，则会自动执行修正操作 [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) **-** 自动修正) |
| 恶意    | 电子邮件内容 (URL 或附件)  | 建议的修正操作正在等待审批|
| 可疑    | 设备或电子邮件内容 | 建议的修正操作正在等待审批|
| 未发现威胁    | 设备或电子邮件内容    | 无需修正操作|


## <a name="remediation-actions-that-are-taken-manually"></a>手动采取的修正操作

除了执行自动调查的修正操作之外，安全运营团队还可以手动执行某些修正操作。 其中包括以下操作：

- 手动设备操作，例如设备隔离或文件隔离。
- 手动电子邮件操作，例如软删除电子邮件。 
- [设备或](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) 电子邮件上的高级搜寻操作。
- [对](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) 电子邮件内容执行资源管理器操作，例如将电子邮件移动到垃圾邮件、软删除电子邮件或硬删除电子邮件。
- 手动 [实时响应](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 操作，例如删除文件、停止进程和删除计划任务。
- 适用于终结点 API [的 Microsoft Defender 实时](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)响应操作，例如隔离设备、运行防病毒扫描和获取有关文件的信息。 

## <a name="next-steps"></a>后续步骤

- [访问操作中心](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [批准或拒绝挂起的操作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [处理自动调查和响应功能中的误报/负数](mtp-autoir-report-false-positives-negatives.md)
