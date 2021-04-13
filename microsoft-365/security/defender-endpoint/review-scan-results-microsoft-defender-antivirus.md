---
title: 查看 Microsoft Defender AV 扫描的结果
description: 使用 Microsoft Endpoint Configuration Manager、Microsoft Intune 或 Windows 安全中心应用查看扫描结果
keywords: 扫描结果， 修正， 完全扫描， 快速扫描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8fe2810ce18589d3131aa17f25ccfb01ec26b892
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689979"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>查看 Microsoft Defender 防病毒扫描结果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防病毒扫描完成后（无论是按需扫描还是计划扫描[](run-scan-microsoft-defender-antivirus.md)）后，将[](scheduled-catch-up-scans-microsoft-defender-antivirus.md)记录结果，你可以查看结果。 


## <a name="use-configuration-manager-to-review-scan-results"></a>使用 Configuration Manager 查看扫描结果

请参阅 [如何监视 Endpoint Protection 状态](/configmgr/protect/deploy-use/monitor-endpoint-protection)。

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>使用 PowerShell cmdlet 查看扫描结果

以下 cmdlet 将返回终结点上的每个检测。 如果对同一威胁进行多次检测，将基于每次检测的时间单独列出每个检测：

```PowerShell
Get-MpThreatDetection
```

![PowerShell cmdlet 和输出的屏幕截图](images/defender/wdav-get-mpthreatdetection.png)

你可以指定 `-ThreatID` 将输出限制为只显示特定威胁的检测。

如果要列出威胁检测，但将同一威胁的检测组合到单个项目，可以使用以下 cmdlet：

```PowerShell
Get-MpThreat
```

![PowerShell 屏幕截图](images/defender/wdav-get-mpthreat.png)

请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>使用 Windows Management Instruction (WMI) 查看扫描结果

使用 [**Get** 方法的 **MSFT_MpThreat** 和 **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) 类。


## <a name="related-articles"></a>相关文章

- [自定义、启动和查看 Microsoft Defender 防病毒扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)