---
title: 使用组策略配置Microsoft Defender 防病毒
description: 了解如何使用组策略在Microsoft Defender for Endpoint中的终结点上配置和管理Microsoft Defender 防病毒。
keywords: 组策略、GPO、配置、设置
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/04/2022
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: e8cda6f387814ed6ec613db8cb53ff030243a92b
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789400"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>使用组策略设置配置和管理Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

可以使用[组策略](/windows/win32/srvnodes/group-policy)在终结点上配置和管理Microsoft Defender 防病毒。

## <a name="configure-microsoft-defender-antivirus-using-group-policy"></a>使用组策略配置Microsoft Defender 防病毒

通常，可以使用以下过程来配置或更改Microsoft Defender 防病毒组策略设置：

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象 (GPO) ，然后单击 **“编辑**”。

2. 使用 **组策略管理编辑器** 转到 **计算机配置**。

3. 单击 **“管理模板**”。

4. 将树展开为 **Windows组件** \> **Microsoft Defender 防病毒**。

5. 展开本主题中表中称为 **“位置** ”的部分 () 其中包含要配置的设置，双击设置以将其打开，然后进行配置更改。

6. [像平时一样部署更新后的 GPO](/windows/win32/srvnodes/group-policy)。

## <a name="group-policy-settings-and-resources"></a>组策略设置和资源

下表列出了Windows 10中常用的组策略设置。

