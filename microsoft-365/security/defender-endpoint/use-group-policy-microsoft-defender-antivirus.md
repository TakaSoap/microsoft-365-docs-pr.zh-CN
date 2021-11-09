---
title: 使用Microsoft Defender 防病毒配置策略
description: 了解如何使用组策略在 Microsoft Defender for Endpoint Microsoft Defender 防病毒终结点上配置和管理用户。
keywords: 组策略， GPO， 配置， 设置
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: a8eb8db33a79ccb7d4cc9cd010a689e524746fad
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60883673"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>使用组策略设置配置和管理Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以使用组[策略](/windows/win32/srvnodes/group-policy)在终结点上配置Microsoft Defender 防病毒管理策略。

## <a name="configure-microsoft-defender-antivirus-using-group-policy"></a>使用Microsoft Defender 防病毒配置策略

通常，可以使用以下过程配置或更改Microsoft Defender 防病毒策略设置：

1. 在组策略管理计算机上，打开组策略 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))管理控制台，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**

2. 使用组 **策略管理编辑器转到** 计算机 **配置**。

3. 单击 **"管理模板"。**

4. 展开树以Windows **组件** \> **Microsoft Defender 防病毒。**

5. 展开本主题 (中称为"位置"的部分) 其中包含要配置的设置，双击该设置将其打开，然后进行配置更改。

6. [像平常一样部署更新的 GPO。](/windows/win32/srvnodes/group-policy)

## <a name="group-policy-settings-and-resources"></a>组策略设置和资源

本主题中的下表列出了 Windows 10 版本 1703 中提供的组策略设置，并提供指向本文档库中相应主题的链接 (（如果适用) ）。

