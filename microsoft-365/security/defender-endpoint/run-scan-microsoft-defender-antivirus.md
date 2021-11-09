---
title: 在扫描中运行和自定义按需Microsoft Defender 防病毒
description: 使用 PowerShell、Windows Management Instrumentation 或在终结点上单独运行和配置按需扫描（Windows 安全中心应用）
keywords: 扫描， 按需， 操作， intune， 即时扫描
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/22/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 1f2f5625eff5b19c47aebf896d6a0398437426aa
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881657"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>配置并运行按需 Microsoft Defender 防病毒软件扫描

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以在个别终结点上运行按需扫描。 这些扫描将立即启动，并且你可以定义扫描的参数，如位置或类型。 运行扫描时，可以从以下三种类型中选择：快速扫描、完全扫描和自定义扫描。 在大多数情况下，请使用快速扫描。 快速扫描将查找所有可能注册为从系统启动的恶意软件的位置，例如注册表项和已知Windows文件夹。

与始终启用实时保护相结合，可在打开和关闭文件时以及用户导航到文件夹时查看文件，快速扫描可帮助提供强大的保护，防止由系统和内核级别恶意软件启动的恶意软件。 在大多数情况下，快速扫描已足够，是计划扫描或按需扫描的推荐选项。 [详细了解扫描类型](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)。

> [!IMPORTANT]
> Microsoft Defender 防病毒执行本地扫描时，在[LocalSystem](/windows/win32/services/localsystem-account)帐户的上下文中运行。 对于网络扫描，它使用设备帐户的上下文。 如果域设备帐户没有访问共享的适当权限，扫描将不起作用。 确保设备具有访问网络共享的权限。

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>使用Microsoft Endpoint Manager运行扫描

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。

2. 选择 **终结点安全** \> **防病毒**。

3. 在选项卡列表中，选择"Windows 10 **不正常终结点**"或Windows 11 **不正常终结点"。**

4. 从所提供的操作列表中，选择"快速扫描" (") "完全 **扫描"。**

   [![扫描"不正常Windows 10"选项卡上的选项。](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> 有关使用 Microsoft Endpoint Manager运行扫描的信息，请参阅[反恶意软件和防火墙任务：如何执行按需扫描](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>使用mpcmdrun.exe命令行实用工具运行扫描

使用以下 `-scan` 参数：

```console
mpcmdrun.exe -scan -scantype 1
```

有关如何使用该工具和其他参数（包括启动完全扫描或定义路径）的信息，请参阅使用[mpcmdrun.exe 命令行](command-line-arguments-microsoft-defender-antivirus.md)工具配置和管理Microsoft Defender 防病毒。

## <a name="use-microsoft-intune-to-run-a-scan"></a>使用Microsoft Intune运行扫描

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。

2. 从边栏中， **选择"设备** \> **""** 所有设备"，然后选择你想要扫描的设备。

3. 选择 **...更多**。 从选项中，选择快速 **扫描** (推荐) 或 **完全扫描**。

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
