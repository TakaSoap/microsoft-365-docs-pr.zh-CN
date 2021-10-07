---
title: 如何在 Microsoft Defender for Office 365 自动调查后报告误报或Office 365
description: MICROSOFT Defender for Office 365 中的 AIR 是否遗漏或Office 365？ 了解如何将误报或漏报提交给 Microsoft 进行分析。
keywords: 自动化， 调查， 警报， 触发器， 操作， 修正， 误报， 漏报
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
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
ms.openlocfilehash: 0096cb5f8c0d878ecc888de74f1548c77ed0dda9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196641"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>如何在自动调查和响应功能中报告误报/负面影响

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

如果[自动调查和响应 (AIR](automated-investigation-response-office.md)) 未Office 365检测错误，则安全运营团队可以采取一些措施来解决此问题。 此类操作包括：

- [向 Microsoft 报告误报/负数](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [根据需要调整警报](#adjust-an-alert-to-prevent-false-positives-from-recurring) (调整) ;和
- [撤消已采取的修正操作](#undo-a-remediation-action)。

使用本文作为指南。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>向 Microsoft 报告误报/负数以进行分析

如果 Microsoft Defender for Office 365 AIR 错过电子邮件、电子邮件附件、电子邮件中的 URL 或 Office 文件的 URL，你可以将可疑的垃圾邮件、网络钓鱼、URL 和文件提交给 Microsoft 进行[Office 365 扫描](admin-submission.md)。

还可以将 [文件提交给 Microsoft 进行恶意软件分析](https://www.microsoft.com/wdsi/filesubmission)。

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>调整警报以防止误报重复发生

如果警报是由合法使用触发的，或者该警报不准确，可以在 云应用安全[门户中管理警报](/cloud-app-security/managing-alerts)。

如果你的组织除 Office 365 外还使用[Microsoft Defender for Endpoint，](/windows/security/threat-protection)并且文件、IP 地址、URL 或域在设备上被视为恶意软件，即使安全，你可以为设备创建一个包含"允许"操作的自定义[指示器。](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)

## <a name="undo-a-remediation-action"></a>撤消修正操作

在大多数情况下，如果对电子邮件、电子邮件附件或 URL 采取修正操作，并且该项目实际上不是威胁，则安全运营团队可以撤消修正操作，并采取措施防止误报重复发生。 可以使用威胁资源管理器 [或](#undo-an-action-using-threat-explorer) "操作 ["选项卡进行调查](#undo-an-action-in-the-action-center) 以撤消操作。

> [!IMPORTANT]
> 在尝试执行以下任务之前，请确保你拥有必要的权限。

### <a name="undo-an-action-using-threat-explorer"></a>使用威胁资源管理器撤消操作

借助威胁资源管理器，安全运营团队可以查找受操作影响的电子邮件，并可能撤消该操作。

<br>

****

|应用场景|撤消选项|了解详细信息|
|---|---|---|
|电子邮件已路由到用户的"垃圾邮件"文件夹|<ul><li>将邮件移动到用户的"已删除邮件"文件夹</li><li>将邮件移动到用户的收件箱</li><li>删除邮件</li></ul>|[查找并调查在邮件中传递的恶意Office 365](investigate-malicious-email-that-was-delivered.md)|
|已隔离电子邮件或文件|<ul><li>释放电子邮件或文件</li><li> 删除电子邮件或文件</li></ul>|[以管理员角色管理隔离邮件](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>撤消操作中心中的操作

在操作中心，你可以看到已采取的修正操作并可能撤消该操作。

1. 转到 Microsoft 365 Defender 门户 <https://security.microsoft.com> () 。
2. 在导航窗格中，选择操作 **中心**。
3. 选择 **"历史记录** "选项卡以查看已完成操作的列表。
4. 选择一个项目。 将打开其飞出窗格。
5. 在飞出窗格中， **选择撤消**。  (只有可以撤消的操作才 **具有"撤消** "按钮。) 

## <a name="see-also"></a>另请参阅

- [Microsoft Defender for Office 365](defender-for-office-365.md)
- [Microsoft Defender for Office 365](office-365-air.md)
