---
title: 计划 Microsoft Defender 防病毒保护更新
description: 计划应下载保护更新的时间、时间和间隔
keywords: 更新， 安全基线， 计划更新
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e4ba9a438ff4640a556a236b50b0be6e816fc7e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689943"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a>管理何时应下载和应用保护更新的计划

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防病毒允许你确定何时应查找和下载更新。

可以按：为终结点计划更新： 

- 指定一周中的哪些天检查保护更新 
- 指定检查保护更新的时间间隔
- 指定检查保护更新的时间

还可以随机化每个终结点检查和下载保护更新的时间。 有关详细信息 [，请参阅计划](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 扫描主题。

## <a name="use-configuration-manager-to-schedule-protection-updates"></a>使用 Configuration Manager 计划保护更新

1.  在 Microsoft Endpoint Manager 控制台上，打开要更改的反恶意软件策略 (单击左侧导航窗格中的"资产和合规性"，然后将树展开到"终结点保护反恶意软件策略概述")  >    >  

2.  转到" **安全智能更新"** 部分。

3. 在特定时间检查和下载更新：
      1. 将 **"以特定间隔检查 Endpoint Protection 安全智能更新..."** 设置为 **0。**
      2. 将 **"每天检查 Endpoint Protection 安全智能更新..."** 设置为应检查更新的时间。
      3
4. 若要持续检查并下载更新，请以特定间隔将"检查 Endpoint Protection 安全智能更新 **..."** 设置为更新之间应发生的小时数。

5.  [像往常一样部署更新的策略](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。

## <a name="use-group-policy-to-schedule-protection-updates"></a>使用组策略计划保护更新

> [!IMPORTANT]
> 默认情况下，Microsoft Defender 防病毒将在任何计划扫描时间前 15 分钟检查更新。 启用这些设置将覆盖该默认设置。

1.  在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

3.  在组 **策略管理编辑器中** ，转到计算机 **配置**。

4.  单击 **"策略****"，然后单击"管理模板"。**

5.  将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **签名智能更新** 并配置以下设置：

    1. 双击指定 **一周中的哪些天检查** 安全智能更新设置，将选项设置为 **已启用**。 输入一周中的一天以检查更新。 单击“**确定**”。
    2. 双击指定 **检查安全智能更新的** 间隔设置，将选项设置为 **已启用**。 输入更新之间的小时数。 单击“**确定**”。
    3. 双击指定 **检查安全智能更新** 的时间设置，将选项设置为 **已启用**。 输入应检查更新的时间。 时间基于终结点的本地时间。 单击“**确定**”。


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a>使用 PowerShell cmdlet 计划保护更新

使用以下 cmdlet：

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

请参阅 [使用 PowerShell cmdlet](use-powershell-cmdlets-microsoft-defender-antivirus.md)  配置和运行 Microsoft Defender 防病毒和 [Defender cmdlet，](/powershell/module/defender/) 详细了解如何将 PowerShell 与 Microsoft Defender 防病毒一同使用。

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a>使用 Windows Management Instruction (WMI) 计划保护更新

对 [**下列** 属性MSFT_MpPreference](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))类的 Set 方法：

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

有关详细信息和允许的参数，请参阅以下内容：
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a>相关文章

- [部署 Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
- [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)
- [使用虚拟机管理移动设备和虚拟机 (更新) ](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)