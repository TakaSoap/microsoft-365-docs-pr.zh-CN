---
title: 使用组策略安排防病毒扫描
description: 使用组策略设置防病毒扫描
keywords: 快速扫描， 完全扫描， 计划， 组策略， 防病毒
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
ms.openlocfilehash: 0e5e22b1c3f73f39ad65df39fd25e9b7b6e8a913
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61163046"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>使用组策略安排防病毒扫描

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

本文介绍如何使用组策略配置计划扫描。 若要了解有关计划扫描和扫描类型有关详细信息，请参阅配置计划的快速或完全Microsoft Defender 防病毒[扫描](schedule-antivirus-scans.md)。 

## <a name="configure-antivirus-scans-using-group-policy"></a>使用组策略配置防病毒扫描

1. 在组策略管理计算机上，在组策略编辑器中，转到计算机配置管理模板 Windows 组件 Microsoft Defender 防病毒 \>  \>  \>  \> **扫描**。

2. 右键单击要配置的组策略对象， **然后选择编辑**。

3. 指定组策略对象的设置，**然后选择确定。** 

4. 对要配置的每个设置重复步骤 1-4。

5. 像平常一样部署组策略对象。 如果需要有关组策略对象的帮助，请参阅 [创建组策略对象](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。

> [!NOTE]
> 在配置计划扫描时，设置"仅在计算机打开但没有使用时启动计划扫描"（默认启用）可以通过要求计算机先处于空闲状态来影响预期的计划时间。
>
> 对于每周扫描，Windows服务器的默认行为是在计算机空闲时在自动维护之外进行扫描。 默认情况下，Windows 10在计算机空闲时在自动维护期间扫描。 若要更改此行为，请通过禁用 **ScanOnlyIfIdle** 修改设置，然后定义计划。

有关详细信息，请参阅管理 [何时](manage-protection-update-schedule-microsoft-defender-antivirus.md) 应下载和应用保护更新和阻止或允许用户 [本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) 主题。

## <a name="group-policy-settings-for-scheduling-scans"></a>计划扫描的组策略设置

| 位置 | 设置 | 说明 | 如果未配置 (，则默认设置)  |
|:---|:---|:---|:---|
| 扫描 | 指定用于计划扫描的扫描类型 | 快速扫描 |
| 扫描 | 指定一周中的哪些天运行计划扫描 | 指定运行 () 或从不运行扫描的日。 | 从不 |
| 扫描 | 指定运行计划扫描的时间 | 例如，指定午夜后 (分钟数，输入 **60** 表示上午 1 点) 。 | 2 a.m. |
| 根 | 随机化计划任务时间 |在Microsoft Defender 防病毒中，将扫描的开始时间随机化为 0 到 23 小时之间的任意间隔。 <p>在 [SCEP](/mem/intune/protect/certificates-scep-configure)中，将扫描随机化为任意间隔加或减 30 分钟。 这可在虚拟机或 VDI 部署中非常有用。 | 已启用 |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>计划终结点不使用时扫描的组策略设置

| 位置 | 设置 | 说明 | 如果未配置 (，则默认设置)  |
|:---|:---|:---|:---|
| 扫描 | 仅在计算机打开但没有使用时启动计划扫描 | 计划的扫描将不会运行，除非计算机已打开但没有使用 | 已启用 |

> [!NOTE]
> 在终结点不使用时计划扫描时，扫描不会接受 CPU 限制配置，并且将充分利用可用资源尽快完成扫描。

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>用于计划修正所需扫描的组策略设置

| 位置 | 设置 | 说明 | 如果未配置 (，则默认设置)  |
|---|---|---|---|
| 修正 | 指定一周中的哪些天运行计划的完全扫描以完成修正 | 指定运行 () 或从不运行扫描的日。 | 从不 |
| 修正 | 指定一天中运行计划完整扫描以完成修正的时间 | 指定午夜过后的分钟数 (例如，输入 **60** 表示凌晨 1 点)  | 2 a.m. |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>用于计划每日扫描的组策略设置

| 位置 | 设置 | 说明 | 如果未配置 (，则默认设置)  |
|:---|:---|:---|:---|
| 扫描 | 指定每天运行快速扫描的间隔 | 指定下一次快速扫描之前应经过的小时数。 例如，若要每两小时运行一次，请输入 **2，** 一天一次，请输入 **24**。 输入 **0** 从不运行每日快速扫描。 | 从不 |
| 扫描 | 指定每日快速扫描的时间 | 指定午夜过后的分钟数 (例如，输入 **60** 表示凌晨 1 点)  | 2 a.m. |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>用于计划保护更新后扫描的组策略设置

| 位置 | 设置 | 说明 | 如果未配置 (，则默认设置) |
|:---|:---|:---|:---|
| 签名更新 | 在安全智能更新后打开扫描 | 扫描将在下载新保护更新后立即发生 | 已启用 |

