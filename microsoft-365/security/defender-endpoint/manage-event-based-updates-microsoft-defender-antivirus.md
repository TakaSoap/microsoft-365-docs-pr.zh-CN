---
title: 在特定事件后应用 Microsoft Defender 防病毒更新
description: 管理 Microsoft Defender 防病毒在启动或接收云提供的检测报告后应用安全智能更新的方式。
keywords: 更新， 保护， 强制更新， 事件， 启动， 检查最新， 通知
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 78a04105fce0a3a1f9f7ea3f9ee993dd53750f3f
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764551"
---
# <a name="manage-event-based-forced-updates"></a>管理基于事件的强制更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防病毒允许你确定更新是应 (还是不应) 某些事件之后发生，例如启动时还是从云提供的保护服务接收特定报告之后。

## <a name="check-for-protection-updates-before-running-a-scan"></a>在运行扫描之前检查保护更新

可以使用 Microsoft Endpoint Configuration Manager、组策略、PowerShell cmdlet 和 WMI 强制 Microsoft Defender 防病毒在运行计划扫描之前检查和下载保护更新。

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a>运行扫描之前，使用 Configuration Manager 检查保护更新

1. 在 Microsoft Endpoint Manager 控制台上，打开要更改的反恶意软件策略 (单击左侧导航窗格中的"资产和合规性"，然后将树展开到"终结点保护反恶意软件策略概述")  >    >  

2. 转到计划 **扫描** 部分，将运行扫描之前检查最新的安全 **智能更新** 设置为 **是**。

3. 单击“**确定**”。

4. [像往常一样部署更新的策略](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a>运行扫描之前，使用组策略检查保护更新

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**

2. 使用组 **策略管理编辑器转到** 计算机 **配置**。

3. 单击 **"策略****"，然后单击"管理模板"。**

4. 将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **扫描**。

5. 在运行计划 **扫描之前** ，双击检查最新的病毒和间谍软件定义，将选项设置为 **已启用**。

6. 单击“**确定**”。

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a>运行扫描之前，使用 PowerShell cmdlet 检查保护更新

使用以下 cmdlet：

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

有关详细信息，请参阅使用[PowerShell cmdlet 配置](use-powershell-cmdlets-microsoft-defender-antivirus.md)和运行 Microsoft Defender 防病毒和[Defender cmdlet。](/powershell/module/defender/index)

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a>使用 Windows Management Instruction (WMI) 在运行扫描之前检查保护更新

对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
CheckForSignaturesBeforeRunningScan
```

有关详细信息，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="check-for-protection-updates-on-startup"></a>启动时检查保护更新

可以使用组策略强制 Microsoft Defender 防病毒在计算机启动时检查和下载保护更新。

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**

2. 使用组 **策略管理编辑器转到** 计算机 **配置**。

3. 单击 **"策略****"，然后单击"管理模板"。**

4. 将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **安全智能更新**。

5. 双击启动时 **检查最新的病毒和** 间谍软件定义，将选项设置为 **已启用**。 

6. 单击“**确定**”。

您还可以使用组策略、PowerShell 或 WMI 将 Microsoft Defender 防病毒配置为在启动时检查更新，即使更新未运行。

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>当 Microsoft Defender 防病毒不存在时，使用组策略下载更新

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**

2. 使用组 **策略管理编辑器，** 转到计算机 **配置**。

3. 单击 **"策略****"，然后单击"管理模板"。**

4. 将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **安全智能更新**。

5. 双击启动时 **启动安全智能更新** ，将选项设置为 **已启用**。

6. 单击“**确定**”。

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>当 Microsoft Defender 防病毒不存在时，使用 PowerShell cmdlet 下载更新

使用以下 cmdlet：

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

有关详细信息，请参阅使用 [PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md) 管理 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/index) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a>使用 Windows Management Instruction (WMI) 在 Microsoft Defender 防病毒不存在时下载更新

对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

有关详细信息，请参阅Windows Defender [WMIv2 API。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a>允许对基于云保护的保护进行临时更改

Microsoft Defender AV 可以基于云保护更改其保护。 此类更改可能会发生在正常或计划的保护更新之外。

如果你已启用云保护，Microsoft Defender AV 会将其可疑的文件发送到Windows Defender云。 如果云服务报告该文件是恶意文件，并且最近一次保护更新中检测到该文件，可以使用组策略配置 Microsoft Defender AV 以自动接收该保护更新。 也可以应用其他重要的保护更新。

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a>使用组策略根据云提供的保护自动下载最近更新

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**

2. 使用组 **策略管理编辑器转到** 计算机 **配置**。

3. 单击 **"策略****"，然后单击"管理模板"。**

4. 将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **安全智能更新**。

5. 双击允许基于 Microsoft **MAPS** 报告进行实时安全智能更新，将选项设置为 **已启用**。 单击" **确定**"。

6. **允许通知禁用 Microsoft MAPS 的基于** 定义的报告，将选项设置为 **已启用**。 单击" **确定**"。
    
> [!NOTE]
> **允许通知以禁用基于定义的报告** 使 Microsoft MAPS 可以禁用已知导致误报报告的定义。 必须配置计算机以加入 Microsoft MAPS，此函数正常运行。

## <a name="see-also"></a>另请参阅

- [部署 Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
- [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)