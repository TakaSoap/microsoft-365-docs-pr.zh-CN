---
title: 如何在 Office 365 自动调查和响应中报告误报或漏报
description: Office 365 高级威胁防护是否错过或错误地检测到了什么？ 了解如何向 Microsoft 提交误报或漏报以进行分析。
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 837232550ca392a364b9842f64a1c3f0d790a502
ms.sourcegitcommit: 33be6075fcc89d4c0a48fa7e59f3b3ebc605d9f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "44520154"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>如何报告自动调查和响应功能中的误报/否定

**适用于：**
- Office 365 高级威胁防护

[Office 365 中的自动化调查和响应（空气）功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)是否未命中或错误地检测到了什么？ 您可以采取一些步骤来修复它。 可以：
- [向 Microsoft 报告误报/负数，](#report-a-false-positivenegative-to-microsoft-for-analysis)或者
- [调整通知](#adjust-an-alert-to-prevent-false-positives-from-recurring)（如果需要）;并 
- [撤消所执行的修正操作](#undo-a-remediation-action)。 

将本文用作指南。 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>将误报/负数报告给 Microsoft 进行分析

如果 Office 365 AIR 错过了电子邮件、电子邮件附件、电子邮件中的 URL 或 Office 文件中的 URL，则可以[将可疑的垃圾邮件、网络钓鱼、url 和文件提交到 Microsoft For office 365 扫描](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)。

您还可以[将文件提交给 Microsoft 进行恶意软件分析](https://www.microsoft.com/wdsi/filesubmission)。

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>调整警报以防止定期误报

如果某个警报由合法使用触发，或者该警报不准确，则可以[在云应用安全门户中管理警报](https://docs.microsoft.com/cloud-app-security/managing-alerts)。

如果您的组织使用的是除 Office 365 之外的[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection)，并且文件、IP 地址、URL 或域在设备上被视为恶意软件，尽管它是安全的，但您可以[创建一个自定义指示器，为设备启用 "允许" 操作](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)。

## <a name="undo-a-remediation-action"></a>撤消修正操作

在大多数情况下，如果对电子邮件、电子邮件附件或 URL 执行了修正操作，而该项目实际上并不是威胁，则安全操作团队可以撤消修正操作并采取措施以防止误报定期发生。 您可以使用 "[威胁资源管理器](#undo-an-action-using-threat-explorer)" 或 "[操作" 选项卡进行调查](#undo-an-action-using-the-actions-tab-for-an-investigation)以撤消某项操作。 

> [!IMPORTANT]
> 在尝试执行以下任务之前，请确保您具有所需的权限。

### <a name="undo-an-action-using-threat-explorer"></a>使用威胁资源管理器撤消操作

通过威胁浏览器，安全操作团队可以找到受操作影响的电子邮件，并可能撤消该操作。

|应用场景  |撤消选项  |了解详细信息 |
|---------|---------|---------|
|将电子邮件路由到用户的 "垃圾邮件" 文件夹     |-将邮件移动到用户的 "已删除邮件" 文件夹<br/>-将邮件移动到用户的收件箱 <br/>-删除邮件          |[查找并调查 Office 365 中提供的恶意电子邮件](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|已隔离电子邮件或文件     |-释放电子邮件或文件 <br/>-删除电子邮件或文件         |[以 Office 365 中的管理员身份管理隔离的邮件和文件](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>使用 "操作" 选项卡进行调查以撤消操作

在操作中心中，你可以看到已执行的更正操作，并且可能会撤消该操作。

1. 转到 [https://protection.office.com](https://protection.office.com) 并登录。 这将转到安全 & 合规中心。

2. 转到**威胁管理**  >  **调查**。

3. 在调查列表中，选择项目 ID 旁边的 "**在新窗口中打开**" 图标。

4. 选择 "**操作**" 选项卡。

5. 选择 "已**完成**" 状态的项目，并在 "**决策**" 列中查找链接（如 "**已批准**"）。 这将打开一个浮出控件，其中包含有关操作的更多详细信息。

6. 若要撤消操作，请选择 "**删除修正**"。

## <a name="related-articles"></a>相关文章

[Office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[开始在 Office 365 中使用自动调查和响应（AIR）](office-365-air.md)
