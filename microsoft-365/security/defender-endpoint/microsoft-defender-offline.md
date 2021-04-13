---
title: Windows 10 中的 Microsoft Defender 脱机版本
description: 你可以直接从防病毒应用Windows Defender Microsoft Defender 脱机版。 还可以管理如何在网络中部署它。
keywords: 扫描， defender， 脱机
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 44a0e78ecfe3854a070831bf01a012c2cec06ce7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689924"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>运行并查看 Microsoft Defender 脱机扫描的结果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 脱机是一种反恶意软件扫描工具，允许你从受信任的环境启动和运行扫描。 扫描从正常的 Windows 内核外部运行，因此它可以定位尝试绕过 Windows Shell 的恶意软件，例如感染或覆盖 MBR (主启动记录的病毒和 rootkit) 。

如果怀疑恶意软件感染，或者想要在恶意软件爆发后确认彻底清理终结点，可以使用 Microsoft Defender 脱机。

在 Windows 10 中，可直接从 Windows 安全中心应用单击一下即可运行 Microsoft Defender [脱机版本](microsoft-defender-security-center-antivirus.md)。 在以前版本的 Windows 中，用户必须安装 Microsoft Defender 脱机版以启动媒体、重新启动终结点并加载可启动媒体。

## <a name="prerequisites-and-requirements"></a>先决条件和要求

Windows 10 中的 Microsoft Defender 脱机版本具有与 Windows 10 相同的硬件要求。 

有关 Windows 10 要求详细信息，请参阅以下主题：

- [最低硬件要求](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [硬件组件指南](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender 脱机版本在具有 ARM 处理器的计算机或 Windows Server 库存单元上不受支持。

若要从终结点运行 Microsoft Defender Offline，用户必须使用管理员权限登录。
 
## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender 脱机更新

Microsoft Defender 脱机使用终结点上提供的最新保护更新;每当更新防病毒Windows Defender它都会更新。 

> [!NOTE]
> 在运行脱机扫描之前，应尝试更新 Microsoft Defender AV 保护。 可以使用组策略强制更新，或者通常将更新部署到终结点，也可以手动下载并安装来自 Microsoft 恶意软件防护中心 [的最新保护更新](https://www.microsoft.com/security/portal/definitions/adl.aspx)。

有关详细信息， [请参阅管理 Microsoft Defender 防病毒安全智能](manage-protection-updates-microsoft-defender-antivirus.md) 更新主题。

## <a name="usage-scenarios"></a>使用方案

在 Windows 10 版本 1607 中，你可以手动强制脱机扫描。 或者，Windows Defender确定需要运行 Microsoft Defender 脱机游戏，它将在终结点上提示用户。 

如果使用脱机扫描来管理终结点，Microsoft Endpoint Manager 中也会显示需要执行脱机扫描。

该提示可以通过通知发生，类似于以下内容：

![显示运行 Microsoft Defender 脱机版本的要求的 Windows 通知](images/defender/notification.png)

用户还将在客户端Windows Defender通知。

在 Configuration Manager 中，可以通过导航到监视 > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status 来 **标识终结点的状态**。 

Microsoft Defender 脱机扫描在恶意软件修正 **状态下指示** 为 **需要脱机扫描**。

![指示需要 Microsoft Defender 脱机扫描的 Microsoft Endpoint Manager](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>配置通知

在与其他 Microsoft Defender AV 通知相同的策略设置中配置 Microsoft Defender 脱机通知。

有关终结点中的通知Windows Defender，请参阅配置 [终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md) 主题。

## <a name="run-a-scan"></a>运行扫描 

> [!IMPORTANT]
> 使用 Microsoft Defender 脱机版本之前，请确保保存所有文件并关闭正在运行的程序。 Microsoft Defender 脱机版扫描大约需要 15 分钟运行。 扫描完成后，它将重新启动终结点。 扫描在常规 Windows 操作环境之外执行。 用户界面将显示不同于由用户执行的正常Windows Defender。 扫描完成后，终结点将重新启动，并且 Windows 将正常加载。

你可以运行具有以下各项的 Microsoft Defender 脱机扫描：

- PowerShell
- Windows Management Instrumentation (WMI)
- Windows 安全应用



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>使用 PowerShell cmdlet 运行脱机扫描

使用以下 cmdlet：

```PowerShell
Start-MpWDOScan
```

请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>使用 Windows Management Instruction (WMI) 运行脱机扫描

使用 [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 类运行脱机扫描。

以下 WMI 脚本代码段将立即运行 Microsoft Defender 脱机扫描，这将导致终结点重新启动、运行脱机扫描，然后重新启动并启动到 Windows。

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

有关详细信息，请参阅以下内容：
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>使用 Windows Defender 安全应用运行脱机扫描

1. 通过单击任务栏中的防护图标或搜索 Defender 的开始菜单打开 Windows 安全 **应用**。

2. 单击病毒&**威胁** 防护磁贴 (左侧菜单栏上的防护图标或) 高级 **扫描标签：**
    
3. 选择 **Microsoft Defender 脱机扫描，** 然后单击立即 **扫描**。

    > [!NOTE]
    > 在 Windows 10 版本 1607 中，脱机扫描可以运行在 **Windows** 设置更新 & 安全Windows Defender下，也可以从 Windows Defender  >    >  客户端运行。


## <a name="review-scan-results"></a>查看扫描结果

Microsoft Defender 脱机版扫描结果将列在 Windows 安全中心应用的 [扫描历史记录部分中](microsoft-defender-security-center-antivirus.md)。 


## <a name="related-articles"></a>相关文章

- [自定义、启动和查看扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)