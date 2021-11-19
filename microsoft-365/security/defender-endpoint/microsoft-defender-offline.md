---
title: Microsoft Defender 脱机版Windows
description: 你可以直接从Microsoft Defender 脱机版直接使用Windows Defender 防病毒应用。 还可以管理如何在网络中部署它。
keywords: 扫描， defender， 脱机
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
ms.openlocfilehash: 4956382717a9b8c5a7856367fa6c3166c64fd1c9
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110891"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>运行并查看 Microsoft Defender 脱机扫描的结果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 脱机版是一种反恶意软件扫描工具，允许你从受信任的环境启动和运行扫描。 扫描从正常的 Windows 内核外部运行，因此它可以针对尝试绕过 Windows shell 的恶意软件，例如感染或覆盖主启动记录 (MBR) 的病毒和 rootkit。

如果您怀疑Microsoft Defender 脱机版感染，或者希望确认恶意软件爆发后对终结点进行彻底清理，可以使用此筛选器。

在Windows 10和Windows 11中，Microsoft Defender 脱机版可以直接从应用单击一次即可Windows 安全中心[运行](microsoft-defender-security-center-antivirus.md)。 在早期版本的 Windows，用户必须Microsoft Defender 脱机版可启动媒体、重新启动终结点并加载可启动媒体。

## <a name="prerequisites-and-requirements"></a>先决条件和要求

Microsoft Defender 脱机版中Windows 10 Windows 11和 Windows 10 具有相同的硬件Windows 10。

有关满足Windows 10和Windows 11要求，请参阅下列主题：

- [最低硬件要求](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [硬件组件准则](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender 脱机版处理器的计算机或 ARM 服务器库存Windows不支持此配置。

若要Microsoft Defender 脱机版终结点运行应用程序，用户必须使用管理员权限登录。

## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender 脱机版更新

Microsoft Defender 脱机版使用终结点上提供的最新保护更新;每当更新Windows Defender 防病毒更新。

> [!NOTE]
> 在运行脱机扫描之前，应尝试更新 Microsoft Defender AV 保护。 可以使用组策略强制更新，或者通常将更新部署到终结点，也可以手动下载并安装来自 Microsoft 恶意软件防护中心[的最新保护更新](https://www.microsoft.com/security/portal/definitions/adl.aspx)。

有关详细信息，[请参阅](manage-protection-updates-microsoft-defender-antivirus.md)Microsoft Defender 防病毒安全智能更新主题。

## <a name="usage-scenarios"></a>使用方案

在Windows 10版本 1607 中，可以手动强制脱机扫描。 或者，Windows Defender确定Microsoft Defender 脱机版需要运行，它将在终结点上提示用户。

如果使用脱机扫描来管理终结点，Microsoft Endpoint Manager也会在客户端中显示需要执行脱机扫描。

该提示可以通过通知发生，类似于以下内容：

:::image type="content" source="../../media/notification.png" alt-text="运行 Microsoft Defender 脱机版。":::

用户还将在客户端中Windows Defender通知。

在 Configuration Manager 中，可以通过导航到"监视">"安全>状态"> Endpoint Protection"> System Center Endpoint Protection **终结点的状态**。

Microsoft Defender 脱机版扫描在"恶意软件修正状态"**下指示** 为 **"需要脱机扫描"。**

:::image type="content" source="../../media/sccm-wdo.png" alt-text="Microsoft Defender 脱机版扫描是必需的。":::

## <a name="configure-notifications"></a>配置通知

Microsoft Defender 脱机版通知与其他 Microsoft Defender AV 通知在同一策略设置中配置。

有关终结点中的通知Windows Defender，请参阅配置[终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)主题。

## <a name="run-a-scan"></a>运行扫描

> [!IMPORTANT]
> 使用前Microsoft Defender 脱机版，请确保保存所有文件并关闭正在运行的程序。 运行Microsoft Defender 脱机版扫描需要大约 15 分钟。 扫描完成后，它将重新启动终结点。 扫描在常规运行环境Windows执行。 用户界面将显示不同于由用户执行的正常Windows Defender。 扫描完成后，终结点将重新启动，Windows正常加载。

可以使用以下Microsoft Defender 脱机版运行自动扫描：

- PowerShell
- Windows Management Instrumentation (WMI)
- 应用程序Windows 安全中心应用程序



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>使用 PowerShell cmdlet 运行脱机扫描

使用以下 cmdlet：

```PowerShell
Start-MpWDOScan
```

请参阅[使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和[Defender for Cloud cmdlet，](/powershell/module/defender/)了解有关如何将 PowerShell 与 Microsoft Defender 防病毒 一Microsoft Defender 防病毒。

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>使用 Windows Management Instruction (WMI) 运行脱机扫描

使用 [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 类运行脱机扫描。

以下 WMI 脚本代码段将立即运行Microsoft Defender 脱机版扫描，这将导致终结点重新启动、运行脱机扫描，然后重新启动并启动到 Windows。

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start
```

有关详细信息，请参阅以下内容：

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>使用 Windows Defender 安全应用运行脱机扫描

1. 通过单击Windows 安全中心中的防护图标或搜索 **"Defender for Cloud"** 的"开始"菜单打开应用。

2. 单击病毒& **威胁** 防护磁贴 (左侧菜单栏上的防护图标或) 高级 **扫描** 标签：

3. 选择 **Microsoft Defender 脱机版扫描"，** 然后单击"**立即扫描"。**

    > [!NOTE]
    > 在 Windows 10 版本 1607 中，脱机扫描可以在 **Windows 设置** Update & 安全Windows Defender下运行，也可以从 \>  \> Windows Defender 客户端运行。

## <a name="review-scan-results"></a>查看扫描结果

Microsoft Defender 脱机版扫描结果将在应用 扫描历史记录部分Windows 安全中心[列出](microsoft-defender-security-center-antivirus.md)。

## <a name="related-articles"></a>相关文章

- [自定义、启动和查看扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
