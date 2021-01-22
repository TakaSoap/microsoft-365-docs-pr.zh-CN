---
title: 在 Microsoft 365 Defender 的 AIR 中处理误报或漏报
description: MICROSOFT 365 Defender 中的 AIR 是否遗漏或错误地检测到了某些内容？ 了解如何将误报或漏报提交给 Microsoft 进行分析。
keywords: 自动化， 调查， 警报， 触发器， 操作， 修正， 误报， 漏报
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930350"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>处理自动调查和响应功能中的误报/负数

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

Microsoft 365 Defender [中的](mtp-autoir.md) 自动调查和响应功能是否遗漏或错误地检测到了某些内容？ 你可以采取一些步骤来修复此问题。 可执行下列操作：

- [向 Microsoft 报告误报/负数](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [根据需要调整警报 (](#adjust-an-alert-to-prevent-false-positives-from-recurring) 调整) ;and 

- [撤消在设备上采取的修正操作](#undo-a-remediation-action-that-was-taken-on-a-device)。 

使用本文作为指南。 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>向 Microsoft 报告误报/负数进行分析

|未接或检测错误的项目 |服务  |需执行的操作  |
|---------|---------|---------|
|- 电子邮件 <br/>- 电子邮件附件 <br/>- 电子邮件中的 URL<br/>- Office 文件的 URL      |[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[将可疑的垃圾邮件、网络钓鱼、URL 和文件提交给 Microsoft 进行扫描](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|设备上文件或应用    |[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection)         |[将文件提交给 Microsoft 进行恶意软件分析](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>调整警报以防止误报重复发生

|方案 |服务 |需执行的操作 |
|--------|--------|--------|
|- 合法使用触发警报 <br/>- 警报不准确    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> 或 <br/>[Azure 高级威胁检测](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[在云应用安全门户中管理警报](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|文件、IP 地址、URL 或域在设备上被视为恶意软件，即使安全|[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) |[使用"允许"操作创建自定义指示器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>撤消在设备上采取的修正操作

如果在 Windows 10 设备 (等设备上采取修正操作) 并且该项目实际上不是威胁，你的安全运营团队可以在操作中心撤消修正[操作。](mtp-action-center.md)

> [!IMPORTANT]
> 在尝试执行 [以下任务之前](mtp-action-center.md#required-permissions-for-action-center-tasks) ，请确保你拥有必要的权限。

1. 转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。 

2. 在“导航”窗格中，选择“操作中心”。 

3. 在 **"历史记录** "选项卡上，选择要撤消的操作。 这将打开一个飞出。<br/>
    > [!TIP]
    > 使用筛选器缩小结果列表。 

4. 在选定项目的飞出中，选择" **打开调查"页**。

5. 在调查详细信息视图中，选择" **操作"** 选项卡。

6. 选择状态为"已完成"**的项目**，在"决策"列中查找链接（**如"已批准**"）。  这将打开一个包含有关该操作的更多详细信息的飞出。

7. 若要撤消该操作，请选择"**删除修正"。**

## <a name="see-also"></a>另请参阅

- [查看自动调查的详细信息和结果](mtp-autoir-results.md)
- [在 Microsoft 365 Defender 中通过高级搜寻主动搜寻威胁](advanced-hunting-overview.md)
