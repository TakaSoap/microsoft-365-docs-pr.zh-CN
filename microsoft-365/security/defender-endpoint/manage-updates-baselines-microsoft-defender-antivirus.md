---
title: 管理Microsoft Defender 防病毒更新并应用基线
description: 管理Microsoft Defender 防病毒保护和产品更新。
keywords: 更新， 安全基线， 保护， 计划更新， 强制更新， 移动更新， wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 10/04/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 881711359313bb0b22870ce15bbbc7ff2d91d1b5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205303"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>管理Microsoft Defender 防病毒更新并应用基线

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 防病毒

保持Microsoft Defender 防病毒保持最新状态至关重要，可确保你的设备具有抵御新的恶意软件和攻击技术所需的最新技术和功能。 确保更新防病毒保护，即使Microsoft Defender 防病毒处于被动[模式。](microsoft-defender-antivirus-compatibility.md) 有两种类型的更新与使Microsoft Defender 防病毒保持最新有关：

- 安全智能更新
- 产品更新

> [!TIP]
> To see the most current engine， platform， and signature date， visit the [Security intelligence updates for Microsoft Defender 防病毒 other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)

## <a name="security-intelligence-updates"></a>安全智能更新

Microsoft Defender 防病毒云[提供的](cloud-protection-microsoft-defender-antivirus.md)保护 (也称为 Microsoft 高级保护服务或 MAPS) 并定期下载安全智能更新以提供保护。

> [!NOTE]
> 更新以以下 KB 编号发布：
>
> - Microsoft Defender 防病毒：KB2267602
> - System Center Endpoint Protection：KB2461484

云提供的保护始终打开，并且需要与 Internet 的活动连接以正常运行。 安全智能更新按计划节奏进行， (策略策略配置) 。 有关详细信息，请参阅在 Microsoft[云中Microsoft Defender 防病毒。](cloud-protection-microsoft-defender-antivirus.md)

