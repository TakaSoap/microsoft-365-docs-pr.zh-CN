---
title: 如何在 Microsoft Defender for Office 365 中自动调查后报告误报或漏报
description: MICROSOFT Defender for Office 365 中的 AIR 是否错过或错误地检测到某些内容？ 了解如何将误报或漏报提交给 Microsoft 进行分析。
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
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 8a91a55d9598b5e780474315ddf1f7019e593fed
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406158"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>如何在自动调查和响应功能中报告误报/负数

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

如果 [Office 365](automated-investigation-response-office.md) 中的 AIR (自动调查和响应) 检测错误或错误检测到某些内容，则安全运营团队可以采取一些措施来解决此问题。 此类操作包括：

- [向 Microsoft 报告误报/负数](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [根据需要调整 (](#adjust-an-alert-to-prevent-false-positives-from-recurring) 警报) ;和
- [撤消已采取的修正操作](#undo-a-remediation-action)。

使用本文作为指南。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>向 Microsoft 报告误报/负数进行分析

如果 Microsoft Defender for Office 365 中的 AIR 错过电子邮件、电子邮件附件、电子邮件中的 URL 或 Office 文件的 URL，可以将可疑的垃圾邮件、网络钓鱼、URL 和文件提交给 Microsoft 进行 [Office 365](admin-submission.md)扫描。

还可以将 [文件提交到 Microsoft 进行恶意软件分析](https://www.microsoft.com/wdsi/filesubmission)。

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>调整警报以防止误报重复发生

如果警报是由合法使用触发的，或者警报不准确，可以在云应用安全门户 [中管理警报](https://docs.microsoft.com/cloud-app-security/managing-alerts)。

如果你的组织除了使用 Office 365 之外还使用[Microsoft Defender for Endpoint，](https://docs.microsoft.com/windows/security/threat-protection)并且文件、IP 地址、URL 或域在设备上被视为恶意软件，即使安全，也可以为设备创建一个包含"允许"操作自定义[指示器。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)

## <a name="undo-a-remediation-action"></a>撤消修正操作

在大多数情况下，如果对电子邮件、电子邮件附件或 URL 采取修正操作，但该项目实际上不是威胁，则安全运营团队可以撤消修正操作，并采取措施防止误报重复发生。 可以使用威胁资源管理器 [或](#undo-an-action-using-threat-explorer) "操作" [选项卡进行调查](#undo-an-action-in-the-action-center) 以撤消操作。

> [!IMPORTANT]
> 在尝试执行以下任务之前，请确保你拥有必要的权限。

### <a name="undo-an-action-using-threat-explorer"></a>使用威胁资源管理器撤消操作

借助威胁资源管理器，安全运营团队可以查找受操作影响的电子邮件，并可能撤消该操作。

|应用场景|撤消选项|了解更多|
|---|---|---|
|电子邮件已路由到用户的"垃圾邮件"文件夹|- 将邮件移动到用户的"已删除邮件"文件夹<br/>- 将邮件移动到用户的收件箱<br/>- 删除邮件|[查找并调查在 Office 365 中传递的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)|
|已隔离电子邮件或文件|- 释放电子邮件或文件<br/>- 删除电子邮件或文件|[以管理员角色管理隔离邮件](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>撤消操作中心中的操作

在操作中心中，你可以看到已采取的修正操作并可能撤消该操作。

1. 转到 Microsoft 365 安全中心 <https://security.microsoft.com> () 。
2. 在导航窗格中，选择 **操作中心**。
3. 选择 **"历史记录** "选项卡以查看已完成操作的列表。
4. 选择一个项目。 将打开其飞出窗格。
5. 在飞出窗格中，选择"撤消 **"。**  (只有可以撤消的操作才 **具有"撤消** "按钮。) 

## <a name="see-also"></a>另请参阅

- [Microsoft Defender for Office 365](office-365-atp.md)
- [Microsoft Defender for Office 365 中的自动调查](office-365-air.md)
