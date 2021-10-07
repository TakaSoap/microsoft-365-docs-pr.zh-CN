---
title: 将 Microsoft Defender AV 保护更新应用到过期终结点
description: 定义何时以及如何对一段时间未更新的终结点应用更新。
keywords: 更新， 保护， 过期， 过时， 旧， 跟进
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 1232d9fe6e604c0b4fea5598cf3b745ea6864cb7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151960"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a>管理 Microsoft Defender 防病毒更新并扫描过期的终结点

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防病毒定义终结点可以避免更新的所需时间，或定义在需要更新和扫描自身之前可以错过的扫描次数。 在设备不经常连接到公司或外部网络或者不每天使用的设备的环境中，这尤其有用。

例如，使用特定电脑的员工休息三天，在此期间不登录到其电脑。

当用户返回工作并登录到其电脑时，Microsoft Defender 防病毒将立即检查并下载最新的保护更新，并运行扫描。

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a>为一段时间未更新的终结点设置跟进保护更新

如果Microsoft Defender 防病毒在指定的时段内未下载保护更新，可以设置为在下次登录时自动检查并下载最新更新。 如果你已全局禁用启动时的自动更新 [下载，这将非常有用](manage-event-based-updates-microsoft-defender-antivirus.md)。

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a>使用 Configuration Manager 配置跟进保护更新

1. 在 Microsoft Endpoint Manager 控制台上，打开要更改的反恶意软件策略 (单击左侧导航窗格中的"资产和合规性"，然后将树展开到"反恶意软件策略Endpoint Protection概述)  \>  \> 

2. 转到" **安全智能更新"** 部分并配置以下设置：

    1. 将 **"如果客户端计算机在连续计划更新** 两次以上时处于脱机状态，则强制进行安全智能更新"设置为 **"是"。**
    2. 对于  **"如果配置管理器用作** 安全智能更新的源..."，请指定配置管理器提供的保护更新应视为过期的小时数。 这将基于定义的回退源顺序，导致使用下一 [个更新位置](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)。

3. 单击“**确定**”。

4. [像往常一样部署更新的策略](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a>使用组策略启用和配置跟进更新功能

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

2. 在组 **策略管理编辑器中** ，转到计算机 **配置**。

3. 单击 **"策略****"，然后单击"管理模板"。**

4. 展开树以Windows **签名> Microsoft Defender 防病毒 >组件**。

5. 双击定义需要更新安全智能的天数设置，将选项设置为 **已启用**。 输入希望 Microsoft Defender AV 检查并下载最新保护更新的天数。

6. 单击“**确定**”。

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a>使用 PowerShell cmdlet 配置跟进保护更新

使用以下 cmdlet：

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

请参阅[使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)配置和运行 Microsoft Defender 防病毒 和[Defender cmdlet，](/powershell/module/defender/)详细了解如何将 PowerShell 与 Microsoft Defender 防病毒。

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a>使用 Windows Management Instruction (WMI) 配置跟进保护更新

对 [**以下** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
SignatureUpdateCatchupInterval
```

有关详细信息和允许的参数，请参阅以下内容：

- [Windows DefenderWMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a>设置保护报告为过期前的天数

还可以指定保护被视为旧Microsoft Defender 防病毒过期的天数。 指定天数后，客户端将自行报告为过期，并向电脑用户显示错误。 还可能导致 Microsoft Defender 防病毒 尝试基于定义的回退源顺序[ (](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)从其他源) 下载更新，例如将 WSUS 或 Microsoft Update 设置为第一个源后将 MMPC 用作辅助源时。

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a>使用组策略指定保护被视为过期前的天数

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

2. 在组 **策略管理编辑器中** ，转到计算机 **配置**。

3. 单击 **"策略****"，然后单击"管理模板"。**

4. 展开树以 **Windows签名> Microsoft Defender 防病毒 >组件并** 配置以下设置：

    1. 双击定义 **间谍软件定义** 被视为过期的天数，将选项设置为 **已启用**。 输入希望 Microsoft Defender AV 考虑间谍软件安全智能过期的天数。

    2. 单击“**确定**”。

    3. 双击"**定义病毒定义** 被视为过期的天数"，将选项设置为"**已启用"。** 输入您希望 Microsoft Defender AV 考虑病毒安全智能过期的天数。

    4. 单击“**确定**”。

## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a>为一段时间未扫描的终结点设置跟进扫描

你可以设置连续计划扫描的丢失次数，然后Microsoft Defender 防病毒扫描。

启用此功能的过程为：

1. 设置至少一个计划扫描 (请参阅计划 [扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 主题) 。
2. 启用跟进扫描功能。
3. 定义在进行跟进扫描之前可以跳过的扫描数。

可以针对完整扫描和快速扫描启用此功能。

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a>使用组策略启用和配置跟进扫描功能

1. 确保已设置至少一个计划扫描。

2. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

3. 在组 **策略管理编辑器中** ，转到计算机 **配置**。

4. 单击 **"策略****"，然后单击"管理模板"。**

5. 展开树以Windows **扫描> Microsoft Defender 防病毒 >组件** 并配置以下设置：

    1. 如果已设置计划快速扫描，请双击"启用捕获快速扫描"设置，将该选项设置为 **"已启用"。**
    2. 如果已设置计划的完全扫描，请双击"启用捕获完全 **扫描**"设置，将该选项设置为 **"已启用"。** 单击“**确定**”。
    3. 双击定义 **强制进行** 跟进扫描的天数设置，将选项设置为 **已启用**。
    4. 输入在用户下次登录电脑时自动运行扫描之前可能错过的扫描数。 运行的扫描类型由指定要用于计划扫描的扫描类型确定 (请参阅计划扫描主题) 。 [](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 单击“**确定**”。

> [!NOTE]
> 组策略设置标题是指天数。 但是，该设置应用于在运行 (扫描) 之前扫描次数。

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a>使用 PowerShell cmdlet 配置跟进扫描

使用以下 cmdlet：

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

请参阅[使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)管理 Microsoft Defender 防病毒[和 Defender cmdlet，](/powershell/module/defender/)详细了解如何将 PowerShell 与 Microsoft Defender 防病毒。

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a>使用 Windows Management Instruction (WMI) 配置跟进扫描

对 [**以下** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

有关详细信息和允许的参数，请参阅以下内容：

- [Windows DefenderWMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-configuration-manager-to-configure-catch-up-scans"></a>使用 Configuration Manager 配置跟进扫描

1. 在 Microsoft Endpoint Manager 控制台上，打开要更改的反恶意软件策略 (单击左侧导航窗格中的"资产和合规性"，然后将树展开到"反恶意软件策略Endpoint Protection概述)  \>  \> 

2. 转到计划 **扫描** 部分，如果客户端计算机脱机，则强制扫描所选扫描类型 **...** 到 **是**。

3. 单击“**确定**”。

4. [像往常一样部署更新的策略](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

## <a name="related-articles"></a>相关文章

- [部署Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
- [管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)
- [管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
