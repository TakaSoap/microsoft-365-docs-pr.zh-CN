---
title: 运行并自定义按需扫描Microsoft Defender 防病毒
description: 使用 PowerShell、Windows Management Instrumentation 运行和配置按需扫描，或者使用 Windows 安全中心 应用在终结点上单独运行和配置Windows 安全中心扫描
keywords: 扫描， 按需， dos， intune， 即时扫描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789167"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>配置并运行按需 Microsoft Defender 防病毒软件扫描

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以在个别终结点上运行按需扫描。 这些扫描将立即启动，并且你可以定义扫描的参数，如位置或类型。

## <a name="quick-scan-versus-full-scan"></a>快速扫描与完全扫描

快速扫描将查找所有可能注册为从系统启动的恶意软件的位置，例如注册表项和已知Windows文件夹。

> [!IMPORTANT]
> Microsoft Defender 防病毒执行本地扫描时，在[LocalSystem](/windows/win32/services/localsystem-account)帐户的上下文中运行。 对于网络扫描，它使用设备帐户的上下文。 如果域设备帐户没有访问共享的适当权限，扫描将不起作用。 确保设备具有访问网络共享的权限。

与 [始终打开实时](configure-real-time-protection-microsoft-defender-antivirus.md)保护功能相结合，快速扫描可帮助针对以系统开头的恶意软件和内核级恶意软件提供强大的覆盖范围。 在打开和关闭文件时，以及用户导航到文件夹时，始终启用实时保护会检查文件。 默认情况下，快速扫描在装载的可移动设备（如 USB 驱动器）上运行。 在大多数情况下，快速扫描足以找到实时保护未选取的恶意软件。

当终结点上报告恶意软件威胁时，完全扫描可能很有用。 扫描可确定是否有需要更彻底清理的非活动组件。 但是，Microsoft 通常建议使用快速扫描，而不是完全扫描。 完整扫描可能需要几个小时或几天才能完成，具体取决于需要扫描的数据的数量和类型。 

> [!TIP]
> 若要详细了解快速扫描和完整扫描之间的差异，请参阅 [快速扫描与完全扫描和自定义扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)。

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>使用Microsoft Endpoint Manager运行扫描

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。
2. 选择 **终结点安全**  >  **防病毒**。
3. 在选项卡列表中，选择 **"Windows 10不正常的终结点"。**
4. 从所提供的操作列表中，选择 **快速扫描** 或 **完全扫描**。

[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> 有关使用 Microsoft Endpoint Manager 运行扫描的信息，请参阅[反恶意软件和防火墙任务：如何执行按需扫描](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>使用mpcmdrun.exe命令行实用工具运行扫描

使用以下 `-scan` 参数：

```console
mpcmdrun.exe -scan -scantype 1
```

有关如何使用该工具和其他参数（包括启动完全扫描或定义路径）的信息，请参阅使用[mpcmdrun.exe 命令行](command-line-arguments-microsoft-defender-antivirus.md)工具配置和管理Microsoft Defender 防病毒。

## <a name="use-microsoft-intune-to-run-a-scan"></a>使用 Microsoft Intune 运行扫描

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。
2. 从边栏中， **选择">所有设备"，** 然后选择要扫描的设备。
3. 选择 **...更多**。 从选项中，选择 **"快速扫描"或**"**完全扫描"。**

## <a name="use-the-windows-security-app-to-run-a-scan"></a>使用Windows 安全中心运行扫描

有关[在个别终结点上运行Windows 安全中心](microsoft-defender-security-center-antivirus.md)的说明，请参阅在应用中运行扫描。

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>使用 PowerShell cmdlet 运行扫描

使用以下 cmdlet：

```PowerShell
Start-MpScan
```

若要详细了解如何将 PowerShell 与 Microsoft Defender 防病毒，请参阅使用[PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和[Defender cmdlet。](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>使用 Windows Management Instruction (WMI) 运行扫描

使用 [**类** 的 Start](/previous-versions/windows/desktop/defender/start-msft-mpscan) **MSFT_MpScan** 类。

有关允许哪些参数的信息，请参阅Windows Defender [WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>相关文章

- [配置 Microsoft Defender 防病毒软件扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [配置计划Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)