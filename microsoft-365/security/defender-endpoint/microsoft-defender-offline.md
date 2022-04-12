---
title: Windows中的Microsoft Defender 脱机版
description: 可以直接从Windows Defender 防病毒应用使用Microsoft Defender 脱机版。 还可以管理其在网络中的部署方式。
keywords: scan，defender，脱机
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
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: ea7d316a7fc31724466dcd459ed72792cea817fd
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787679"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>运行并查看 Microsoft Defender 脱机扫描的结果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

Microsoft Defender 脱机版是一种反恶意软件扫描工具，可用于从受信任的环境启动和运行扫描。 扫描从普通Windows内核外部运行，因此它可以针对尝试绕过Windows shell 的恶意软件，例如感染或覆盖 MBR)  (主启动记录的病毒和根基。

如果怀疑存在恶意软件感染，或者想要在恶意软件爆发后确认彻底清理终结点，则可以使用Microsoft Defender 脱机版。

在Windows 10和Windows 11中，Microsoft Defender 脱机版可以直接从[Windows 安全中心应用](microsoft-defender-security-center-antivirus.md)单击一下即可运行。 在早期版本的Windows中，用户必须安装Microsoft Defender 脱机版以启动媒体、重启终结点和加载可启动媒体。

## <a name="prerequisites-and-requirements"></a>先决条件和要求

Windows 10和Windows 11中的Microsoft Defender 脱机版具有与Windows 10相同的硬件要求。

有关Windows 10和Windows 11要求的详细信息，请参阅以下主题：

- [最低硬件要求](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [硬件组件准则](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> MICROSOFT DEFENDER 脱机版在具有 ARM 处理器的计算机或Windows服务器库存保留单元上不受支持。

若要从终结点运行Microsoft Defender 脱机版，必须使用管理员权限登录用户。

## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender 脱机版更新

Microsoft Defender 脱机版使用终结点上提供的最新保护更新;每当更新Windows Defender 防病毒时都会更新。

> [!NOTE]
> 在运行脱机扫描之前，应尝试更新 Microsoft Defender AV 保护。 可以使用组策略强制更新，或者不管你通常如何将更新部署到终结点，也可以手动从[Microsoft 恶意软件防护中心](https://www.microsoft.com/security/portal/definitions/adl.aspx)下载和安装最新的保护更新。

有关详细信息，请参阅[“管理Microsoft Defender 防病毒安全智能更新](manage-protection-updates-microsoft-defender-antivirus.md)”主题。

## <a name="usage-scenarios"></a>使用方案

Windows 10版本 1607 中，可以手动强制执行脱机扫描。 或者，如果Windows Defender确定Microsoft Defender 脱机版需要运行，则会在终结点上提示用户。

如果使用脱机扫描来管理终结点，则在Microsoft Endpoint Manager中也会显示执行脱机扫描的需要。

通过通知可能会出现提示，如下所示：

:::image type="content" source="../../media/notification.png" alt-text="要运行Microsoft Defender 脱机版的通知" lightbox="../../media/notification.png":::

还将在Windows Defender客户端中通知用户。

在Configuration Manager中，可以通过导航到监视 **>概述>安全> Endpoint Protection状态> System Center Endpoint Protection状态** 来标识终结点的状态。

Microsoft Defender 脱机版扫描在 **恶意软件修正状态** 下指示为 **需要脱机扫描**。

:::image type="content" source="../../media/sccm-wdo.png" alt-text="扫描Microsoft Defender 脱机版的指示器" lightbox="../../media/sccm-wdo.png":::

## <a name="configure-notifications"></a>配置通知

Microsoft Defender 脱机版通知是在与其他 Microsoft Defender AV 通知相同的策略设置中配置的。

有关Windows Defender中的通知的详细信息，请参阅[“配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)”主题。

## <a name="run-a-scan"></a>运行扫描

> [!IMPORTANT]
> 在使用Microsoft Defender 脱机版之前，请确保保存任何文件并关闭正在运行的程序。 Microsoft Defender 脱机版扫描大约需要 15 分钟才能运行。 扫描完成后，它将重启终结点。 扫描是在通常的Windows操作环境之外执行的。 用户界面将显示与Windows Defender执行的正常扫描不同。 扫描完成后，终结点将重新启动，Windows将正常加载。

可以使用以下内容运行Microsoft Defender 脱机版扫描：

- PowerShell
- Windows Management Instrumentation (WMI)
- Windows 安全中心应用



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>使用 PowerShell cmdlet 运行脱机扫描

使用以下 cmdlet：

```PowerShell
Start-MpWDOScan
```

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅[使用 PowerShell cmdlet 配置和运行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender 防病毒 cmdlet](/powershell/module/defender/)。

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>使用 Windows 管理指令 (WMI) 运行脱机扫描

使用 [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 类运行脱机扫描。

以下 WMI 脚本片段将立即运行Microsoft Defender 脱机版扫描，这将导致终结点重启、运行脱机扫描，然后重启并启动到Windows。

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start
```

有关详细信息，请参阅以下内容：

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>使用Windows Defender安全应用运行脱机扫描

1. 通过单击任务栏中的盾牌图标或在开始菜单中搜索Defender for Cloud，打开 **Windows 安全中心** 应用。

2. 单击 **“病毒&威胁防护** ”磁贴 (或左侧菜单栏) 的防护图标，然后单击 **“高级扫描** ”标签：

3. 选择 **Microsoft Defender 脱机版扫描**，然后立即单击 **“扫描**”。

    > [!NOTE]
    > 在 Windows 10 版本 1607 中，脱机扫描可以从 **Windows 设置****更新&**\>安全\>**Windows Defender** 或从Windows Defender客户端运行。

## <a name="review-scan-results"></a>查看扫描结果

Microsoft Defender 脱机版扫描结果将列在[Windows 安全中心应用的“扫描历史记录”部分](microsoft-defender-security-center-antivirus.md)中。

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

- [自定义、启动和查看扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
