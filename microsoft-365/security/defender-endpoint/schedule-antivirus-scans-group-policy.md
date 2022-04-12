---
title: 使用组策略安排防病毒扫描
description: 使用组策略设置防病毒扫描
keywords: 快速扫描，完全扫描，计划，组策略，防病毒
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/10/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: dbd3f2b4342757509a6440ff87a112b75b663f22
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788031"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>使用组策略安排防病毒扫描

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

本文介绍如何使用组策略配置计划的扫描。 若要详细了解计划扫描和扫描类型，请参阅[配置计划的快速或完整Microsoft Defender 防病毒扫描](schedule-antivirus-scans.md)。 

## <a name="configure-antivirus-scans-using-group-policy"></a>使用组策略配置防病毒扫描

1. 在组策略管理计算机上的组策略编辑器\>中，转到 **计算机配置** \> **管理模板****Windows组件** \> **Microsoft Defender 防病毒** \> **扫描**。

2. 右键单击要配置的组策略对象，然后选择 **“编辑**”。

3. 指定组策略对象的设置，然后选择 **“确定**”。 

4. 针对要配置的每个设置重复步骤 1-4。

5. 像平时一样部署组策略对象。 如果需要有关组策略对象的帮助，请参阅[创建组策略对象](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。

> [!NOTE]
> 配置计划扫描时， **设置仅在计算机开启但未在使用（** 默认情况下启用）时才启动计划扫描，这会要求计算机先空闲，从而影响预期的计划时间。
>
> 对于每周扫描，Windows服务器上的默认行为是在计算机处于空闲状态时在自动维护之外进行扫描。 Windows 10及更高版本的默认值是在计算机处于空闲状态时在自动维护期间进行扫描。 若要更改此行为，请通过禁用 **ScanOnlyIfIdle** 来修改设置，然后定义计划。

有关详细信息，请参阅 [“管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md) ”， [并阻止或允许用户本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主题。

## <a name="group-policy-settings-for-scheduling-scans"></a>组策略计划扫描的设置

| 位置 | 设置 | 说明 | 默认设置 (（如果未配置）)  |
|:---|:---|:---|:---|
| 扫描 | 指定用于计划扫描的扫描类型 | 快速扫描 |
| 扫描 | 指定运行计划扫描的星期几 | 指定 (或从不) 运行扫描的日期。 | 从不 |
| 扫描 | 指定运行计划扫描的一天中的时间 | 指定午夜后的分钟数 (例如，输入 **60** 表示凌晨 1 点) 。 | 凌晨 2 点 |
| 根 | 随机化计划的任务时间 |在Microsoft Defender 防病毒中，将扫描的开始时间随机化为从 0 到 23 小时的任何间隔。 <p>在 [SCEP](/mem/intune/protect/certificates-scep-configure) 中，将扫描随机化为任意间隔加或减 30 分钟。 这在虚拟机或 VDI 部署中非常有用。 | 已启用 |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>组策略在终结点未使用时计划扫描的设置

| 位置 | 设置 | 说明 | 默认设置 (（如果未配置）)  |
|:---|:---|:---|:---|
| 扫描 | 仅当计算机处于打开状态但未使用时才启动计划扫描 | 除非计算机处于打开状态但未在使用中，否则计划扫描将不会运行 | 已启用 |

> [!NOTE]
> 在计划扫描终结点未使用的时间时，扫描不遵循 CPU 限制配置，并且会充分利用可用的资源，以尽可能快地完成扫描。

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>组策略用于计划所需的修正扫描的设置

| 位置 | 设置 | 说明 | 默认设置 (（如果未配置）)  |
|---|---|---|---|
| 修复 | 指定运行计划的完整扫描以完成修正的星期几 | 指定 (或从不) 运行扫描的日期。 | 从不 |
| 修复 | 指定运行计划的完整扫描以完成修正的一天中的时间 | 指定午夜后的分钟数 (例如，输入 **60** 表示凌晨 1 点)  | 凌晨 2 点 |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>组策略用于计划每日扫描的设置

| 位置 | 设置 | 说明 | 默认设置 (（如果未配置）)  |
|:---|:---|:---|:---|
| 扫描 | 指定每天运行快速扫描的间隔 | 指定下一次快速扫描之前应经过的小时数。 例如，若要每两小时运行一次，请输入 **2**，每天输入一次，输入 **24**。 输入 **0** 以从不运行每日快速扫描。 | 从不 |
| 扫描 | 指定每日快速扫描的时间 | 指定午夜后的分钟数 (例如，输入 **60** 表示凌晨 1 点)  | 凌晨 2 点 |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>组策略保护更新后计划扫描的设置

| 位置 | 设置 | 说明 | 默认设置 (（如果未配置）) |
|:---|:---|:---|:---|
| 签名更新 | 安全智能更新后启用扫描 | 下载新的保护更新后，将立即进行扫描 | 已启用 |

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)