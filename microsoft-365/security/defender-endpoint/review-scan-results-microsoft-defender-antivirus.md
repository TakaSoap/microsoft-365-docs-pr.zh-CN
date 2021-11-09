---
title: 查看扫描Microsoft Defender 防病毒结果
description: 使用应用、Microsoft Endpoint Configuration Manager、Microsoft Intune或Windows 安全中心扫描结果
keywords: 扫描结果， 修正， 完全扫描， 快速扫描
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: cec44ad879eb7e425fa8ed20daa468eae7c61af1
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881765"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>查看Microsoft Defender 防病毒扫描结果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

完成Microsoft Defender 防病毒（无论是按需扫描还是计划扫描）后，将记录[](run-scan-microsoft-defender-antivirus.md)结果，并且您可以查看[](scheduled-catch-up-scans-microsoft-defender-antivirus.md)结果。 


## <a name="use-configuration-manager-to-review-scan-results"></a>使用 Configuration Manager 查看扫描结果

请参阅[如何监视Endpoint Protection状态](/configmgr/protect/deploy-use/monitor-endpoint-protection)。

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>使用 PowerShell cmdlet 查看扫描结果

以下 cmdlet 将返回终结点上的每个检测。 如果对同一威胁进行多次检测，将基于每次检测的时间单独列出每个检测：

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="PowerShell cmdlet 和输出的屏幕截图。":::

你可以指定 `-ThreatID` 将输出限制为只显示特定威胁的检测。

如果要列出威胁检测，但将同一威胁的检测组合到单个项目，可以使用以下 cmdlet：

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="PowerShell 代码。":::

请参阅 [使用 PowerShell cmdlet 配置并运行 Microsoft Defender 防病毒软件](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender cmdlet](/powershell/module/defender/) ，了解有关如何通过 Microsoft Defender 防病毒软件使用 PowerShell 的信息。

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>使用 Windows Management Instruction (WMI) 查看扫描结果

使用 [**Get** 方法的 **MSFT_MpThreat** 和 **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) 类。


## <a name="related-articles"></a>相关文章

- [自定义、启动和查看扫描Microsoft Defender 防病毒修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)