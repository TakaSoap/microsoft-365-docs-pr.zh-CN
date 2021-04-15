---
title: 使用组策略配置 Microsoft Defender 防病毒
description: 了解如何使用组策略在适用于终结点的 Microsoft Defender 终结点上配置和管理 Microsoft Defender 防病毒。
keywords: 组策略， GPO， 配置， 设置
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 04/13/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: e8d3cbd58b80d6c393b8d7173c61509b26a29b4a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765655"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>使用组策略设置配置和管理 Microsoft Defender 防病毒

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以使用组 [策略](/windows/win32/srvnodes/group-policy) 在终结点上配置和管理 Microsoft Defender 防病毒。

通常，可以使用以下过程配置或更改 Microsoft Defender 防病毒组策略设置：

1. 在组策略管理计算机上，打开组策略 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))管理控制台，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**

2. 使用组 **策略管理编辑器转到** 计算机 **配置**。

3. 单击 **"管理模板"。**

4. 将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**。

5. 展开本主题 (表中称为"位置"的部分) 其中包含要配置的设置，双击该设置将其打开，然后进行配置更改。

6. [像平常一样部署更新的 GPO。](/windows/win32/srvnodes/group-policy) 

本主题中的下表列出了 Windows 10 版本 1703 中提供的组策略设置，并提供指向本文档库中相应主题的链接 (适用) 。

