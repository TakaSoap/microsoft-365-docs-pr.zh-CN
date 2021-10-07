---
title: 为 Microsoft Defender 防病毒检测配置修正
description: 配置Microsoft Defender 防病毒威胁时应执行哪些操作，以及隔离文件应在隔离文件夹中保留多久
keywords: 修正， 修复， 删除， 威胁， 隔离， 扫描， 还原
search.product: eADQiWindows 10XVcnh
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
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 3392653aab996ef62f05664a33c82f55639003c4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196959"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>为 Microsoft Defender 防病毒检测配置修正


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

当Microsoft Defender 防病毒扫描时，它会尝试修正或删除检测到的威胁。 你可以配置Microsoft Defender 防病毒应对特定威胁、是否应在修正前创建还原点以及何时应删除威胁。

本文介绍如何使用组策略配置这些设置，但您也可以使用 Microsoft Endpoint Configuration Manager[和](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings)[Microsoft Intune](/intune/device-restrictions-configure)。

您还可以使用[ `Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference)或[ `MSFT_MpPreference` WMI 类](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)配置这些设置。

## <a name="configure-remediation-options"></a>配置修正选项

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

2. 在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后选择 **管理模板**。

3. 展开树以Windows **组件** \> **Microsoft Defender 防病毒。**

4. 使用下表选择一个位置，然后根据需要编辑策略。

5. 选择“**确定**”。

<br/><br/>

|位置|设置|说明|如果未配置 (默认设置) |
|---|---|---|---|
|扫描|创建系统还原点|在尝试清理或扫描之前，将每天创建一个系统还原点|Disabled|
|扫描|打开从扫描历史记录文件夹中删除项目|指定项目应在扫描历史记录中保留的天数|30 天|
|根|关闭常规修正|你可以指定是Microsoft Defender 防病毒自动修正威胁，还是应询问终结点用户应该怎么办。|禁用 (自动修正威胁) |
|隔离|配置从隔离文件夹删除项目|指定在删除项目之前应在隔离中保留的天数|90 天|
|威胁|指定检测到威胁警报时不应采取默认操作的威胁警报级别|系统为每个检测到的威胁Microsoft Defender 防病毒一个威胁级别 (低、中等、高或严重级别) 。 可以使用此设置定义在隔离、删除或忽略每个威胁级别 (、删除或忽略威胁) |不适用|
|威胁|指定检测到时不应采取默认操作的威胁|指定应该如何 (威胁 ID 来) 特定威胁。 你可以指定是应隔离、删除还是忽略特定威胁|不适用|

> [!IMPORTANT]
> Microsoft Defender 防病毒基于许多因素检测并修正文件。 有时，完成修正需要重新启动。 即使检测稍后被确定为误报，也必须完成重新启动以确保所有其他修正步骤已完成。
>
> 如果确定已Microsoft Defender 防病毒误报隔离文件，可以在设备重启后从隔离中还原文件。 请参阅[在中还原隔离Microsoft Defender 防病毒。](restore-quarantined-files-microsoft-defender-antivirus.md)
>
> 若要在将来避免此问题，可以从扫描中排除文件。 请参阅[配置并验证扫描Microsoft Defender 防病毒排除项](configure-exclusions-microsoft-defender-antivirus.md)。

另请参阅[配置修正所需的计划完整Microsoft Defender 防病毒扫描，](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed)了解与修正相关的更多设置。

## <a name="see-also"></a>另请参阅

- [配置 Microsoft Defender 防病毒软件扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [配置计划Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [配置并运行按需 Microsoft Defender 防病毒软件扫描](run-scan-microsoft-defender-antivirus.md)
- [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)
- [配置最终用户Microsoft Defender 防病毒交互](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [自定义、启动和查看Microsoft Defender 防病毒扫描和修正的结果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
