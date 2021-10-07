---
title: 解决邮件中的误报或Microsoft 365 Defender
description: AIR 在设备中是否遗漏或Microsoft 365 Defender？ 了解如何将误报或漏报提交给 Microsoft 进行分析。
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: df2effa41977624530b5f9ea8881f7f5aaeef82f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209101"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a>解决邮件中的误报或Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

任何威胁防护解决方案偶尔会出现误报或负面影响。 如果[自动调查和响应功能在](m365d-autoir.md)检测到Microsoft 365 Defender错误检测到某些内容时，安全运营团队可以采取以下步骤：

- [向 Microsoft 报告误报/负数](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [根据需要调整警报](#adjust-an-alert-to-prevent-false-positives-from-recurring) (调整) 
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
|- 通过合法使用触发警报 <br/>- 警报不准确    |[Microsoft Cloud App Security](/cloud-app-security)<br/> 或者 <br/>[Azure 威胁防护](/azure/security/fundamentals/threat-detection)         |[管理 云应用安全 门户中的警报](/cloud-app-security/managing-alerts)         |
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
- [通过高级搜寻主动搜寻Microsoft 365 Defender](advanced-hunting-overview.md)