> [!TIP]
> 下载组策略参考电子表格，其中列出了用于Windows随附的管理模板文件中包含的计算机和用户配置的策略设置。 编辑组策略对象时，可以配置引用电子表格。 <br/><br/> 以下是最新版本：
> - [组策略 设置 2020 年 5 月更新 (2004 年 5 月Windows 10参考电子表格) ](https://www.microsoft.com/download/details.aspx?id=101451)
> - [组策略 设置 2021 年 10 月 Windows 11 日更新 (21H2) 参考电子表格](https://www.microsoft.com/download/details.aspx?id=103506)

<br/><br/>

|位置|设置|文章|
|---|---|---|
|客户端接口|启用无头 UI 模式|[阻止用户查看或与Microsoft Defender 防病毒用户界面交互](prevent-end-user-interaction-microsoft-defender-antivirus.md)|
|客户端接口|当客户端需要执行操作时，向客户端显示其他文本|[配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)|
|客户端接口|取消所有通知|[配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)|
|客户端接口|禁止重新启动通知|[配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)|
|排除项|扩展排除项|[在Microsoft Defender 防病毒扫描中配置和验证排除项](configure-exclusions-microsoft-defender-antivirus.md)|
|排除项|路径排除项|[在Microsoft Defender 防病毒扫描中配置和验证排除项](configure-exclusions-microsoft-defender-antivirus.md)|
|排除项|进程排除项|[在Microsoft Defender 防病毒扫描中配置和验证排除项](configure-exclusions-microsoft-defender-antivirus.md)|
|排除项|关闭自动排除项|[在Microsoft Defender 防病毒扫描中配置和验证排除项](configure-exclusions-microsoft-defender-antivirus.md)|
|地图|配置“一见钟情时阻止”功能|[启用首次看到时阻止](configure-block-at-first-sight-microsoft-defender-antivirus.md)|
|地图|加入 Microsoft MAPS|[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)|
|地图|需要进一步分析时发送文件示例|[启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)|
|地图|配置本地设置替代以向 Microsoft MAPS 报告|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|MpEngine|配置扩展云检查|[配置云块超时时间段](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)|
|MpEngine|选择云保护级别|[指定云传递的保护级别](specify-cloud-protection-level-microsoft-defender-antivirus.md)|
|网络检查系统|为网络流量检查指定其他定义集| 未使用 (已弃用)  |
|网络检查系统|启用定义停用| 未使用 (已弃用) |
|网络检查系统|启用协议识别| 未使用 (已弃用) |
|隔离|配置本地设置替代，以便从隔离文件夹中删除项|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|隔离|配置从隔离文件夹中删除项|[为Microsoft Defender 防病毒扫描配置修正](configure-remediation-microsoft-defender-antivirus.md)|
|实时保护|配置本地设置替代以监视计算机上的文件和程序活动|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|实时保护|配置本地设置替代以监视传入和传出文件活动|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|实时保护|配置本地设置替代以扫描所有下载的文件和附件|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|实时保护|配置本地设置替代以启用行为监视|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|实时保护|配置本地设置替代以启用实时保护|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|实时保护|定义要扫描的下载文件和附件的最大大小|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|监视计算机上的文件和程序活动|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|扫描所有下载的文件和附件|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|关闭实时保护|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|启用行为监视|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|启用实时保护时启用进程扫描|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|打开原始卷写入通知|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|实时保护|为传入和传出文件和程序活动配置监视|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|修复|为一天中的时间配置本地设置重写以运行计划的完整扫描以完成修正|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|修复|指定运行计划的完整扫描以完成修正的星期几|[配置计划的Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|修复|指定运行计划的完整扫描以完成修正的一天中的时间|[配置计划的Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|报表|关闭增强的通知|[配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)
|根|关闭Microsoft Defender 防病毒|未使用。 如果使用或计划使用非 Microsoft 防病毒产品，请参阅[Microsoft Defender 防病毒与其他安全产品的兼容性](microsoft-defender-antivirus-compatibility.md)。|
|根|定义要绕过代理服务器的地址|[配置设备代理和 Internet 连接设置](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|根|定义用于连接到网络的代理 autoconfig (.pac) |[配置设备代理和 Internet 连接设置](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|根|定义用于连接到网络的代理服务器|[配置设备代理和 Internet 连接设置](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|根|为列表配置本地管理员合并行为|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|根|允许反恶意软件服务以正常优先级启动|[为Microsoft Defender 防病毒扫描配置修正](configure-remediation-microsoft-defender-antivirus.md)|
|根|允许反恶意软件服务始终保持运行|[为Microsoft Defender 防病毒扫描配置修正](configure-remediation-microsoft-defender-antivirus.md)|
|根|关闭常规修正|[为Microsoft Defender 防病毒扫描配置修正](configure-remediation-microsoft-defender-antivirus.md)|
|根|随机化计划的任务时间|[为Microsoft Defender 防病毒配置计划的扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|扫描|允许用户暂停扫描|[阻止用户查看或与Microsoft Defender 防病毒用户界面](prevent-end-user-interaction-microsoft-defender-antivirus.md)交互 (Windows 10) |
|扫描|在运行计划扫描之前检查最新的病毒和间谍软件定义|[管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)|
|扫描|定义强制执行追赶扫描后的天数|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|扫描|打开“赶上完全扫描”|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|扫描|打开“快速扫描”|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|扫描|为 CPU 利用率的最大百分比配置本地设置替代|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|扫描|为计划扫描日配置本地设置替代|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|扫描|为计划的快速扫描时间配置本地设置替代|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|扫描|为计划的扫描时间配置本地设置替代|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|扫描|配置要用于计划扫描的扫描类型的本地设置替代|[阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|扫描|创建系统还原点|[为Microsoft Defender 防病毒扫描配置修正](configure-remediation-microsoft-defender-antivirus.md)|
|扫描|打开从扫描历史记录文件夹中删除项|[为Microsoft Defender 防病毒扫描配置修正](configure-remediation-microsoft-defender-antivirus.md)|
|扫描|启用启发式|[启用和配置Microsoft Defender 防病毒始终可用的保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md)|
|扫描|启用电子邮件扫描|[在Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|启用重新分析点扫描|[在Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|在映射的网络驱动器上运行完全扫描|[在Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|扫描存档文件|[在Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|扫描网络文件|[在Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|扫描打包的可执行文件|[在Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
| 扫描 | 扫描脚本 | [在Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) <p>另请参阅 [Defender/AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender)。|
|扫描|扫描可移动驱动器|[在Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|指定扫描存档文件的最大深度|[在Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|指定扫描期间 CPU 利用率的最大百分比|[在Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|指定要扫描的存档文件的最大大小|[在Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|扫描|指定运行计划扫描的星期几|[为Microsoft Defender 防病毒配置计划的扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|扫描|指定每天运行快速扫描的间隔|[为Microsoft Defender 防病毒配置计划的扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|扫描|指定用于计划扫描的扫描类型|[为Microsoft Defender 防病毒配置计划的扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|扫描|指定每日快速扫描的时间|[为Microsoft Defender 防病毒配置计划的扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|扫描|指定运行计划扫描的一天中的时间|[为Microsoft Defender 防病毒配置计划的扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|扫描|仅当计算机处于打开状态但未使用时才启动计划扫描|[为Microsoft Defender 防病毒配置计划的扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|安全智能更新|允许从 Microsoft 更新进行安全智能更新|[管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)|
|安全智能更新|在电池电源上运行时允许安全智能更新|[管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)|
|安全智能更新|允许通知将基于定义的报告禁用到 Microsoft MAPS|[管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)|
|安全智能更新|允许基于 Microsoft MAPS 报告的实时安全智能更新|[管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)|
|安全智能更新|检查启动时的最新病毒和间谍软件定义|[管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)|
|安全智能更新|定义用于下载安全智能更新的文件共享|[管理Microsoft Defender 防病毒保护和安全智能更新](manage-protection-updates-microsoft-defender-antivirus.md)|
|安全智能更新|定义需要赶上安全智能更新的天数|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|安全智能更新|定义将间谍软件定义视为过期之前的天数|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|安全智能更新|定义将病毒定义视为过期之前的天数|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|安全智能更新|定义用于下载安全智能更新的源的顺序|[管理Microsoft Defender 防病毒保护和安全智能更新](manage-protection-updates-microsoft-defender-antivirus.md)|
|安全智能更新|启动时启动安全智能更新|[管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md)|
|安全智能更新|指定要检查安全情报更新的一周中的日期|[管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|安全智能更新|指定用于检查安全智能更新的时间间隔|[管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|安全智能更新|指定检查安全智能更新的时间|[管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|安全智能更新|安全智能更新后启用扫描|[为Microsoft Defender 防病毒配置计划的扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|威胁|指定检测到时不应执行默认操作的威胁警报级别|[为Microsoft Defender 防病毒扫描配置修正](configure-remediation-microsoft-defender-antivirus.md)|
|威胁|指定检测到时不应对其执行默认操作的威胁|[为Microsoft Defender 防病毒扫描配置修正](configure-remediation-microsoft-defender-antivirus.md)|

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="see-also"></a>另请参阅

- [有关管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
