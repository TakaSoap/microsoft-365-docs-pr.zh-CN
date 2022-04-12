---
title: 将 Microsoft Defender AV 保护更新应用于过期终结点
description: 定义何时以及如何为一段时间内未更新的终结点应用更新。
keywords: 更新， 保护， 过时， 过时， 旧， 赶上
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 0f7f42662bf698f6e3a092539e58a8a9de529b24
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789461"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>管理 Microsoft Defender 防病毒更新并扫描过期的终结点

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

Microsoft Defender 防病毒使你能够定义终结点可以避免更新的时间，或者在需要更新和扫描之前可能错过多少次扫描。 在设备不经常连接到公司或外部网络或不每天使用的设备的环境中，这尤其有用。

例如，使用特定电脑的员工将休息三天，在此期间不会登录到其电脑。

当用户返回工作并登录到其电脑时，Microsoft Defender 防病毒将立即检查并下载最新的保护更新，并运行扫描。

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>为一段时间未更新的终结点设置追赶保护更新

如果Microsoft Defender 防病毒在指定的时间段内未下载保护更新，可以将其设置为在下一次登录时自动检查和下载最新更新。 如果 [在启动时已全局禁用自动更新下载，](manage-event-based-updates-microsoft-defender-antivirus.md)这非常有用。

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>使用Configuration Manager配置追赶保护更新

1. 在Microsoft Endpoint Manager控制台上，打开要更改的反恶意软件策略 (单击左侧导航窗格中的 **“资产和符合性**”，然后将树展开为“**反恶意软件** 策略 **概述** \> **Endpoint Protection**\>) 

2. 转到 **“安全智能更新** ”部分并配置以下设置：

    1. **如果客户端计算机连续两次以上计划更新** 为 **“是**”，请设置强制安全智能更新。
    2. 对于 **If Configuration Manager用作安全智能更新的源...**，请指定应将Configuration Manager提供的保护更新视为过期的小时。 这将导致根据定义的 [回退源顺序](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)使用下一个更新位置。

3. 单击“确定”。

4. [像往常一样部署更新的策略](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>使用组策略启用和配置追赶更新功能

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 在 **组策略管理编辑器** 中转到 **计算机配置**。

3. 单击 **“策略** ”，然后单击 **“管理模板**”。

4. 将树展开为 **> Microsoft Defender 防病毒 >签名更新Windows组件**。

5. 双击“ **定义需要追加安全智能更新”设置的天数** ，并将选项设置为 **“已启用**”。 输入希望 Microsoft Defender AV 检查和下载最新保护更新的天数。

6. 单击“确定”。

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>使用 PowerShell cmdlet 配置追赶保护更新

使用以下 cmdlet：

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅[使用 PowerShell cmdlet 配置和运行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender 防病毒 cmdlet](/powershell/module/defender/)。

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>使用Windows管理指令 (WMI) 配置追赶保护更新

对以下属性使用 MSFT_MpPreference 类的 [**Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))：

```WMI
SignatureUpdateCatchupInterval
```

有关详细信息和允许的参数，请参阅以下内容：

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>将保护报告为过期之前的天数

还可以指定Microsoft Defender 防病毒保护被视为旧或过期的天数。 指定天数后，客户端会将自己报告为过期，并向电脑用户显示错误。 它还可能导致Microsoft Defender 防病毒尝试根据定义的[回退源顺序](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)) 从 (的其他源下载更新，例如在将 WSUS 或 Microsoft Update 设置为第一个源后，将 MMPC 用作辅助源时。

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>使用组策略指定保护被视为过期之前的天数

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 在 **组策略管理编辑器** 中转到 **计算机配置**。

3. 单击 **“策略** ”，然后单击 **“管理模板**”。

4. 展开树以 **Windows组件> Microsoft Defender 防病毒 >签名更新** 并配置以下设置：

    1. 双击 **“定义间谍软件定义被视为过期之前的天数** ”，并将选项设置为 **“已启用**”。 输入希望 Microsoft Defender AV 将间谍软件安全智能视为过期的天数。

    2. 单击“确定”。

    3. 双击 **“定义将病毒定义视为过期之前的天数** ”，并将选项设置为 **“已启用**”。 输入希望 Microsoft Defender AV 将病毒安全智能视为过期的天数。

    4. 单击“确定”。

## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>为一段时间未扫描的终结点设置追赶扫描

可以设置在Microsoft Defender 防病毒将强制扫描之前可能错过的连续计划扫描数。

启用此功能的过程是：

1. 设置至少一个计划的扫描 (请参阅 [计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 主题) 。
2. 启用追赶扫描功能。
3. 定义在执行追赶扫描之前可以跳过的扫描数。

可以为完整扫描和快速扫描启用此功能。

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>使用组策略启用和配置追赶扫描功能

1. 确保已设置至少一个计划的扫描。

2. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后单击 **“编辑**”。

3. 在 **组策略管理编辑器** 中转到 **计算机配置**。

4. 单击 **“策略** ”，然后单击 **“管理模板**”。

5. 展开树以 **Windows组件> Microsoft Defender 防病毒 >扫描** 并配置以下设置：

    1. 如果已设置计划的快速扫描，请双击 **“启用”快速扫描** 设置，并将选项设置为 **“已启用**”。
    2. 如果已设置计划的完整扫描，请双击 **“启用”补全扫描** 设置，并将选项设置为 **“已启用**”。 单击“确定”。
    3. 双击“ **定义追加扫描被强制设置后的天数** ”，并将选项设置为 **“已启用**”。
    4. 输入在用户下一次登录到电脑时自动运行扫描之前可能错过的扫描次数。 运行的扫描类型由 **指定用于计划扫描的扫描类型** 确定 (请参阅 [计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 主题) 。 单击“确定”。

> [!NOTE]
> 组策略设置标题是指天数。 但是，该设置应用于扫描次数， (不会在运行追赶扫描之前) 天。

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>使用 PowerShell cmdlet 配置追赶扫描

使用以下 cmdlet：

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

有关如何将 PowerShell 与Microsoft Defender 防病毒配合使用的详细信息，请参阅[使用 PowerShell cmdlet 管理 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 和 [Defender 防病毒 cmdlet](/powershell/module/defender/)。

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>使用Windows管理指令 (WMI) 来配置追赶扫描

对以下属性使用 MSFT_MpPreference 类的 [**Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))：

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

有关详细信息和允许的参数，请参阅以下内容：

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>使用Configuration Manager配置追赶扫描

1. 在Microsoft Endpoint Manager控制台上，打开要更改的反恶意软件策略 (单击左侧导航窗格中的 **“资产和符合性**”，然后将树展开为“**反恶意软件** 策略 **概述** \> **Endpoint Protection**\>) 

2. 转到 **“计划扫描”** 部分，**如果客户端计算机处于脱机状态，请强制扫描所选扫描类型...** 

3. 单击“确定”。

4. [像往常一样部署更新的策略](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

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

- [部署Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
- [管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)
- [管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
