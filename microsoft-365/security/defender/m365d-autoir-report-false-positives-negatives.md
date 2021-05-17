---
title: 在 Defender 中解决误报Microsoft 365漏报
description: DEFENDER 中的 AIR 是否遗漏或Microsoft 365错误？ 了解如何将误报或漏报提交给 Microsoft 进行分析。
keywords: 自动化， 调查， 警报， 修正， 误报， 漏报
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 3cffa97d26b2b28de8d9e45d7030e0931a7ba072
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269572"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a>在 Defender 中解决误报Microsoft 365漏报

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

任何威胁防护解决方案偶尔会出现误报或负面影响。 如果[Defender 中的](m365d-autoir.md)自动调查和响应功能Microsoft 365或错误检测到某些内容，则安全操作团队可以采取以下步骤：

- [向 Microsoft 报告误报/负数](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [根据需要调整](#adjust-an-alert-to-prevent-false-positives-from-recurring) (通知) 
- [撤消对设备采取的修正操作](#undo-a-remediation-action-that-was-taken-on-a-device)

以下各节介绍如何执行这些任务。

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>向 Microsoft 报告误报/负数以进行分析

|未接或检测错误的项目 |服务  |需执行的操作  |
|---------|---------|---------|
|- 电子邮件 <br/>- 电子邮件附件 <br/>- 电子邮件中的 URL<br/>- 文件Office URL      |[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)        |[将可疑的垃圾邮件、网络钓鱼、URL 和文件提交给 Microsoft 进行扫描](../office-365-security/admin-submission.md)         |
|设备上的文件或应用    |[Microsoft Defender for Endpoint](/windows/security/threat-protection)         |[将文件提交给 Microsoft 进行恶意软件分析](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>调整警报以防止误报重复发生

|应用场景 |服务 |需执行的操作 |
|--------|--------|--------|
|- 通过合法使用触发警报 <br/>- 警报不准确    |[Microsoft Cloud App Security](/cloud-app-security)<br/> 或 <br/>[Azure 威胁防护](/azure/security/fundamentals/threat-detection)         |[管理 云应用安全 门户中的警报](/cloud-app-security/managing-alerts)         |
|文件、IP 地址、URL 或域在设备上被视为恶意软件，即使安全|[Microsoft Defender for Endpoint](/windows/security/threat-protection) |[使用"允许"操作创建自定义指示器](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>撤消在设备上采取的修正操作

如果对实体（如设备或电子邮件 (）采取修正操作) 并且受影响的实体实际上不是威胁，则安全运营团队可以在操作中心撤消修正 [操作](m365d-action-center.md)。

1. 转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。 
2. 在“导航”窗格中，选择“操作中心”。 
3. 在 **"历史记录** "选项卡上，选择要撤消的操作。 将打开其飞出窗格。
4. 在飞出窗格中， **选择撤消**。

> [!TIP]
> 请参阅 [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions)。

## <a name="see-also"></a>另请参阅

- [查看自动调查的详细信息和结果](m365d-autoir-results.md)
- [在 defender 中通过高级搜寻主动Microsoft 365威胁](advanced-hunting-overview.md)
- [解决 Microsoft Defender for Endpoint 中的误报/漏报](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)