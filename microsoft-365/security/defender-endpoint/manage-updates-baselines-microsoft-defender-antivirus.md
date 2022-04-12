---
title: 管理Microsoft Defender 防病毒更新并应用基线
description: 管理Microsoft Defender 防病毒如何接收保护和产品更新。
keywords: 更新， 安全基线， 保护， 计划更新， 强制更新， 移动更新， wsus
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
ms.date: 04/11/2022
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 48ab00c97559ecbbfe430b89c3742b8914c224ba
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788471"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>管理Microsoft Defender 防病毒更新并应用基线

**适用于：**
- [Microsoft Defender for Endpoint计划 1 和 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

保持Microsoft Defender 防病毒最新对于确保设备拥有防范新的恶意软件和攻击技术所需的最新技术和功能至关重要。 确保更新防病毒保护，即使Microsoft Defender 防病毒处于[被动模式](microsoft-defender-antivirus-compatibility.md)下运行。 有两种类型的更新与保持Microsoft Defender 防病毒最新相关：

- 安全智能更新
- 产品更新

> [!TIP]
> 若要查看最新的引擎、平台和签名日期，请访问[Microsoft Defender 防病毒和其他 Microsoft 反恶意软件的安全智能更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)

## <a name="security-intelligence-updates"></a>安全智能更新

Microsoft Defender 防病毒使用[云提供的保护](cloud-protection-microsoft-defender-antivirus.md) (也称为 Microsoft 高级保护服务或 MAPS) ，并定期下载动态安全智能更新以提供额外的保护。 这些动态更新不会通过安全智能更新 KB2267602 来取代常规的安全智能更新。

> [!NOTE]
> 更新在以下 KB 下发布：
> - Microsoft Defender 防病毒：KB2267602
> - System Center Endpoint Protection：KB2461484

云提供的保护始终处于启用状态，需要与 Internet 建立主动连接才能正常工作。 安全智能更新在计划节奏上进行， (可通过策略) 进行配置。 有关详细信息，请参阅[Microsoft Defender 防病毒中使用 Microsoft 云提供的保护](cloud-protection-microsoft-defender-antivirus.md)。

有关最近安全智能更新的列表，请参阅[Microsoft Defender 防病毒和其他 Microsoft 反恶意软件的安全智能更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。

引擎更新包含在安全智能更新中，并按每月节奏发布。

## <a name="product-updates"></a>产品更新

Microsoft Defender 防病毒需要 [每月更新 (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)称为 *平台更新*。

可以通过以下方法之一管理更新的分发：

- [Windows服务器更新服务 (WSUS) ](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- 用于将 Microsoft 和Windows更新部署到网络中终结点的常用方法。

有关详细信息，请参阅[管理Microsoft Defender 防病毒保护更新的源](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。

> [!NOTE]
> - 每月更新分阶段发布，导致 [窗口服务器更新服务](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)中显示多个包。
> - 本文列出了广泛发布通道中包含的更改。 [请参阅此处的最新广泛频道版本](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info)。
> - 若要详细了解逐步推出过程，并查看有关下一版本的详细信息，请参阅 [管理 Microsoft Defender 更新的逐步推出过程](manage-gradual-rollout.md)。
> - 若要详细了解安全智能更新，请参阅[Microsoft Defender 防病毒和其他 Microsoft 反恶意软件的安全智能更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。
> - 如果要查找 Microsoft Defender 进程列表， **[请下载 mde-urls 工作簿](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)**，然后选择 **Microsoft Defender Process** 工作表。 mde-urls 工作簿还列出了网络必须能够连接到的服务及其关联 URL，如[“启用对代理服务器中Microsoft Defender for Endpoint服务 URL 的访问”中](configure-proxy-internet.md)所述。

## <a name="monthly-platform-and-engine-versions"></a>每月平台和引擎版本

有关如何更新或安装平台更新的信息，请参阅[Windows Defender反恶意软件平台的更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。

我们的所有更新都包含

- 性能改进
- 可服务性改进
- 云、[Microsoft 365 Defender) ](/microsoft-365/security/defender/microsoft-365-defender) (集成改进
<br/><br/>
<details>
<summary>2022 年 3 月 (平台：4.18.2203.5 |引擎：1.1.19100.5) </summary>

&ensp;安全智能更新版本： **1.361.1449.0**<br/>
&ensp;发布日期： **2022 年 4 月 7 日**<br/>
&ensp;平台： **4.18.2203.5**<br/>
&ensp;引擎： **1.1.19100.5**<br/>
&ensp;支持阶段： **安全和关键更新**<br/>

引擎版本：1.1.19100.5 <br/>
安全智能更新版本：1.361.1449.0<br/>

### <a name="whats-new"></a>新增功能

- 为阻止Outlook加载项[的攻击面减少规则](attack-surface-reduction.md)添加了修复 
- 添加了与短实时进程相关的 [行为监视](configure-protection-features-microsoft-defender-antivirus.md) 性能问题的修复 
- 为 [AMSI](/windows/win32/amsi/antimalware-scan-interface-portal) 排除添加了修补程序 
- 改进 [了篡改防护](prevent-changes-to-security-settings-with-tamper-protection.md) 功能 
- 添加了一个修复程序，用于在某些情况下在使用配置时禁用`SharedSignaturesPath`[实时保护](configure-protection-features-microsoft-defender-antivirus.md) (有关参数的`SharedSignaturesPath`更多详细信息，请参阅 [Set-MpPreference](/powershell/module/defender/set-mppreference)) 

### <a name="known-issues"></a>已知问题

无已知问题

<br/><br/>
</details><details>
<summary>2022 年 2 月 (平台：4.18.2202.4 |引擎：1.1.19000.8) </summary>

&ensp;安全智能更新版本： **1.361.14.0**<br/>
&ensp;发布日期： **2022 年 3 月 14 日**<br/>
&ensp;平台： **4.18.2202.4**<br/>
&ensp;引擎： **1.1.19000.8**<br/>
&ensp;支持阶段： **安全和关键更新**<br/>

引擎版本：1.1.19000.8 <br/>
安全智能更新版本：1.361.14.0 <br/>

### <a name="whats-new"></a>新增功能

- 对检测和行为监视逻辑的改进
- 修复了误报触发攻击面减少检测
- 添加了修补程序，可提高EDR和高级搜寻检测警报的保真度
- Defender 不再支持 Toast 弹出窗口上的自定义通知。 修改了 GPO/Intune/SCCM 和文档以反映此更改。
- 用于捕获写入可移动存储的文件的信息和副本的改进。 若要了解详细信息，请参阅[Microsoft Defender for Endpoint设备控制可移动存储 访问控制可移动存储介质](device-control-removable-storage-access-control.md)。
- SmartScreen 服务无法访问时改进了流量输出 
- 使用代理和身份验证要求的客户的连接性改进
- 修复了网络 FileShares 的 VDI 设备更新 bug 
- 在块模式下EDR现在支持使用新的 CSP 实现精细设备目标。 请参阅[阻止模式下的终结点检测和响应 (EDR) ](edr-in-block-mode.md)。

### <a name="known-issues"></a>已知问题

无已知问题

<br/><br/>
</details><details>
<summary>2022 年 1 月 (平台：4.18.2201.10 |引擎：1.1.18900.2) </summary>

&ensp;安全智能更新版本： **1.357.8.0**<br/>
&ensp;发布日期： **2022 年 2 月 9 日**<br/>
&ensp;平台： **4.18.2201.10**<br/>
&ensp;引擎： **1.1.18900.2**<br/>
&ensp;支持阶段： **安全和关键更新**<br/>

引擎版本：1.1.18900.2 <br/>
安全智能更新版本：1.357.8.0 <br/>

### <a name="whats-new"></a>新增功能

- 筛选性能中的行为监视改进
- 强化到 TrustedInstaller
- 篡改保护改进
- 在 [Set-MpPreference 中](/powershell/module/defender/set-mppreference)替换`ScanScheduleTime`为新的 `ScanScheduleOffest` cmdlet。 此策略将午夜后的分钟数配置为执行计划的扫描。
- 向 [Set-MpPreference](/powershell/module/defender/set-mppreference) 添加了`-ServiceHealthReportInterval`设置。 此策略配置时间间隔 (分钟) 执行计划的扫描。
- 向 [Set-MpPreference](/powershell/module/defender/set-mppreference) 添加了`AllowSwitchToAsyncInspection`设置。 此策略可实现性能优化，允许同步检查的网络流在检查和验证后切换到异步检查。
- 性能分析器 v2 更新：添加了远程 PowerShell 和 PowerShell 7.x 支持。 有关Microsoft Defender 防病毒，请参阅[性能分析器](tune-performance-defender-antivirus.md)。
- 修复了Microsoft Defender 防病毒网络检查系统驱动程序中潜在的重复数据包 bug。

### <a name="known-issues"></a>已知问题

无已知问题

<br/><br/>
</details>


### <a name="previous-version-updates-technical-upgrade-support-only"></a>以前的版本更新：仅支持技术升级

发布新包版本后，对前两个版本的支持将减少到仅技术支持。 本部分中列出的版本早于该版本，仅提供技术升级支持。<br/><br/>

<details>
<summary>2021 年 11 月 (平台：4.18.2111.5 |引擎：1.1.18800.4) </summary>

&ensp;安全智能更新版本： **1.355.2.0**<br/>
&ensp;发布日期： **2021 年 12 月 9 日**<br/>
&ensp;平台： **4.18.2111.5**<br/>
&ensp;引擎： **1.1.18800.4**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

引擎版本：1.1.18800.4 安全智能更新版本：1.355.2.0

### <a name="whats-new"></a>新增功能

- 提高了Exchange服务器上某些密集型方案的 CPU 使用效率
- 在 Defender PowerShell 模块的Get-MpComputerStatus下添加了新的设备控制状态字段。 有关详细信息，请参阅[Microsoft Defender for Endpoint设备控制可移动存储 访问控制](device-control-removable-storage-access-control.md)。
- 修复了 `SharedSignatureRoot` 使用 PowerShell 设置值时无法删除值的 bug
- 修复了无法启用[篡改保护](prevent-changes-to-security-settings-with-tamper-protection.md)的 bug，尽管Microsoft Defender for Endpoint表示已启用篡改保护
- 为Microsoft Defender 防病毒工具的性能分析器添加了可支持性和 bug 修复。 有关详细信息，请参阅[性能分析器Microsoft Defender 防病毒](tune-performance-defender-antivirus.md)。   
   - 为其添加了 PowerShell ISE 支持 `New-MpPerformanceRecording`
   - 修复了 bug 错误 `Get-MpPerformanceReport -TopFilesPerProcess`
   - 修复了在 PowerShell 7.x、远程会话和 PowerShell ISE 中使用 `New-MpPerformanceRecording` 时性能录制会话泄漏的问题


### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 10 月 (平台：4.18.2110.6 |引擎：1.1.18700.4) </summary>

&ensp;安全智能更新版本： **1.353.3.0**<br/>
&ensp;发布日期： **2021 年 10 月 28 日**<br/>
&ensp;平台： **4.18.2110.6**<br/>
&ensp;引擎： **1.1.18700.4**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

引擎版本：1.1.18700.4 安全智能更新版本：1.353.3.0

### <a name="whats-new"></a>新增功能

- 对文件传输协议 (FTP) 网络流量覆盖率的改进
- 修复了如何减少在Windows Server 2016上运行的Exchange Server中的 Microsoft Defender CPU 使用率
- 修复扫描中断问题
- 修复了安全中心未出现阻止篡改尝试的警报
- Microsoft Defender 服务中篡改复原能力的改进

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 9 月 (平台：4.18.2109.6 |引擎：1.1.18600.4) </summary>

&ensp;安全智能更新版本： **1.351.7.0**<br/>
&ensp;发布日期： **2021 年 10 月 7 日**<br/>
&ensp;平台： **4.18.2109.6**<br/>
&ensp;引擎： **1.1.18600.4**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

引擎版本：1.1.18600.4 安全智能更新版本：1.351.7.0

### <a name="whats-new"></a>新增功能
- Microsoft Defender 防病毒引擎和平台更新的新延迟环。 选择加入此环的设备将收到延迟 48 小时的更新。 建议仅针对关键环境使用新的延迟环。 请参阅 [管理 Microsoft Defender 更新的逐步推出过程](manage-gradual-rollout.md)。
- Microsoft Defender 更新逐步推出过程的改进

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 8 月 (平台：4.18.2108.7 |引擎：1.1.18500.10) </summary>

&ensp;安全智能更新版本： **1.349.22.0**<br/>
&ensp;发布日期： **2021 年 9 月 2 日**<br/>
&ensp;平台： **4.18.2108.7**<br/>
&ensp;引擎： **1.1.18500.10**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能
- 对行为监视引擎的改进
- 发布了[用于Microsoft Defender 防病毒的新性能分析器](tune-performance-defender-antivirus.md)
- Microsoft Defender 防病毒针对加载恶意 DLL 进行强化
- Microsoft Defender 防病毒针对 TrustedInstaller 旁路进行强化
- 扩展文件更改通知以包含更多数据用于Human-Operated勒索软件 (HumOR) 

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 7 月至 2021 年 7 月 (平台：4.18.2107.4 |引擎：1.1.18400.4) </summary>

&ensp;安全智能更新版本： **1.345.13.0**<br/>
&ensp;发布日期： **2021 年 8 月 5 日**<br/>
&ensp;平台： **4.18.2107.4**<br/>
&ensp;引擎： **1.1.18400.4**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能
- 为Windows可移植设备添加了设备控制支持
- 默认情况下，对使用者启用可能不需要的应用程序 (PUA) 保护 (看到 [可能不需要的应用将被阻止](https://support.microsoft.com/windows/potentially-unwanted-apps-will-be-blocked-by-default-b9f53cb9-7f1e-40bb-8c6b-a17e0ab6289e)) 
- 组策略对象托管系统的计划扫描将遵循用户配置的扫描时间
- 对行为监视引擎的改进

### <a name="known-issues"></a>已知问题
无已知问题

<br/>
</details><details>
<summary> 2021 年 6 月 (平台：4.18.2106.5 |引擎：1.1.18300.4) </summary>

&ensp;安全智能更新版本： **1.343.17.0**<br/>
&ensp;发布日期： **2021 年 6 月 28 日**<br/>
&ensp;平台： **4.18.2106.5**<br/>
&ensp;引擎： **1.1.18300.4**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能
- 用于管理 Microsoft Defender 更新逐步推出过程的新控件。 请参阅 [管理 Microsoft Defender 更新的逐步推出过程](manage-gradual-rollout.md)。
- 对行为监视引擎的改进
- 反恶意软件定义推出改进
- 扩展边缘网络事件检查

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 5 月 (平台：4.18.2105.4 |引擎：1.1.18200.4) </summary>

&ensp;安全智能更新版本： **1.341.8.0**<br/>
&ensp;发布日期： **2021 年 6 月 3 日**<br/>
&ensp;平台： **4.18.2105.4**<br/>
&ensp;引擎： **1.1.18200.4**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能
- 对[行为监视](client-behavioral-blocking.md)的改进
- 修复了 [网络保护](network-protection.md) 通知筛选功能

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 4 月 (平台：4.18.2104.14 |引擎：1.1.18100.5) </summary>

&ensp;安全智能更新版本： **1.337.2.0**<br/>
&ensp;发布日期： **2021 年 4 月 26**  日 (引擎：1.1.18100.6 发布于 2021 年 5 月 5 日) <br/>
&ensp;平台： **4.18.2104.14**<br/>
&ensp;引擎： **1.1.18100.5**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能
- 更多行为监视逻辑
- 改进了内核模式密钥记录器检测
- 添加了新控件以管理 [Microsoft Defender 更新](manage-gradual-rollout.md)的逐步推出过程


### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 3 月 (平台：4.18.2103.7 |引擎：1.1.18000.5) </summary>

&ensp;安全智能更新版本： **1.335.36.0**<br/>
&ensp;发布日期： **2021 年 4 月 2 日**<br/>
&ensp;平台： **4.18.2103.7**<br/>
&ensp;引擎： **1.1.18000.5**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能

- 对行为监视引擎的改进
- 扩展的网络暴力攻击缓解措施
- 启用 [篡改保护](prevent-changes-to-security-settings-with-tamper-protection.md) 时，更多失败的篡改尝试事件生成

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 2 月-2021 (平台：4.18.2102.3 |引擎：1.1.17900.7) </summary>

&ensp;安全智能更新版本： **1.333.7.0**<br/>
&ensp;发布日期： **2021 年 3 月 9 日**<br/>
&ensp;平台： **4.18.2102.3**<br/>
&ensp;引擎： **1.1.17900.7**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能

- 通过[篡改保护](prevent-changes-to-security-settings-with-tamper-protection.md)改进了服务恢复
- 扩展篡改保护范围

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2021 年 1 月 (平台：4.18.2101.9 |引擎：1.1.17800.5) </summary>

&ensp;安全智能更新版本： **1.327.1854.0**<br/>
&ensp;发布日期： **2021 年 2 月 2 日**<br/>
&ensp;平台： **4.18.2101.9**<br/>
&ensp;引擎： **1.1.17800.5**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能

- Shellcode 攻击检测改进
- 提高凭据窃取尝试的可见性
- 改进了Microsoft Defender 防病毒服务中的防吸功能
- 改进了对 ARM x64 仿真的支持
- 修复：执行实时保护执行初始检测后，EDR阻止通知仍保留在威胁历史记录中

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2020 年 11 月 (平台：4.18.2011.6 |引擎：1.1.17700.4) </summary>

&ensp;安全智能更新版本： **1.327.1854.0**<br/>
&ensp;发布日期： **2020 年 12 月 3 日**<br/>
&ensp;平台： **4.18.2011.6**<br/>
&ensp;引擎： **1.1.17700.4**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能

- 改进了 [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 状态支持日志记录

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details><details>
<summary> 2020 年 10 月 (平台：4.18.2010.7 |引擎：1.1.17600.5) </summary>

&ensp;安全智能更新版本： **1.327.7.0**<br/>
&ensp;发布日期： **2020 年 10 月 29 日**<br/>
&ensp;平台： **4.18.2010.7**<br/>
&ensp;引擎： **1.1.17600.5**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能

- 特殊威胁类别的新说明
- 改进了仿真功能
- 改进了主机地址允许/阻止功能
- Defender CSP 中用于忽略本地用户排除项合并的新选项

### <a name="known-issues"></a>已知问题

无已知问题
<br/>
</details><details>
<summary> 2020 年 9 月 (平台：4.18.2009.7 |引擎：1.1.17500.4) </summary>

&ensp;安全智能更新版本： **1.325.10.0**<br/>
&ensp;发布日期： **2020 年 10 月 1 日**<br/>
&ensp;平台： **4.18.2009.7**<br/>
&ensp;引擎： **1.1.17500.4**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能

- 在隔离区还原文件需要管理员权限
- 现在支持 XML 格式的事件
- CSP 支持忽略排除合并
- 适用于以下功能的新管理接口：
   - UDP 检查
   - 服务器 2019 上的网络保护
   - 网络保护的 IP 地址排除项
- 提高了 TPM 度量的可见性
- 改进了Office VBA 模块扫描

### <a name="known-issues"></a>已知问题

无已知问题
<br/>
</details>
<details>
<summary> 2020 年 8 月 (平台：4.18.2008.9 |引擎：1.1.17400.5) </summary>

&ensp;安全智能更新版本： **1.323.9.0**<br/>
&ensp;发布日期： **2020 年 8 月 27 日**<br/>
&ensp;平台： **4.18.2008.9**<br/>
&ensp;引擎： **1.1.17400.5**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能

- 添加更多遥测事件
- 改进了扫描事件遥测
- 改进了内存扫描的行为监视
- 改进了宏流扫描
- 添加 `AMRunningMode` 到 Get-MpComputerStatus PowerShell cmdlet
- [忽略 DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 。 Microsoft Defender 防病毒在检测到另一个防病毒程序时自动关闭。


### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

<details>
<summary> 2020年7月至2020年7月 (平台：4.18.2007.8 |引擎：1.1.17300.4) </summary>

&ensp;安全智能更新版本： **1.321.30.0**<br/>
&ensp;发布日期： **2020 年 7 月 28 日**<br/>
&ensp;平台： **4.18.2007.8**<br/>
&ensp;引擎： **1.1.17300.4**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能

- 改进了 BITS 遥测
- 改进了 Authenticode 代码签名证书验证

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

<details>
<summary> 2020 年 6 月 (平台：4.18.2006.10 |引擎：1.1.17200.2) </summary>

&ensp;安全智能更新版本： **1.319.20.0**<br/>
&ensp;发布日期： **2020 年 6 月 22 日**<br/>
&ensp;平台： **4.18.2006.10**<br/>
&ensp;引擎： **1.1.17200.2**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能

- 指定[支持日志位置](./collect-diagnostic-data.md)的可能性
- 在被动模式下跳过攻击性追赶扫描。
- 允许 Defender 更新按流量计费的连接
- 修复了禁用缓存时的性能优化
- 修复了注册表查询
- 修复了 ADMX 中的扫描时间随机化

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

<details>
<summary> 2020 年 5 月 (平台：4.18.2005.4 |引擎：1.1.17100.2) </summary>

&ensp;安全智能更新版本： **1.317.20.0**<br/>
&ensp;发布日期： **2020 年 5 月 26 日**<br/>
&ensp;平台： **4.18.2005.4**<br/>
&ensp;引擎： **1.1.17100.2**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能

- 改进了扫描事件的日志记录
- 改进了用户模式故障处理。
- 添加了用于篡改保护的事件跟踪
- 修复了 AMSI 示例提交
- 修复了 AMSI 云阻塞问题
- 固定安全更新安装日志

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

<details>
<summary> 2020 年 4 月 (平台：4.18.2004.6 |引擎：1.1.17000.2) </summary>

&ensp;安全智能更新版本： **1.315.12.0**<br/>
&ensp;发布日期： **2020 年 4 月 30 日**<br/>
&ensp;平台： **4.18.2004.6**<br/>
&ensp;引擎： **1.1.17000.2**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能
- WDfilter 改进
- 添加更多可操作的事件数据来攻击表面减少检测事件
- 修复了诊断数据和 WMI 中的版本信息
- 修复了平台更新后 UI 中不正确的平台版本
- 用于无文件威胁防护的动态 URL intel
- UEFI 扫描功能
- 扩展更新日志记录

### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

<details>
<summary> 2020 年 3 月 (平台：4.18.2003.8 |引擎：1.1.16900.2) </summary>

&ensp;安全智能更新版本： **1.313.8.0**<br/>
&ensp;发布日期： **2020 年 3 月 24 日**<br/>
&ensp;平台： **4.18.2003.8**<br/>
&ensp;引擎： **1.1.16900.4**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能

- 添加到 [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md) 的 CPU 限制选项
- 改进诊断功能
- 将安全智能超时 (5 分钟) 
- 扩展 AMSI 引擎内部日志功能
- 改进进程阻止通知

### <a name="known-issues"></a>已知问题
[**已修复**]Microsoft Defender 防病毒在运行扫描时跳过文件。

<br/>
</details>

<details>

<summary> 2020 年 2 月 (平台： - |引擎：1.1.16800.2) </summary>


&ensp;安全智能更新版本： **1.311.4.0**<br/>
&ensp;发布日期： **2020 年 2 月 25 日**<br/>
&ensp;平台/客户端： **-**<br/>
&ensp;引擎： **1.1.16800.2**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能


### <a name="known-issues"></a>已知问题
无已知问题
<br/>
</details>

<details>
<summary> 2020 年 1 月 (平台：4.18.2001.10 |引擎：1.1.16700.2) </summary>


安全智能更新版本： **1.309.32.0**<br/>
发布日期： **2020 年 1 月 30 日**<br/>
平台/客户端： **4.18.2001.10**<br/>
引擎： **1.1.16700.2**<br/>
&ensp;支持阶段： **技术升级支持仅 ()**<br/>

### <a name="whats-new"></a>新增功能

- 修复了 WS2016 上包含Exchange的 BSOD
- 将 TMP 重定向到网络路径时支持平台更新
- 平台和引擎版本将添加到 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- 将紧急签名更新扩展到 [被动模式](./microsoft-defender-antivirus-compatibility.md)
- 修复 4.18.1911.3 挂起问题

### <a name="known-issues"></a>已知问题

[**已修复**] 使用 [新式备用模式](/windows-hardware/design/device-experiences/modern-standby)的设备可能会遇到与Windows Defender筛选器驱动程序的挂起，从而导致保护缺口。  客户认为受影响的计算机尚未更新到最新的反恶意软件平台。
<br/>
> [!IMPORTANT]
> 此更新为：
> - 运行较低版本的平台的 RS1 设备需要支持 SHA2;
> - 对于存在挂起问题的系统，具有重新启动标志;
> - 在 2020 年 4 月重新发布，不会被更新取代，以保持未来的可用性;
> - 由于重新启动要求，已分类为更新;和
> - 仅提供[Windows 更新](https://support.microsoft.com/help/4027667/windows-10-update)。
<br/>
</details>

<details>
<summary> 2019 年 11 月 (平台：4.18.1911.3 |引擎：1.1.16600.7) </summary>

安全智能更新版本： **1.307.13.0**<br/>
发布日期： **2019 年 12 月 7 日**<br/>
平台： **4.18.1911.3**<br/>
引擎： **1.1.17000.7**<br/>
支持阶段： **无支持**<br/>

### <a name="whats-new"></a>新增功能

- 修复了 MpCmdRun 跟踪级别
- 修复了 WDFilter 版本信息
- 改进 PUA (通知) 
- 添加 MRT 日志以支持文件

### <a name="known-issues"></a>已知问题
安装此更新后，设备需要跳转包 4.18.2001.10 才能更新到最新平台版本。
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Microsoft Defender 防病毒平台支持

平台和引擎更新按月节奏提供。 若要获得完全支持，请随时了解最新的平台更新。 我们的支持结构是动态的，根据最新平台版本的可用性，这分为两个阶段：

- **安全更新和关键更新服务阶段** - 运行最新平台版本时，你将有资格接收反恶意软件平台的安全更新和关键更新。

- **技术支持 (仅) 阶段** - 发布新平台版本后，对旧版本 (N-2) 的支持将减少到仅技术支持。 不再支持低于 N-2 的平台版本。*

\*将继续为从Windows 10版本升级提供技术支持 (请参阅) 到最新平台[版本的Windows 10版本中包含的平台](#platform-version-included-with-windows-10-releases)版本。

在技术支持 (仅) 阶段，Microsoft 客户服务&支持和 Microsoft 托管支持产品/服务 (（如顶级支持) ）将提供商业上合理的支持事件。 如果支持事件需要升级到开发以获得进一步指导、需要非安全更新或需要安全更新，则将要求客户升级到最新平台版本或中间更新 (*) 。

> [!NOTE]
> 如果要手动部署Microsoft Defender 防病毒平台更新，或者使用脚本或非 Microsoft 管理产品部署Microsoft Defender 防病毒平台更新，请确保在安装最新版本的平台更新 (N-2) 之前，从 [Microsoft 更新目录](https://www.catalog.update.microsoft.com/Search.aspx?q=4.18.2001.10)安装版本`4.18.2001.10`。

### <a name="platform-version-included-with-windows-10-releases"></a>Windows 10版本中包含的平台版本

下表提供了随最新Windows 10版本一起提供的Microsoft Defender 防病毒平台和引擎版本：<br/><br/>

|Windows 10版本  |平台版本  |引擎版本 |支持阶段 |
|:---|:---|:---|:---|
|2004 (20H1/20H2)  |4.18.1909.6 |1.1.17000.2 | 技术升级支持仅 ()  |
|1909 (19H2)  |4.18.1902.5 |1.1.16700.3 | 技术升级支持仅 ()  |
|1903 (19H1)  |4.18.1902.5 |1.1.15600.4 | 技术升级支持仅 ()  |
|1809 (RS5)  |4.18.1807.18075 |1.1.15000.2 | 技术升级支持仅 ()  |
|1803 (RS4)  |4.13.17134.1 |1.1.14600.4 | 技术升级支持仅 ()  |
|1709 (RS3)  |4.12.16299.15 |1.1.14104.0 | 技术升级支持仅 ()  |
|1703 (RS2)  |4.11.15603.2 |1.1.13504.0 | 技术升级支持仅 ()  |
|1607 (RS1)  |4.10.14393.3683 |1.1.12805.0 | 技术升级支持仅 ()  |

有关Windows 10发布信息，请参阅[Windows生命周期概况介绍。](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>部署映像服务和管理 (DISM) 的更新

建议使用最新的防病毒和反恶意软件更新更新Windows 10 (Enterprise、Pro和主页版本) 、Windows Server 2019、Windows Server 2022 和 Windows Server 2016 OS 安装映像。 使 OS 安装映像保持最新有助于避免在保护方面出现缺口。

有关详细信息，请参阅 [Microsoft Defender 更新Windows操作系统安装映像](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。

<details>
<summary>20220321.1</summary>

&ensp;包版本： **20220321.1**<br/>
&ensp;平台版本： **4.18.2202.4**<br/>
&ensp;引擎版本： **1.1.19000.8**<br/>
&ensp;签名版本： **1.351.337.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无

<br/>
</details><details>
<summary>20220305.1</summary>

&ensp;包版本： **20220305.1**<br/>
&ensp;平台版本： **4.18.2201.10**<br/>
&ensp;引擎版本： **1.1.18900.3**<br/>
&ensp;签名版本： **1.359.1405.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无

<br/>
</details><details>
<summary>20220203.1</summary>

&ensp;包版本： **20220203.1**<br/>
&ensp;平台版本： **4.18.2111.5**<br/>
&ensp;引擎版本： **1.1.18900.2**<br/>
&ensp;签名版本： **1.357.32.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>20220105.1</summary>

&ensp;包版本： **20220105.1**<br/>
&ensp;平台版本： **4.18.2111.5**<br/>
&ensp;引擎版本： **1.1.18800.4**<br/>
&ensp;签名版本： **1.355.1482.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2112.01</summary>

&ensp;包版本： **1.1.2112.01**<br/>
&ensp;平台版本： **4.18.2110.6**<br/>
&ensp;引擎版本： **1.1.18700.4**<br/>
&ensp;签名版本： **1.353.2283.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2111.02</summary>

&ensp;包版本： **1.1.2111.02**<br/>
&ensp;平台版本： **4.18.2110.6**<br/>
&ensp;引擎版本： **1.1.18700.4**<br/>
&ensp;签名版本： **1.353.613.0**<br/>

### <a name="fixes"></a>修补程序
- 修复了与本地化文件相关的问题

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2110.01</summary>

&ensp;包版本： **1.1.2110.01**<br/>
&ensp;平台版本： **4.18.2109.6**<br/>
&ensp;引擎版本： **1.1.18500.10**<br/>
&ensp;签名版本： **1.349.2103.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2109.01</summary>

&ensp;包版本： **1.1.2109.01**<br/>
&ensp;平台版本： **4.18.2107.4**<br/>
&ensp;引擎版本： **1.1.18400.5**<br/>
&ensp;签名版本： **1.347.891.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2108.01</summary>

&ensp;包版本： **1.1.2108.01**<br/>
&ensp;平台版本： **4.18.2107.4**<br/>
&ensp;引擎版本： **1.1.18300.4**<br/>
&ensp;签名版本： **1.343.2244.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2107.02</summary>

&ensp;包版本： **1.1.2107.02**<br/>
&ensp;平台版本： **4.18.2105.5**<br/>
&ensp;引擎版本： **1.1.18300.4**<br/>
&ensp;签名版本： **1.343.658.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2106.01</summary>

&ensp;包版本： **1.1.2106.01**<br/>
&ensp;平台版本： **4.18.2104.14**<br/>
&ensp;引擎版本： **1.1.18100.6**<br/>
&ensp;签名版本： **1.339.1923.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2105.01</summary>

&ensp;包版本： **1.1.2105.01**<br/>
&ensp;平台版本： **4.18.2103.7**<br/>
&ensp;引擎版本： **1.1.18100.6**<br/>
&ensp;签名版本： **1.339.42.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2104.01</summary>

&ensp;包版本： **1.1.2104.01**<br/>
&ensp;平台版本： **4.18.2102.4**<br/>
&ensp;引擎版本： **1.1.18000.5**<br/>
&ensp;签名版本： **1.335.232.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;包版本： **1.1.2103.01**<br/>
&ensp;平台版本： **4.18.2101.9**<br/>
&ensp;引擎版本： **1.1.17800.5**<br/>
&ensp;签名版本： **1.331.2302.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;包版本： **1.1.2102.03**<br/>
&ensp;平台版本： **4.18.2011.6**<br/>
&ensp;引擎版本： **1.1.17800.5**<br/>
&ensp;签名版本： **1.331.174.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;包版本： **1.1.2101.02**<br/>
&ensp;平台版本： **4.18.2011.6**<br/>
&ensp;引擎版本： **1.1.17700.4**<br/>
&ensp;签名版本： **1.329.1796.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;包版本： **1.1.2012.01**<br/>
&ensp;平台版本： **4.18.2010.7**<br/>
&ensp;引擎版本： **1.1.17600.5**<br/>
&ensp;签名版本： **1.327.1991.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;包版本： **1.1.2011.02**<br/>
&ensp;平台版本： **4.18.2010.7**<br/>
&ensp;引擎版本： **1.1.17600.5**<br/>
&ensp;签名版本： **1.327.658.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 刷新Microsoft Defender 防病毒签名
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;包版本： **1.1.2011.01**<br/>
&ensp;平台版本： **4.18.2009.7**<br/>
&ensp;引擎版本： **1.1.17600.5**<br/>
&ensp;签名版本： **1.327.344.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 无
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;包版本： **1.1.2011.01**<br/>
&ensp;平台版本： **4.18.2008.9**<br/>
&ensp;引擎版本： **1.1.17400.5**<br/>
&ensp;签名版本： **1.327.2216.0**<br/>

### <a name="fixes"></a>修补程序
- 无

### <a name="additional-information"></a>其他信息
- 添加了对 Windows 10 RS1 或更高版本 OS 安装映像的支持。
<br/>
</details>

## <a name="more-resources"></a>更多资源

| 文章 | 说明  |
|:---|:---|
|[适用于Windows操作系统安装映像的 Microsoft Defender 更新](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | 查看 OS 安装映像的反恶意软件更新包 (WIM 和 VHD 文件) 。 获取Windows 10 (Enterprise、Pro和主页版本) 、Windows Server 2019、Windows Server 2022 和Windows Server 2016安装映像的Microsoft Defender 防病毒更新。  |
|[管理如何下载和应用保护更新](manage-protection-updates-microsoft-defender-antivirus.md) | 可通过多个源提供保护更新。 |
|[管理何时应下载和应用保护更新](manage-protection-update-schedule-microsoft-defender-antivirus.md) | 可以计划何时应下载保护更新。 |
|[管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md) | 如果终结点未通过更新或计划扫描，则可以在用户下次登录时强制更新或扫描。 |
|[管理基于事件的强制更新](manage-event-based-updates-microsoft-defender-antivirus.md) | 可以将保护更新设置为在启动时或某些云传送的保护事件之后下载。 |
|[管理移动设备和虚拟机 （VM） 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| 可以指定对移动设备和虚拟机特别有用的设置，例如是否应在电池电源上进行更新。 |
| [Microsoft Defender for Endpoint EDR传感器的更新](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac) | 可以更新 2021 年发布的新Microsoft Defender for Endpoint统一解决方案包中包含的EDR传感器 (MsSense.exe) 。   |

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)