> [!TIP]
> [下载组策略设置 Reference Spreadsheet for Windows 10 May 2020 Update (2004) 。 ](https://www.microsoft.com/download/101451) 此电子表格列出了 2004 年 5 月更新 Windows 10 2004 年 5 月 (中包含的管理模板文件中包含的计算机和用户配置) 。 可以在编辑组策略对象时配置对电子表格的参考。<br/><br/>

<br>

****

|位置|Setting|文章|
|---|---|---|
|客户端接口|启用无头 UI 模式|[阻止用户查看或与用户界面Microsoft Defender 防病毒交互](prevent-end-user-interaction-microsoft-defender-antivirus.md)|
|客户端接口|当客户端需要执行一个操作时，向客户端显示其他文本|[配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)|
|客户端接口|禁止显示所有通知|[配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)|
|客户端接口|禁止重新启动通知|[配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)|
|排除|扩展排除项|[配置并验证扫描中的Microsoft Defender 防病毒项](configure-exclusions-microsoft-defender-antivirus.md)|
|排除|路径排除项|[配置并验证扫描中的Microsoft Defender 防病毒项](configure-exclusions-microsoft-defender-antivirus.md)|
|排除|进程排除项|[配置并验证扫描中的Microsoft Defender 防病毒项](configure-exclusions-microsoft-defender-antivirus.md)|
|排除|关闭自动排除项|[配置并验证扫描中的Microsoft Defender 防病毒项](configure-exclusions-microsoft-defender-antivirus.md)|
|MAPS|配置"首次看到时阻止"功能|[启用"首次看到时阻止"](configure-block-at-first-sight-microsoft-defender-antivirus.md)|
|MAPS|加入 Microsoft MAPS|[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)|
|MAPS|需要进一步分析时发送文件示例|[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)|
|MAPS|配置向 Microsoft MAPS 报告的本地设置替代|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|MpEngine|配置扩展云检查|[配置云块超时时间段](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)|
|MpEngine|选择云保护级别|[指定云传递的保护级别](specify-cloud-protection-level-microsoft-defender-antivirus.md)|
|网络检查系统|为网络流量检查指定其他定义集|[为网络流量检查指定其他定义集](specify-additional-definitions-network-traffic-inspection-mdav.md)|
|网络检查系统|启用定义停用|[配置定义停用](turn-on-definition-retirement.md)|
|网络检查系统|打开协议识别|[打开协议识别](turn-on-protocol-recognition.md)|
|Quarantine|为从隔离文件夹中删除项目配置本地设置替代|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|Quarantine|配置从隔离文件夹删除项目|[配置扫描Microsoft Defender 防病毒修正](configure-remediation-microsoft-defender-antivirus.md)|
|实时保护|配置本地设置覆盖以监视您的计算机上的文件和程序活动|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|实时保护|配置本地设置覆盖以监视传入和传出文件活动|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|实时保护|配置用于扫描所有下载的文件和附件的本地设置替代|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|实时保护|配置本地设置替代以启用行为监视|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|实时保护|配置本地设置覆盖以启用实时保护|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|实时保护|定义要扫描的已下载文件和附件的最大大小|[启用和配置Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|监视您的计算机上的文件和程序活动|[启用和配置Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|扫描所有下载的文件和附件|[启用和配置Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|关闭实时保护|[启用和配置Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|打开行为监视|[启用和配置Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|启用实时保护时打开进程扫描|[启用和配置Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|打开原始卷写入通知|[启用和配置Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|配置对传入和传出文件和程序活动的监视|[启用和配置Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|修正|为运行计划的完整扫描以完成修正的时间配置本地设置替代|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|修正|指定一周中的哪些天运行计划的完全扫描以完成修正|[配置计划Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|修正|指定一天中运行计划完整扫描以完成修正的时间|[配置计划Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Reporting|关闭增强型通知|[配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)
|根|关闭Microsoft Defender 防病毒|未 (此设置必须设置为"未配置"，以确保任何已安装的第三方防病毒应用) 
|根|定义绕过代理服务器的地址|[配置设备代理和 Internet 连接设置](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|根|定义代理自动配置 (.pac) 以连接到网络|[配置设备代理和 Internet 连接设置](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|根|定义用于连接到网络的代理服务器|[配置设备代理和 Internet 连接设置](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|根|配置列表的本地管理员合并行为|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|根|允许反恶意软件服务以正常优先级启动|[配置扫描Microsoft Defender 防病毒修正](configure-remediation-microsoft-defender-antivirus.md)|
|根|允许反恶意软件服务始终运行|[配置扫描Microsoft Defender 防病毒修正](configure-remediation-microsoft-defender-antivirus.md)|
|根|关闭常规修正|[配置扫描Microsoft Defender 防病毒修正](configure-remediation-microsoft-defender-antivirus.md)|
|根|随机化计划任务时间|[配置计划扫描以用于Microsoft Defender 防病毒](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|扫描|允许用户暂停扫描|[阻止用户查看](prevent-end-user-interaction-microsoft-defender-antivirus.md)或与 Microsoft Defender 防病毒 用户界面 (不支持Windows 10) |
|扫描|在运行计划扫描之前检查最新的病毒和间谍软件定义|[管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)|
|扫描|定义强制进行跟进扫描的天数|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|扫描|打开"捕获完整扫描"|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|扫描|打开"捕获快速扫描"|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|扫描|为 CPU 使用率的最大百分比配置本地设置覆盖|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|扫描|为计划扫描日配置本地设置覆盖|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|扫描|为计划的快速扫描时间配置本地设置覆盖|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|扫描|为计划扫描时间配置本地设置覆盖|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|扫描|为要用于计划扫描的扫描类型配置本地设置覆盖|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|扫描|创建系统还原点|[配置扫描Microsoft Defender 防病毒修正](configure-remediation-microsoft-defender-antivirus.md)|
|扫描|打开从扫描历史记录文件夹中删除项目|[配置扫描Microsoft Defender 防病毒修正](configure-remediation-microsoft-defender-antivirus.md)|
|扫描|打开启发式|[启用和配置Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|扫描|打开电子邮件扫描|[配置扫描选项Microsoft Defender 防病毒](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|打开重新分析点扫描|[配置扫描选项Microsoft Defender 防病毒](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|在映射的网络驱动器上运行完全扫描|[配置扫描选项Microsoft Defender 防病毒](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|扫描存档文件|[配置扫描选项Microsoft Defender 防病毒](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|扫描网络文件|[配置扫描选项Microsoft Defender 防病毒](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|扫描打包的可执行文件|[配置扫描选项Microsoft Defender 防病毒](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|扫描可移动驱动器|[配置扫描选项Microsoft Defender 防病毒](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|指定扫描存档文件的最大深度|[配置扫描选项Microsoft Defender 防病毒](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|指定扫描期间 CPU 使用率的最大百分比|[配置扫描选项Microsoft Defender 防病毒](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|指定要扫描的存档文件的最大大小|[配置扫描选项Microsoft Defender 防病毒](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|指定一周中的哪些天运行计划扫描|[配置计划扫描以用于Microsoft Defender 防病毒](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|扫描|指定每天运行快速扫描的间隔|[配置计划扫描以用于Microsoft Defender 防病毒](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|扫描|指定用于计划扫描的扫描类型|[配置计划扫描以用于Microsoft Defender 防病毒](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|扫描|指定每日快速扫描的时间|[配置计划扫描以用于Microsoft Defender 防病毒](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|扫描|指定运行计划扫描的时间|[配置计划扫描以用于Microsoft Defender 防病毒](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|扫描|仅在计算机打开但没有使用时启动计划扫描|[配置计划扫描以用于Microsoft Defender 防病毒](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|安全智能更新|允许 Microsoft 更新中的安全智能更新|[管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)|
|安全智能更新|使用电池电源运行时允许安全智能更新|[管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)|
|安全智能更新|允许通知禁用向 Microsoft MAPS 发送的基于定义的报告|[管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)|
|安全智能更新|允许基于 Microsoft MAPS 报告进行实时安全智能更新|[管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)|
|安全智能更新|启动时检查最新的病毒和间谍软件定义|[管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)|
|安全智能更新|定义用于下载安全智能更新的文件共享|[管理Microsoft Defender 防病毒安全和安全智能更新](manage-protection-updates-microsoft-defender-antivirus.md)|
|安全智能更新|定义需要更新安全智能的天数|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|安全智能更新|定义间谍软件定义被视为过期前的天数|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|安全智能更新|定义病毒定义被视为过期前的天数|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|安全智能更新|定义用于下载安全智能更新的源的顺序|[管理Microsoft Defender 防病毒安全和安全智能更新](manage-protection-updates-microsoft-defender-antivirus.md)|
|安全智能更新|启动时启动安全智能更新|[管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)|
|安全智能更新|指定一周中的哪些天检查安全智能更新|[管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|安全智能更新|指定检查安全智能更新的间隔|[管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|安全智能更新|指定检查安全智能更新的时间|[管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|安全智能更新|在安全智能更新后打开扫描|[配置计划扫描以用于Microsoft Defender 防病毒](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|威胁|指定检测到威胁警报时不应采取默认操作的威胁警报级别|[配置扫描Microsoft Defender 防病毒修正](configure-remediation-microsoft-defender-antivirus.md)|
|威胁|指定检测到时不应采取默认操作的威胁|[配置扫描Microsoft Defender 防病毒修正](configure-remediation-microsoft-defender-antivirus.md)|
|

## <a name="see-also"></a>另请参阅

- [有关管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
