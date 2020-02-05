---
title: 如何在 Microsoft 威胁防护中报告空气中的误报或虚假否定
description: 无线在 Microsoft 威胁防护中是否已错过或错误地检测到了什么？ 了解如何向 Microsoft 提交误报或漏报以进行分析。
keywords: 自动化、调查、警报、触发器、操作、修正、误报、假负
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 1177f552652e728928a2b1d322b4ce0217415509
ms.sourcegitcommit: ca2209d9176f99048d0a7adc20261029ca23dcbd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2020
ms.locfileid: "41774188"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>如何报告自动调查和响应功能中的误报/否定

**适用于：**
- Microsoft 威胁防护

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

在 Microsoft 威胁防护中是否进行了[自动化调查和响应功能](mtp-autoir.md)丢失或错误地检测到了什么？ 您可以采取一些步骤来修复它。 可执行下列操作：
- [向 Microsoft 报告误报/负数，](#report-a-false-positivenegative-to-microsoft-for-analysis)或者
- [调整通知](#adjust-an-alert-to-prevent-false-positives-from-recurring)（如果需要）;并 
- [撤消对设备所执行的修正操作](#undo-a-remediation-action-that-was-taken-on-a-device)。 

将本文用作指南。 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>将误报/负数报告给 Microsoft 进行分析

|缺少或错误地检测到项目 |服务  |需执行的操作  |
|---------|---------|---------|
|-电子邮件 <br/>-电子邮件附件 <br/>-电子邮件中的 URL<br/>-Office 文件中的 URL      |[Office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[将可疑的垃圾邮件、网络钓鱼、Url 和文件提交到 Microsoft for Office 365 扫描](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|设备上的文件或应用    |[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection)         |[将文件提交给 Microsoft 进行恶意软件分析](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>调整警报以防止定期误报

|方案 |服务 |需执行的操作 |
|--------|--------|--------|
|-警报由合法使用触发 <br/>-警报不准确    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> 或 <br/>[Azure 高级威胁检测](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[在云应用安全门户中管理通知](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|即使是安全的，文件、IP 地址、URL 或域也会在设备上被视为恶意软件|[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection) |[创建具有 "允许" 操作的自定义指示器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>撤消对设备执行的修正操作

如果对设备（如 Windows 10 设备）执行了修正操作，并且该项目实际上是干净的，则安全操作团队可以撤消[操作中心](mtp-action-center.md)中的修正操作。

> [!IMPORTANT]
> 在尝试执行以下任务之前，请确保您具有[所需的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)。

1. 转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。 

2. 在“导航”窗格中，选择“操作中心”****。 

3. 在 "**历史记录**" 选项卡上，选择要撤消的操作。 这将打开一个浮出控件。<br/>
    > [!TIP]
    > 使用筛选器缩小结果列表。 

4. 在选定项的浮出控件中，选择 "**打开调查页面**"。

5. 在调查详细信息视图中，选择 "**操作**" 选项卡。

6. 选择 "已**完成**" 状态的项目，并在 "**决策**" 列中查找链接（如 "**已批准**"）。 这将打开一个浮出控件，其中包含有关操作的更多详细信息。

7. 若要撤消操作，请选择 "**删除修正**"。

## <a name="related-articles"></a>相关文章

- [批准或拒绝与自动调查和响应相关的操作](mtp-autoir-actions.md)
- [详细了解操作中心](mtp-action-center.md)
- [通过 Microsoft 威胁防护中的高级搜寻主动搜寻威胁](advanced-hunting-overview.md)