| 位置 | 设置 | 文章 |
|:---|:---|:---|
| 客户端接口 | 启用无头 UI 模式 | [阻止用户查看 Microsoft Defender 防病毒用户界面或与之交互](prevent-end-user-interaction-microsoft-defender-antivirus.md) |
| 客户端接口 | 当客户端需要执行一个操作时，向客户端显示其他文本 | [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md) |
| 客户端接口 | 禁止显示所有通知 | [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md) |
| 客户端接口 | 禁止重新启动通知 | [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md) |
| 排除项 | 扩展排除项 | [配置并验证 Microsoft Defender 防病毒扫描中的排除项](configure-exclusions-microsoft-defender-antivirus.md) |
| 排除项 | 路径排除项 | [配置并验证 Microsoft Defender 防病毒扫描中的排除项](configure-exclusions-microsoft-defender-antivirus.md) |
| 排除项 | 进程排除项 | [配置并验证 Microsoft Defender 防病毒扫描中的排除项](configure-exclusions-microsoft-defender-antivirus.md) | 
| 排除项 | 关闭自动排除项 | [配置并验证 Microsoft Defender 防病毒扫描中的排除项](configure-exclusions-microsoft-defender-antivirus.md) |
| MAPS | 配置"首次看到时阻止"功能 | [启用"首次看到时阻止"](configure-block-at-first-sight-microsoft-defender-antivirus.md) |
| MAPS | 加入 Microsoft MAPS | [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPS | 需要进一步分析时发送文件示例 | [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md) |
| MAPS | 配置向 Microsoft MAPS 报告的本地设置替代 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| MpEngine | 配置扩展云检查 | [配置云块超时时间段](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) |
| MpEngine | 选择云保护级别 | [指定云传递的保护级别](specify-cloud-protection-level-microsoft-defender-antivirus.md) |
| 网络检查系统 | 为网络流量检查指定其他定义集 | 不再相关 |
| 网络检查系统 | 启用定义停用 | 不再相关 |
| 网络检查系统 | 打开协议识别 | 不再相关 |
| 隔离 | 为从隔离文件夹中删除项目配置本地设置替代 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 隔离 | 配置从隔离文件夹删除项目 | [配置 Microsoft Defender 防病毒扫描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 实时保护 | 配置本地设置覆盖以监视您的计算机上的文件和程序活动 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 实时保护 | 配置本地设置覆盖以监视传入和传出文件活动 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 实时保护 | 配置用于扫描所有下载的文件和附件的本地设置替代 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 实时保护 | 配置本地设置替代以启用行为监视 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 实时保护 | 配置本地设置覆盖以启用实时保护 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 实时保护 | 定义要扫描的已下载文件和附件的最大大小 | [启用和配置 Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 实时保护 | 监视您的计算机上的文件和程序活动 | [启用和配置 Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 实时保护 | 扫描所有下载的文件和附件 | [启用和配置 Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 实时保护 | 关闭实时保护 | [启用和配置 Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 实时保护 | 打开行为监视 | [启用和配置 Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 实时保护 | 启用实时保护时打开进程扫描 | [启用和配置 Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 实时保护 | 打开原始卷写入通知 | [启用和配置 Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 实时保护 | 配置对传入和传出文件和程序活动的监视 | [启用和配置 Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 修正 | 为运行计划的完整扫描以完成修正的时间配置本地设置替代 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 修正 | 指定一周中的哪些天运行计划的完全扫描以完成修正 | [配置计划的 Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 修正 | 指定一天中运行计划完整扫描以完成修正的时间 | [配置计划的 Microsoft Defender 防病毒扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 报告 | 关闭增强型通知 | [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)
| 根 | 关闭 Microsoft Defender 防病毒 | 未 (此设置必须设置为"未配置"，以确保任何已安装的第三方防病毒应用) 
| 根 | 定义绕过代理服务器的地址 | 未使用 |
| 根 | 定义代理自动 (.pac) 以连接到网络 | 未使用 |
| 根 | 定义用于连接到网络的代理服务器 | 未使用 |
| 根 | 配置列表的本地管理员合并行为 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 根 | 允许反恶意软件服务以正常优先级启动 | [配置 Microsoft Defender 防病毒扫描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 根 | 允许反恶意软件服务始终运行 | [配置 Microsoft Defender 防病毒扫描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 根 | 关闭常规修正 | [配置 Microsoft Defender 防病毒扫描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 根 | 随机化计划任务时间 | [配置 Microsoft Defender 防病毒的计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 扫描 | 允许用户暂停扫描 | [阻止用户查看或与 Windows](prevent-end-user-interaction-microsoft-defender-antivirus.md) 10 (不支持的 Microsoft Defender 防病毒用户界面)  |
| 扫描 | 在运行计划扫描之前检查最新的病毒和间谍软件定义 | [管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 扫描 | 定义强制进行跟进扫描的天数 | [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 扫描 | 打开"捕获完整扫描" | [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 扫描 | 打开"捕获快速扫描" | [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 扫描 | 为 CPU 使用率的最大百分比配置本地设置覆盖 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 扫描 | 为计划扫描日配置本地设置覆盖 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 扫描 | 为计划的快速扫描时间配置本地设置覆盖 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 扫描 | 为计划扫描时间配置本地设置覆盖 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 扫描 | 为要用于计划扫描的扫描类型配置本地设置覆盖 | [阻止或允许用户在本地修改策略设置](configure-local-policy-overrides-microsoft-defender-antivirus.md) |
| 扫描 | 创建系统还原点 | [配置 Microsoft Defender 防病毒扫描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 扫描 | 打开从扫描历史记录文件夹中删除项目 | [配置 Microsoft Defender 防病毒扫描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 扫描 | 打开启发式 | [启用和配置 Microsoft Defender 防病毒始终启用保护和监视](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 扫描 | 打开电子邮件扫描 | [在 Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 扫描 | 打开重新分析点扫描 | [在 Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 扫描 | 在映射的网络驱动器上运行完全扫描 | [在 Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 扫描 | 扫描存档文件 | [在 Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 扫描 | 扫描网络文件 | [在 Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 扫描 | 扫描打包的可执行文件 | [在 Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 扫描 | 扫描可移动驱动器 | [在 Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 扫描 | 指定扫描存档文件的最大深度 | [在 Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 扫描 | 指定扫描期间 CPU 使用率的最大百分比 | [在 Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 扫描 | 指定要扫描的存档文件的最大大小 | [在 Microsoft Defender 防病毒中配置扫描选项](configure-advanced-scan-types-microsoft-defender-antivirus.md) |
| 扫描 | 指定一周中的哪些天运行计划扫描 | [配置 Microsoft Defender 防病毒的计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 扫描 | 指定每天运行快速扫描的间隔 | [配置 Microsoft Defender 防病毒的计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 扫描 | 指定用于计划扫描的扫描类型 | [配置 Microsoft Defender 防病毒的计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 扫描 | 指定每日快速扫描的时间 | [配置 Microsoft Defender 防病毒的计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 扫描 | 指定运行计划扫描的时间 | [配置 Microsoft Defender 防病毒的计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 扫描 | 仅在计算机打开但没有使用时启动计划扫描 | [配置 Microsoft Defender 防病毒的计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 安全智能更新 | 允许 Microsoft 更新中的安全智能更新 | [管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| 安全智能更新 | 使用电池电源运行时允许安全智能更新 | [管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md) |
| 安全智能更新 | 允许通知禁用向 Microsoft MAPS 发送的基于定义的报告 | [管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 安全智能更新 | 允许基于 Microsoft MAPS 报告进行实时安全智能更新 | [管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 安全智能更新 | 启动时检查最新的病毒和间谍软件定义 | [管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 安全智能更新 | 定义用于下载安全智能更新的文件共享 | [管理 Microsoft Defender 防病毒保护和安全智能更新](manage-protection-updates-microsoft-defender-antivirus.md) |
| 安全智能更新 | 定义需要更新安全智能的天数 | [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 安全智能更新 | 定义间谍软件定义被视为过期前的天数 | [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 安全智能更新 | 定义病毒定义被视为过期前的天数 | [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) |
| 安全智能更新 | 定义用于下载安全智能更新的源的顺序 | [管理 Microsoft Defender 防病毒保护和安全智能更新](manage-protection-updates-microsoft-defender-antivirus.md) |
| 安全智能更新 | 启动时启动安全智能更新 | [管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md) |
| 安全智能更新 | 指定一周中的哪些天检查安全智能更新 | [管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| 安全智能更新 | 指定检查安全智能更新的间隔 | [管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| 安全智能更新 | 指定检查安全智能更新的时间 | [管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md) |
| 安全智能更新 | 在安全智能更新后打开扫描 | [配置 Microsoft Defender 防病毒的计划扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| 威胁 | 指定检测到威胁警报时不应采取默认操作的威胁警报级别 | [配置 Microsoft Defender 防病毒扫描的修正](configure-remediation-microsoft-defender-antivirus.md) |
| 威胁 | 指定检测到时不应采取默认操作的威胁 | [配置 Microsoft Defender 防病毒扫描的修正](configure-remediation-microsoft-defender-antivirus.md) |


## <a name="related-articles"></a>相关文章

- [有关管理和配置工具的参考主题](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
