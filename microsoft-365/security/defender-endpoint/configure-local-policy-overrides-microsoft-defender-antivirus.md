---
title: 为Microsoft Defender 防病毒设置配置本地替代
description: 在 Microsoft Defender AV 中启用或禁用用户本地更改设置。
keywords: 本地重写、本地策略、组策略、gpo、锁定、合并、列表
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: ae90694bab8191c2ad83fa1de7563bc2ba7643e8
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789747"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>阻止或允许用户在本地修改Microsoft Defender 防病毒策略设置


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

默认情况下，通过组策略对象部署到网络中终结点的Microsoft Defender 防病毒设置将阻止用户在本地更改设置。 可在某些实例中更改此项。

例如，可能需要允许某些用户组 (，例如安全研究人员和威胁调查员，) 进一步控制他们使用的终结点上的各个设置。

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>为Microsoft Defender 防病毒设置配置本地替代

这些策略的默认设置为 **“已禁用**”。

如果设置为 **“已启用**”，则终结点上的用户可以在适当的)  (对与 [Windows 安全中心](microsoft-defender-security-center-antivirus.md)应用、本地组策略设置和 PowerShell cmdlet 关联的设置进行更改。

下表列出了每个替代策略设置以及关联功能或设置的配置说明。

若要配置这些设置，请执行以下操作：

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 在 **组策略管理编辑器** 中转到 **“计算机配置**”，然后单击 **“管理模板**”。

3. 将树展开为 **Windows组件** > **Microsoft Defender 防病毒** 然后在本文 (设置表中指定 **的位置**) 。

4. 双击下表中指定的策略 **设置** ，并将选项设置为所需的配置。 单击 **“确定**”，并重复任何其他设置。

5. 像往常一样部署组策略对象。

## <a name="table-of-settings"></a>设置表

<br/><br/>

| 位置 | 设置 | 文章 |
|---|---|---|---|
| 地图 |配置本地设置替代以向 Microsoft MAPS 报告|[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md) |
| 隔离|配置本地设置替代，以便从隔离文件夹中删除项|[配置扫描修正](configure-remediation-microsoft-defender-antivirus.md) |
| 实时保护|配置本地设置替代以监视计算机上的文件和程序活动|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 实时保护|配置本地设置替代以监视传入和传出文件活动 | [启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 实时保护|配置本地设置替代以扫描所有下载的文件和附件|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 实时保护|配置本地设置替代以启用行为监视|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 实时保护|配置本地设置替代以启用实时保护|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 修复|为一天中的时间配置本地设置重写以运行计划的完整扫描以完成修正|[配置扫描修正](configure-remediation-microsoft-defender-antivirus.md) |
| 扫描|为 CPU 利用率的最大百分比配置本地设置替代|[配置和运行扫描](run-scan-microsoft-defender-antivirus.md) |
| 扫描|为计划扫描日配置本地设置替代|[配置计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 扫描|为计划的快速扫描时间配置本地设置替代|[配置计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 扫描|为计划的扫描时间配置本地设置替代|[配置计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 扫描|配置要用于计划扫描的扫描类型的本地设置替代|[配置计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>配置本地和全局定义的威胁修正和排除列表的合并方式

还可以配置本地定义列表与全局定义列表的组合或合并方式。 此设置适用于 [排除列表](configure-exclusions-microsoft-defender-antivirus.md)、 [指定的修正列表](configure-remediation-microsoft-defender-antivirus.md)和 [攻击面减少](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。

默认情况下，已在本地组策略和Windows 安全中心应用中配置的列表与已在网络上部署的相应组策略对象定义的列表合并。 如果存在冲突，则全局定义的列表优先。

可以禁用此设置，以确保仅使用全局定义的列表 (，例如来自任何已部署 GPO) 的列表。

### <a name="use-group-policy-to-disable-local-list-merging"></a>使用组策略禁用本地列表合并

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 在 **组策略管理编辑器** 中转到 **“计算机配置**”，然后单击 **“管理模板**”。

3. 展开树以 **> Microsoft Defender 防病毒Windows组件**。

4. 双击 **“配置列表的本地管理员合并行为** ”，并将选项设置为 **“已禁用**”。 单击“确定”。

> [!NOTE]
> 如果禁用本地列表合并，它将覆盖受控文件夹访问设置。 它还覆盖本地管理员设置的任何受保护文件夹或允许的应用。 有关受控文件夹访问设置的详细信息，请参阅[Windows 安全中心中允许阻止的应用](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="related-topics"></a>相关主题

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [配置最终用户与Microsoft Defender 防病毒交互](configure-end-user-interaction-microsoft-defender-antivirus.md)