有关最近安全智能更新的列表，请参阅安全智能更新[Microsoft Defender 防病毒和其他 Microsoft 反恶意软件](https://www.microsoft.com/en-us/wdsi/defenderupdates)。

引擎更新包含在安全智能更新中，并按月发布。

## <a name="product-updates"></a>产品更新

Microsoft Defender 防病毒需要 [每月更新 (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)称为 *平台更新*。

可以通过以下方法之一管理更新的分发：

- [WindowsWSUS (服务器更新) ](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- 你用于部署 Microsoft 和将Windows更新到网络中终结点的常用方法。

有关详细信息，请参阅管理保护Microsoft Defender 防病毒[源](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。

> [!NOTE]
>
> - 每月更新会分期发布，从而在 Window Server Update Services 中显示 [多个程序包](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。
> - 本文列出了广泛发布频道中包含的更改。 [在此处查看最新的广泛频道版本](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info)。
> - 若要了解有关逐步推出过程以及有关下一版本详细信息，请参阅管理 Microsoft Defender 更新 [的逐步推出过程](manage-gradual-rollout.md)。
> - 若要了解有关安全智能更新的信息，请参阅安全智能更新[Microsoft Defender 防病毒和其他 Microsoft 反恶意软件](https://www.microsoft.com/wdsi/defenderupdates)。

## <a name="monthly-platform-and-engine-versions"></a>每月平台和引擎版本

若要了解如何更新或安装平台更新，请参阅反恶意软件Windows Defender[更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。

我们的所有更新都包含

- 性能改进;
- 可服务性改进;和
- 云 (集成[改进](/microsoft-365/security/defender/microsoft-365-defender)Microsoft 365 Defender) 。
<br/>
<details>
<summary> 2021 年 8 月 (平台：4.18.2108.7 |引擎：1.1.18500.10) </summary>

&ensp;安全智能更新版本 **：1.349.22.0**<br/>
&ensp;已发布 **：2021 年 9 月 2 日**<br/>
&ensp;平台 **：4.18.2108.7**<br/>
&ensp;引擎 **：1.1.18500.10**<br/>
&ensp;支持阶段： **安全和关键更新**<br/>

### <a name="whats-new"></a>新增功能
- 对行为监视引擎的改进
- 发布了新的[性能分析器Microsoft Defender 防病毒](tune-performance-defender-antivirus.md)
- Microsoft Defender 防病毒加载恶意 DLL 进行了强化
- Microsoft Defender 防病毒 TrustedInstaller 旁路进行强化
- 添加了对配置每规则攻击面减少 [规则排除项的支持](customize-attack-surface-reduction.md)
- 扩展文件更改通知以包含有关使用 Human-Operated 勒索软件 (HumOR) 

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 7 月 (平台：4.18.2107.4 |引擎：1.1.18400.4) </summary>

&ensp;安全智能更新版本 **：1.345.13.0**<br/>
&ensp;发布时间 **：2021 年 8 月 5 日**<br/>
&ensp;平台 **：4.18.2107.4**<br/>
&ensp;引擎 **：1.1.18400.4**<br/>
&ensp;支持阶段： **安全和关键更新**<br/>

### <a name="whats-new"></a>新增功能
- 为可移植设备Windows设备控制支持
- 默认情况下， (PUA) 保护中可能不需要的应用程序为使用者打开 (看到默认情况下，可能会不需要的应用将被阻止) [](https://support.microsoft.com/windows/potentially-unwanted-apps-will-be-blocked-by-default-b9f53cb9-7f1e-40bb-8c6b-a17e0ab6289e)
- 组策略对象托管系统的计划扫描将遵循用户配置的扫描时间
- 对行为监视引擎的改进

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 6 月 (平台：4.18.2106.5 |引擎：1.1.18300.4) </summary>

&ensp;安全智能更新版本 **：1.343.17.0**<br/>
&ensp;发布时间 **：2021 年 6 月 28 日**<br/>
&ensp;平台 **：4.18.2106.5**<br/>
&ensp;引擎 **：1.1.18300.4**<br/>
&ensp;支持阶段： **安全和关键更新**<br/>

### <a name="whats-new"></a>新增功能
- 用于管理 Microsoft Defender 更新的逐步推出过程的新控件。 请参阅 [管理 Microsoft Defender 更新的逐步推出过程](manage-gradual-rollout.md)。
- 对行为监视引擎的改进
- 反恶意软件定义的推出改进
- 扩展的边缘网络事件检查

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>旧版本更新：仅技术升级支持

发布新程序包版本后，仅对前两个版本的支持减少到技术支持。 低于本部分中列出的版本，并且仅提供用于技术升级支持的版本。
<details>
<summary> 2021 年 5 月 (平台：4.18.2105.4 |引擎：1.1.18200.4) </summary>

&ensp;安全智能更新版本 **：1.341.8.0**<br/>
&ensp;发布时间 **：2021 年 6 月 3 日**<br/>
&ensp;平台 **：4.18.2105.4**<br/>
&ensp;引擎 **：1.1.18200.4**<br/>
&ensp;支持阶段 **：仅支持 (升级)**<br/>

### <a name="whats-new"></a>新增功能
- 对行为 [监视的改进](client-behavioral-blocking.md)
- 修复 [了网络保护](network-protection.md) 通知筛选功能

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 4 月 (平台：4.18.2104.14 |引擎：1.1.18100.5) </summary>

&ensp;安全智能更新版本 **：1.337.2.0**<br/>
&ensp;发布时间 **：2021**  年 4 月 26 (引擎：2021 年 5 月 5 日发布 1.1.18100.6) <br/>
&ensp;平台 **：4.18.2104.14**<br/>
&ensp;引擎 **：1.1.18100.5**<br/>
&ensp;支持阶段 **：仅支持 (升级)**<br/>

### <a name="whats-new"></a>新增功能
- 更多行为监视逻辑
- 改进了内核模式密钥记录器检测
- 添加了新控件来管理 Microsoft Defender 更新的逐步 [推出过程](manage-gradual-rollout.md)


### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 3 月 (平台：4.18.2103.7 |引擎：1.1.18000.5) </summary>

&ensp;安全智能更新版本 **：1.335.36.0**<br/>
&ensp;发布时间 **：2021 年 4 月 2 日**<br/>
&ensp;平台 **：4.18.2103.7**<br/>
&ensp;引擎 **：1.1.18000.5**<br/>
&ensp;支持阶段 **：仅支持 (升级)**<br/>

### <a name="whats-new"></a>新增功能

- 对行为监控引擎的改进
- 扩展的网络暴力攻击缓解措施
- 启用防篡改保护后，生成 [更多失败篡改](prevent-changes-to-security-settings-with-tamper-protection.md) 尝试事件

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 2 月 (平台：4.18.2102.3 |引擎：1.1.17900.7) </summary>

&ensp;安全智能更新版本 **：1.333.7.0**<br/>
&ensp;已发布 **：2021 年 3 月 9 日**<br/>
&ensp;平台 **：4.18.2102.3**<br/>
&ensp;引擎 **：1.1.17900.7**<br/>
&ensp;支持阶段 **：仅支持 (升级)**<br/>

### <a name="whats-new"></a>新增功能

- 通过防篡改保护 [改进了服务恢复](prevent-changes-to-security-settings-with-tamper-protection.md)
- 扩展防篡改保护作用域

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 1 月 (平台：4.18.2101.9 |引擎：1.1.17800.5) </summary>

&ensp;安全智能更新版本 **：1.327.1854.0**<br/>
&ensp;发布时间 **：2021 年 2 月 2 日**<br/>
&ensp;平台 **：4.18.2101.9**<br/>
&ensp;引擎 **：1.1.17800.5**<br/>
&ensp;支持阶段 **：仅支持 (升级)**<br/>

### <a name="whats-new"></a>新增功能

- Shellcode 攻击检测改进
- 提高了凭据窃取尝试的可见性
- 改进服务中的反Microsoft Defender 防病毒功能
- 改进了对 x64 ARM的支持
- 修复：EDR执行初始检测后，阻止通知仍保留在威胁历史记录中

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2020 年 11 月 (平台：4.18.2011.6 |引擎：1.1.17700.4) </summary>

&ensp;安全智能更新版本 **：1.327.1854.0**<br/>
&ensp;发布时间 **：2020 年 12 月 3 日**<br/>
&ensp;平台 **：4.18.2011.6**<br/>
&ensp;引擎 **：1.1.17700.4**<br/>
&ensp;支持阶段 **：仅支持 (升级)**<br/>

### <a name="whats-new"></a>新增功能

- 改进 [的 SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 状态支持日志记录

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2020 年 10 月 (平台：4.18.2010.7 |引擎：1.1.17600.5) </summary>

&ensp;安全智能更新版本 **：1.327.7.0**<br/>
&ensp;发布时间 **：2020 年 10 月 29 日**<br/>
&ensp;平台 **：4.18.2010.7**<br/>
&ensp;引擎 **：1.1.17600.5**<br/>
&ensp;支持阶段 **：仅支持 (升级)**<br/>

### <a name="whats-new"></a>新增功能

- 特殊威胁类别的新说明
- 改进的模拟功能
- 改进了主机地址允许/阻止功能
- Defender CSP 中用于忽略本地用户排除项合并的新选项

### <a name="known-issues"></a>已知问题

无已知问题
<br/>
</details><details>
<summary> 2020 年 9 月 (平台：4.18.2009.7 |引擎：1.1.17500.4) </summary>

&ensp;安全智能更新版本 **：1.325.10.0**<br/>
&ensp;发布时间 **：2020 年 10 月 1 日**<br/>
&ensp;平台 **：4.18.2009.7**<br/>
&ensp;引擎 **：1.1.17500.4**<br/>
&ensp;支持阶段 **：仅支持 (升级)**<br/>

### <a name="whats-new"></a>新增功能

- 需要管理员权限才能还原隔离中的文件
- XML 格式事件现在受支持
- 忽略排除合并的云解决方案提供商支持
- 用于：
   - UDP 检查
   - Server 2019 上的网络保护
   - 网络保护的 IP 地址排除项
- 改进了对 TPM 测量的可见性
- 改进了 Office VBA 模块扫描

### <a name="known-issues"></a>已知问题

无已知问题
<br/>
</details>
<details>
<summary> 2020 年 8 月 (平台：4.18.2008.9 |引擎：1.1.17400.5) </summary>

&ensp;安全智能更新版本 **：1.323.9.0**<br/>
&ensp;发布时间 **：2020 年 8 月 27 日**<br/>
&ensp;平台 **：4.18.2008.9**<br/>
&ensp;引擎 **：1.1.17400.5**<br/>
&ensp;支持阶段 **：仅支持 (升级)**<br/>

### <a name="whats-new"></a>新增功能

- 添加更多遥测事件
- 改进了扫描事件遥测
- 改进了内存扫描行为监视
- 改进的宏流扫描
- 已 `AMRunningMode` 添加到 Get-MpComputerStatus PowerShell cmdlet
- [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 将被忽略。 Microsoft Defender 防病毒检测到其他防病毒程序时自动关闭自身。


### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

<details>
<summary> 2020 年 7 月 (平台：4.18.2007.8 |引擎：1.1.17300.4) </summary>

&ensp;安全智能更新版本 **：1.321.30.0**<br/>
&ensp;发布时间 **：2020 年 7 月 28 日**<br/>
&ensp;平台 **：4.18.2007.8**<br/>
&ensp;引擎 **：1.1.17300.4**<br/>
&ensp;支持阶段 **：仅支持技术 (升级)**<br/>

### <a name="whats-new"></a>新增功能

- 改进的 BITS 遥测
- 改进的验证码代码签名证书验证

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

<details>
<summary> 2020 年 6 月 (平台：4.18.2006.10 |引擎：1.1.17200.2) </summary>

&ensp;安全智能更新版本 **：1.319.20.0**<br/>
&ensp;发布时间 **：2020 年 6 月 22 日**<br/>
&ensp;平台 **：4.18.2006.10**<br/>
&ensp;引擎 **：1.1.17200.2**<br/>
&ensp;支持阶段 **：仅支持技术 (升级)**<br/>

### <a name="whats-new"></a>新增功能

- 指定支持 [日志的位置的可能性](./collect-diagnostic-data.md)
- 在被动模式下跳过主动的捕获扫描。
- 允许 Defender 更新按流量计费的连接
- 修复了禁用缓存时的性能调整
- 修复了注册表查询
- 修复了 ADMX 中的扫描时间随机化

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

<details>
<summary> 2020 年 5 月 (平台：4.18.2005.4 |引擎：1.1.17100.2) </summary>

&ensp;安全智能更新版本 **：1.317.20.0**<br/>
&ensp;发布时间 **：2020 年 5 月 26 日**<br/>
&ensp;平台 **：4.18.2005.4**<br/>
&ensp;引擎 **：1.1.17100.2**<br/>
&ensp;支持阶段 **：仅支持技术 (升级)**<br/>

### <a name="whats-new"></a>新增功能

- 改进了扫描事件的日志记录
- 改进了用户模式崩溃处理。
- 添加了防篡改保护的事件跟踪
- 修复了 AMSI 示例提交
- 修复了 AMSI 云阻止
- 修复了安全更新安装日志

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

<details>
<summary> 2020 年 4 月 (平台：4.18.2004.6 |引擎：1.1.17000.2) </summary>

&ensp;安全智能更新版本 **：1.315.12.0**<br/>
&ensp;发布时间 **：2020 年 4 月 30 日**<br/>
&ensp;平台 **：4.18.2004.6**<br/>
&ensp;引擎 **：1.1.17000.2**<br/>
&ensp;支持阶段 **：仅支持技术 (升级)**<br/>

### <a name="whats-new"></a>新增功能
- WDfilter 改进
- 向攻击面减少检测事件添加更多可操作事件数据
- 诊断数据和 WMI 中的固定版本信息
- 修复了平台更新后 UI 中的平台版本不正确
- 用于无文件威胁防护的动态 URL intel
- UEFI 扫描功能
- 扩展更新日志记录

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

<details>
<summary> 2020 年 3 月 (平台：4.18.2003.8 |引擎：1.1.16900.2) </summary>

&ensp;安全智能更新版本 **：1.313.8.0**<br/>
&ensp;已发布 **：2020 年 3 月 24 日**<br/>
&ensp;平台 **：4.18.2003.8**<br/>
&ensp;引擎 **：1.1.16900.4**<br/>
&ensp;支持阶段 **：仅支持技术 (升级)**<br/>

### <a name="whats-new"></a>新增功能

- 添加到[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 限制选项
- 改进诊断功能
- 将安全智能超时 (5 分钟) 
- 扩展 AMSI 引擎内部日志功能
- 改进进程阻止通知

### <a name="known-issues"></a>已知问题
[**Fixed**]Microsoft Defender 防病毒扫描时跳过文件。

<br/>
</details>

<details>

<summary> 2020 年 2 月 (平台： - |引擎：1.1.16800.2) </summary>


&ensp;安全智能更新版本 **：1.311.4.0**<br/>
&ensp;发布时间 **：2020 年 2 月 25 日**<br/>
&ensp;平台/客户端： **-**<br/>
&ensp;引擎 **：1.1.16800.2**<br/>
&ensp;支持阶段 **：仅支持技术 (升级)**<br/>

### <a name="whats-new"></a>新增功能


### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

<details>
<summary> 2020 年 1 月 (平台：4.18.2001.10 |引擎：1.1.16700.2) </summary>


安全智能更新版本 **：1.309.32.0**<br/>
发布时间 **：2020 年 1 月 30 日**<br/>
平台/客户端 **：4.18.2001.10**<br/>
引擎 **：1.1.16700.2**<br/>
&ensp;支持阶段 **：仅支持技术 (升级)**<br/>

### <a name="whats-new"></a>新增功能

- 修复了 WS2016 上的 BSOD 与 Exchange
- 当 TMP 重定向到网络路径时支持平台更新
- 平台和引擎版本已添加到 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- 将紧急签名更新扩展到 [被动模式](./microsoft-defender-antivirus-compatibility.md)
- 修复 4.18.1911.3 挂起

### <a name="known-issues"></a>已知问题

[**修复**][使用现代待机](/windows-hardware/design/device-experiences/modern-standby)模式的设备可能会遇到与 Windows Defender 筛选器驱动程序的挂起，导致保护差距。  受影响的计算机向客户显示尚未更新到最新的反恶意软件平台。
<br/>
> [!IMPORTANT]
> 此更新为：
> - 运行较低版本的平台以支持 SHA2 的 RS1 设备需要;
> - 对于有挂起问题的系统，具有重新启动标志;
> - 在 2020 年 4 月重新发布，并且不会被更新的更新所取代，以保持将来的可用性;
> - 因重启要求而分类为更新;和
> - 仅提供更新[Windows提供](https://support.microsoft.com/help/4027667/windows-10-update)。
<br/>
</details>

<details>
<summary> 2019 年 11 月 (平台：4.18.1911.3 |引擎：1.1.16600.7) </summary>

安全智能更新版本 **：1.307.13.0**<br/>
发布时间 **：2019 年 12 月 7 日**<br/>
平台 **：4.18.1911.3**<br/>
引擎 **：1.1.17000.7**<br/>
支持阶段： **不支持**<br/>

### <a name="whats-new"></a>新增功能

- 修复了 MpCmdRun 跟踪级别
- 修复了 WDFilter 版本信息
- 改进 PUA (通知) 
- 添加 MRT 日志以支持文件

### <a name="known-issues"></a>已知问题
安装此更新后，设备需要跳转程序包 4.18.2001.10 才能更新到最新的平台版本。
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Microsoft Defender 防病毒平台支持

平台和引擎更新按月提供。 若要完全受支持，请及时了解最新的平台更新。 我们的支持结构是动态的，根据最新平台版本的可用性，将发展为两个阶段：

- **安全和关键更新服务阶段** - 运行最新平台版本时，你将有资格接收反恶意软件平台的安全和关键更新。

- **技术支持 (仅在)** 阶段 - 发布新平台版本后，对早期版本 (N-2) 的支持将仅减少为技术支持。 不再支持 N-2 之前的平台版本。*

\*将继续为从 Windows 10 发行版升级提供技术支持 (请参阅[Windows 10](#platform-version-included-with-windows-10-releases)版本) 到最新平台版本的平台版本。

在技术支持 (仅在) 阶段，商业上合理的支持事件将通过 Microsoft 客户服务 & 支持和 Microsoft 的托管支持产品/服务 (如 Premier Support) 提供。 如果支持事件需要上报开发以进一步提供指导、需要非安全更新或需要安全更新，将要求客户升级到最新平台版本或中间更新 (*) 。

> [!NOTE]
> 如果要手动部署 Microsoft Defender 防病毒 平台更新，或者如果你使用脚本或非 Microsoft 管理产品来部署 Microsoft Defender 防病毒 平台更新，请确保在安装最新版本的平台更新 `4.18.2001.10` (N-2) 之前从[Microsoft](https://www.catalog.update.microsoft.com/Search.aspx?q=4.18.2001.10)更新目录中安装版本。

### <a name="platform-version-included-with-windows-10-releases"></a>版本中包含的平台Windows 10版本

下表提供了Microsoft Defender 防病毒最新版本附带的新平台和Windows 10版本：<br/><br/>

|Windows 10发布  |平台版本  |引擎版本 |支持阶段 |
|:---|:---|:---|:---|
|2004 (20H1/20H2)  |4.18.1909.6 |1.1.17000.2 | 仅支持技术 (升级)  |
|1909 (19H2)  |4.18.1902.5 |1.1.16700.3 | 仅支持技术 (升级)  |
|1903 (19H1)  |4.18.1902.5 |1.1.15600.4 | 仅支持技术 (升级)  |
|1809 (RS5)  |4.18.1807.18075 |1.1.15000.2 | 仅支持技术 (升级)  |
|1803 (RS4)  |4.13.17134.1 |1.1.14600.4 | 仅支持技术 (升级)  |
|1709 (RS3)  |4.12.16299.15 |1.1.14104.0 | 仅支持技术 (升级)  |
|1703 (RS2)  |4.11.15603.2 |1.1.13504.0 | 仅支持技术 (升级)  |
|1607 (RS1)  |4.10.14393.3683 |1.1.12805.0 | 仅支持技术 (升级)  |

有关Windows 10的信息，请参阅生命周期Windows[表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>DISM 部署映像服务和管理 (更新) 

我们建议使用最新的防病毒和反恶意软件更新更新 Windows 10 (Enterprise、Pro 和家庭版) 、Windows Server 2019、Windows Server 2022 和 Windows Server 2016 操作系统安装映像。 使操作系统安装映像保持最新有助于避免保护差距。

有关详细信息，请参阅[Microsoft Defender 更新Windows操作系统安装映像](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。

<details>
<summary>1.1.2109.01</summary>

&ensp;程序包版本 **：1.1.2109.01**<br/>
&ensp;平台版本 **：4.18.2107.4**<br/>
&ensp;引擎版本 **：1.1.18400.5**<br/>
&ensp;签名版本 **：1.347.891.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2108.01</summary>

&ensp;程序包版本 **：1.1.2108.01**<br/>
&ensp;平台版本 **：4.18.2107.4**<br/>
&ensp;引擎版本 **：1.1.18300.4**<br/>
&ensp;签名版本 **：1.343.2244.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2107.02</summary>

&ensp;程序包版本 **：1.1.2107.02**<br/>
&ensp;平台版本 **：4.18.2105.5**<br/>
&ensp;引擎版本 **：1.1.18300.4**<br/>
&ensp;签名版本 **：1.343.658.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2106.01</summary>

&ensp;程序包版本 **：1.1.2106.01**<br/>
&ensp;平台版本 **：4.18.2104.14**<br/>
&ensp;引擎版本 **：1.1.18100.6**<br/>
&ensp;签名版本 **：1.339.1923.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2105.01</summary>

&ensp;程序包版本 **：1.1.2105.01**<br/>
&ensp;平台版本 **：4.18.2103.7**<br/>
&ensp;引擎版本 **：1.1.18100.6**<br/>
&ensp;签名版本 **：1.339.42.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2104.01</summary>

&ensp;程序包版本 **：1.1.2104.01**<br/>
&ensp;平台版本 **：4.18.2102.4**<br/>
&ensp;引擎版本 **：1.1.18000.5**<br/>
&ensp;签名版本 **：1.335.232.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;程序包版本 **：1.1.2103.01**<br/>
&ensp;平台版本 **：4.18.2101.9**<br/>
&ensp;引擎版本 **：1.1.17800.5**<br/>
&ensp;签名版本 **：1.331.2302.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;程序包版本 **：1.1.2102.03**<br/>
&ensp;平台版本 **：4.18.2011.6**<br/>
&ensp;引擎版本 **：1.1.17800.5**<br/>
&ensp;签名版本 **：1.331.174.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;程序包版本 **：1.1.2101.02**<br/>
&ensp;平台版本 **：4.18.2011.6**<br/>
&ensp;引擎版本 **：1.1.17700.4**<br/>
&ensp;签名版本 **：1.329.1796.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;程序包版本 **：1.1.2012.01**<br/>
&ensp;平台版本 **：4.18.2010.7**<br/>
&ensp;引擎版本 **：1.1.17600.5**<br/>
&ensp;签名版本 **：1.327.1991.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;程序包版本 **：1.1.2011.02**<br/>
&ensp;平台版本 **：4.18.2010.7**<br/>
&ensp;引擎版本 **：1.1.17600.5**<br/>
&ensp;签名版本 **：1.327.658.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 刷新Microsoft Defender 防病毒签名
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;程序包版本 **：1.1.2011.01**<br/>
&ensp;平台版本 **：4.18.2009.7**<br/>
&ensp;引擎版本 **：1.1.17600.5**<br/>
&ensp;签名版本 **：1.327.344.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;程序包版本 **：1.1.2011.01**<br/>
&ensp;平台版本 **：4.18.2008.9**<br/>
&ensp;引擎版本 **：1.1.17400.5**<br/>
&ensp;签名版本 **：1.327.2216.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 添加了对 Windows 10 RS1 或更高版本操作系统安装映像的支持。
<br/>
</details>

## <a name="more-resources"></a>更多资源

| 文章 | 说明  |
|:---|:---|
|[适用于操作系统安装映像Windows Microsoft Defender 更新](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | 查看适用于操作系统安装映像的反恶意软件更新程序包 (WIM 和 VHD 文件) 。 获取 Microsoft Defender 防病毒、Windows 10 (Enterprise Pro 家庭版) 、Windows Server 2019、Windows Server 2022 和 Windows Server 2016 安装映像的更新。  |
|[管理保护更新的下载和应用方式](manage-protection-updates-microsoft-defender-antivirus.md) | 保护更新可以通过多个源提供。 |
|[管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md) | 你可以计划应下载保护更新的时间。 |
|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) | 如果终结点错过更新或计划扫描，可以在用户下次登录时强制进行更新或扫描。 |
|[管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md) | 你可以将保护更新设置为在启动时或在某些云提供的保护事件之后下载。 |
|[管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| 你可以指定对移动设备和虚拟机特别有用的设置（如是否应该使用电池电源进行更新）。 |
