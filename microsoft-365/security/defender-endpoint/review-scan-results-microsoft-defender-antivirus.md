---
title: 查看Microsoft Defender 防病毒扫描的结果
description: 使用Microsoft Endpoint Configuration Manager、Microsoft Intune或Windows 安全中心应用查看扫描结果
keywords: 扫描结果，修正，完全扫描，快速扫描
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
ms.openlocfilehash: 9ffe10560bb36c8fc1311061510f35396934e3b8
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790627"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a>查看Microsoft Defender 防病毒扫描结果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

Microsoft Defender 防病毒扫描完成后，无论是[按需](run-scan-microsoft-defender-antivirus.md)[扫描还是计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)，结果均会被记录下来，你可以查看结果。 


## <a name="use-configuration-manager-to-review-scan-results"></a>使用Configuration Manager查看扫描结果

请参阅[如何监视Endpoint Protection状态](/configmgr/protect/deploy-use/monitor-endpoint-protection)。

## <a name="use-powershell-cmdlets-to-review-scan-results"></a>使用 PowerShell cmdlet 查看扫描结果

以下 cmdlet 将返回终结点上的每个检测。 如果有多个检测相同的威胁，则每个检测将根据每个检测的时间单独列出：

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="PowerShell cmdlet 和输出" lightbox="../../media/wdav-get-mpthreatdetection.png":::

可以指定 `-ThreatID` 将输出限制为仅显示特定威胁的检测。

如果想要列出威胁检测，但将相同威胁的检测合并到单个项中，可以使用以下 cmdlet：

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="PowerShell 代码" lightbox="../../media/wdav-get-mpthreat.png":::

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅[使用 PowerShell cmdlet 配置和运行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender 防病毒 cmdlet](/powershell/module/defender/)。

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a>使用Windows管理指令 (WMI) 查看扫描结果

使用 [**MSFT_MpThreat** 和 **MSFT_MpThreatDetection** 类的 **Get** 方法](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)


## <a name="related-articles"></a>相关文章

- [自定义、启动和查看Microsoft Defender 防病毒扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
