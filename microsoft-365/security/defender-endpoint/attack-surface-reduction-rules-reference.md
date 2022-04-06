---
title: 攻击面减少规则参考
description: 列出有关按规则减少攻击面规则的详细信息。
keywords: 攻击面减少规则， ASR， asr 规则， 臀部， 主机入侵预防系统， 保护规则， 反攻击规则， 反开发， 攻击规则， 感染预防规则， Microsoft Defender for Endpoint， 配置 ASR 规则， ASR 规则说明
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar,
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.date: 02/04/2022
ms.openlocfilehash: 4662e6b6af9c90f22b6e54c58f54ba80049dc3e1
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663063"
---
# <a name="attack-surface-reduction-rules-reference"></a>攻击面减少规则参考

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

本文提供有关减少攻击规则的信息：

- [支持的操作系统版本](#supported-operating-systems)
- [支持的配置管理系统](#supported-configuration-management-systems)
- [按规则警报和通知详细信息](#per-rule-alert-and-notification-details)
- [ASR 规则和 GUID 矩阵](#asr-rules-and-guids-matrix)
- [ASR 规则模式](#asr-rule-modes)
- [按规则说明](#per-rule-descriptions)
  - 规则说明
  - 配置管理系统规则名称

## <a name="public-preview-supported-operating-systems"></a>公共预览版：支持的操作系统

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

下表列出了当前预发行产品的攻击面减少规则支持的操作系统。 规则按字母顺序列出。 除非另有说明，否则最小Windows&nbsp; 10版本为版本 1709 (RS3，版本 16299) 或更高版本;Windows Server 版本的最小&nbsp;版本为 1809 或更高版本。

> [!NOTE]
> Windows&nbsp; Server2012R2&nbsp;&nbsp; 和 Windows&nbsp; Server2016&nbsp; 中的攻击面减少规则适用于使用新式统一解决方案包载入的设备。 有关详细信息，请参阅[适用于 Windows Server 2012 R2 和 2016 预览版的现代统一解决方案中的新功能](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)。
>

| 规则名称 | &nbsp;Windows Server 2016 <sup>[[1](#fn1)]<sup></sup> | &nbsp;Windows Server 2012 R2 <sup>[[1](#fn1)]<sup></sup> |
|---|:---:|:---:|
|[阻止滥用被利用的易受攻击的签名驱动程序](#block-abuse-of-exploited-vulnerable-signed-drivers) | Y | Y |
|[阻止 Adobe Reader 创建子进程](#block-adobe-reader-from-creating-child-processes) | Y | Y |
|[阻止所有Office应用程序创建子进程](#block-all-office-applications-from-creating-child-processes) | Y | Y |
|[阻止从Windows本地安全机构子系统 (lsass.exe) 窃取凭据](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Y | Y |
|[阻止电子邮件客户端和 Webmail 中的可执行内容](#block-executable-content-from-email-client-and-webmail) | Y | Y |
|[阻止可执行文件运行，除非它们满足普遍性、年龄或受信任的列表条件](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Y | Y |
|[阻止执行可能混淆的脚本](#block-execution-of-potentially-obfuscated-scripts) | Y | Y |
|[阻止 JavaScript 或 VBScript 启动下载的可执行内容](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | N | N |
|[阻止Office应用程序创建可执行内容](#block-office-applications-from-creating-executable-content) | Y | Y |
|[阻止Office应用程序将代码注入其他进程](#block-office-applications-from-injecting-code-into-other-processes)  | Y | Y |
|[阻止Office通信应用程序创建子进程](#block-office-communication-application-from-creating-child-processes) | Y | Y |
|[通过 WMI 事件订阅](#block-persistence-through-wmi-event-subscription)\*阻止持久性 _不支持文件和文件夹排除项。_ | N | N |
|[阻止源自 PSExec 和 WMI 命令的进程创建](#block-process-creations-originating-from-psexec-and-wmi-commands) | Y | Y |
|[阻止从 USB 运行的不受信任和未签名的进程](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Y | Y |
|[阻止来自Office宏的 Win32 API 调用](#block-win32-api-calls-from-office-macros) | N | N |
|[对勒索软件使用高级保护](#use-advanced-protection-against-ransomware) | Y | Y |
|  |  |  |

 (<a id="fn1">1</a>) 是指适用于 Windows Server 2012 和 2016 的新式统一解决方案。 有关详细信息，请参阅[将Windows服务器载入 Defender for Endpoint 服务](configure-server-endpoints.md)。

_结束公共预览版：支持的操作系统_

## <a name="supported-operating-systems"></a>支持的操作系统 

下表列出了当前发布到正式版的规则支持的操作系统。 规则按字母顺序列出。

> [!Note]
>
> 除非另有说明，否则最小Windows&nbsp; 10版本为版本 1709 (RS3，版本 16299) 或更高版本;Windows Server 版本的最小&nbsp;版本为 1809 或更高版本。
>

|规则名称|&nbsp;Windows 10|&nbsp;Windows Server 2019|&nbsp;Windows Server|
|---|:---:|:---:|:---:|
|[阻止滥用被利用的易受攻击的签名驱动程序](#block-abuse-of-exploited-vulnerable-signed-drivers) | Y | Y | Y <br><br> 版本 1803 (半年频道) 或更高版本 |
|[阻止 Adobe Reader 创建子进程](#block-adobe-reader-from-creating-child-processes) | Y 版本 1809 或更高版本 | Y | Y  <br><br> |
|[阻止所有Office应用程序创建子进程](#block-all-office-applications-from-creating-child-processes) | Y | Y | Y <br><br> |
|[阻止从Windows本地安全机构子系统 (lsass.exe) 窃取凭据](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Y 版本 1803 或更高版本 | Y <br><br> | Y <br><br> |
|[阻止电子邮件客户端和 Webmail 中的可执行内容](#block-executable-content-from-email-client-and-webmail) | Y | Y <br><br> | Y <br><br> |
|[阻止可执行文件运行，除非它们满足普遍性、年龄或受信任的列表条件](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Y 版本 1803 或更高版本 | Y <br><br> | Y <br><br> |
|[阻止执行可能混淆的脚本](#block-execution-of-potentially-obfuscated-scripts) | Y | Y <br><br> | Y <br><br> |
|[阻止 JavaScript 或 VBScript 启动下载的可执行内容](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | Y | Y <br><br> | Y <br><br> |
|[阻止Office应用程序创建可执行内容](#block-office-applications-from-creating-executable-content) | Y | Y <br><br> | Y <br><br> |
|[阻止Office应用程序将代码注入其他进程](#block-office-applications-from-injecting-code-into-other-processes)  | Y | Y <br><br> | Y <br><br> |
|[阻止Office通信应用程序创建子进程](#block-office-communication-application-from-creating-child-processes) | Y | Y <br><br> | Y <br><br> |
|[通过 WMI 事件订阅阻止持久性](#block-persistence-through-wmi-event-subscription) <br><br> \*_不支持文件和文件夹排除项。_ | Y 版本 1903 (内部版本 18362) 或更高版本| Y | Y <br><br> 版本 1903 (内部版本 18362) 或更高版本 |
|[阻止源自 PSExec 和 WMI 命令的进程创建](#block-process-creations-originating-from-psexec-and-wmi-commands) | Y 版本 1803 或更高版本 | Y <br><br> | Y <br><br>  |
|[阻止从 USB 运行的不受信任和未签名的进程](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Y | Y <br><br> | Y <br><br> |
|[阻止来自Office宏的 Win32 API 调用](#block-win32-api-calls-from-office-macros) | Y | Y <br><br> | Y <br><br> |
|[对勒索软件使用高级保护](#use-advanced-protection-against-ransomware) | Y 版本 1803 或更高版本 | Y <br><br> | Y <br><br> |
|  |  |  |  |

## <a name="supported-configuration-management-systems"></a>支持的配置管理系统

下表列出了有关此表中引用的配置管理系统版本的信息的链接。

|规则名称 | Intune | Microsoft Endpoint Manager |Microsoft Endpoint Configuration Manager |<sup>组策略[[1](#fn1)]<sup></sup> | PowerShell<sup>[[1](#fn1)]<sup></sup>  |
|---|:---:|:---:|:---:|:---:|:---:|
|[阻止滥用被利用的易受攻击的签名驱动程序](#block-abuse-of-exploited-vulnerable-signed-drivers) | Y  | Y MEM OMA-URI |   | Y  |  Y  |
|[阻止 Adobe Reader 创建子进程](#block-adobe-reader-from-creating-child-processes) | Y |   |  | Y  | Y  |
|[阻止所有Office应用程序创建子进程](#block-all-office-applications-from-creating-child-processes) | Y |   |Y <br><br> CB 1710 | Y  | Y  |
|[阻止从Windows本地安全机构子系统 (lsass.exe) 窃取凭据](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Y  |   | Y <br><br>CB 1802 | Y  | Y  |
|[阻止电子邮件客户端和 Webmail 中的可执行内容](#block-executable-content-from-email-client-and-webmail) | Y |  |Y <br><br> CB 1710 | Y | Y  |
|[阻止可执行文件运行，除非它们满足普遍性、年龄或受信任的列表条件](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Y |   | Y <br><br> CB 1802 |  Y |  Y |
|[阻止执行可能混淆的脚本](#block-execution-of-potentially-obfuscated-scripts) | Y |   |  Y  <br><br> CB 1710 | Y  | Y  |
|[阻止 JavaScript 或 VBScript 启动下载的可执行内容](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | Y |   | Y <br><br> CB 1710 | Y  | Y  |
|[阻止Office应用程序创建可执行内容](#block-office-applications-from-creating-executable-content) | Y |  |Y <br><br> CB 1710 | Y  | Y  |
|[阻止Office应用程序将代码注入其他进程](#block-office-applications-from-injecting-code-into-other-processes) | Y |  | Y <br><br> CB 1710 | Y  | Y  |
|[阻止Office通信应用程序创建子进程](#block-office-communication-application-from-creating-child-processes) | Y |  |Y <br><br> CB 1710 | Y  | Y  |
|[通过 WMI 事件订阅阻止持久性](#block-persistence-through-wmi-event-subscription) |  |  |  |Y   | Y  |
|[阻止源自 PSExec 和 WMI 命令的进程创建](#block-process-creations-originating-from-psexec-and-wmi-commands) | Y |   |   |  Y | Y  |
|[阻止从 USB 运行的不受信任和未签名的进程](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Y |   |Y <br><br> CB 1802  | Y  | Y  |
|[阻止来自Office宏的 Win32 API 调用](#block-win32-api-calls-from-office-macros) | Y |   | Y <br><br> CB 1710  | Y  |  Y |
|[对勒索软件使用高级保护](#use-advanced-protection-against-ransomware) | Y |   | Y <br><br> CB 1802 | Y  | Y  |
|  |  |  |  |  |  |

   (<a id="fn1">1</a>) 可以使用任何规则的 GUID 按规则配置攻击面减少规则。

- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)
- [System Center Configuration Manager (SCCM) CB 1710](/configmgr/core/servers/manage/updates) <br>_SCCM 现已Microsoft Endpoint Configuration Manager。_

## <a name="per-rule-alert-and-notification-details"></a>每个规则警报和通知详细信息

为阻止模式下的所有规则生成 Toast 通知。 任何其他模式下的规则都不会生成 Toast 通知

对于指定了"规则状态"的规则：

- 包含组合的 ASR 规则\<ASR Rule, Rule State\>用于显示警报 (仅针对高云块级别的设备) Microsoft Defender for Endpoint上的 toast 通知。 不在高云块级别的设备不会为任何<ASR 规则、规则状态>组合生成警报
- EDR警报针对指定状态下的 ASR 规则生成，但仅针对云块级别较高的设备生成。

| 规则名称： | 规则状态： | 在EDR中生成警报？ <br>  (是&nbsp;\|&nbsp;无)  | 生成 Toast 通知？ <br>  (是&nbsp;\|&nbsp;无)  |
|---|:---:|:---:|:---:|
|   |   |  _仅适用于高云块级别的设备_ | _仅在阻止模式下_ |
|[阻止滥用被利用的易受攻击的签名驱动程序](#block-abuse-of-exploited-vulnerable-signed-drivers) |   | N  | Y |
|[阻止 Adobe Reader 创建子进程](#block-adobe-reader-from-creating-child-processes) | 阻止  | Y <br> 需要高云块级别的设备  | Y <br> 需要高云块级别的设备 |
|[阻止所有Office应用程序创建子进程](#block-all-office-applications-from-creating-child-processes) |   | N | Y |
|[阻止从Windows本地安全机构子系统 (lsass.exe) 窃取凭据](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) |   | N | Y |
|[阻止电子邮件客户端和 Webmail 中的可执行内容](#block-executable-content-from-email-client-and-webmail) |   | Y <br> 需要高云块级别的设备 | Y <br> 需要高云块级别的设备 |
|[阻止可执行文件运行，除非它们满足普遍性、年龄或受信任的列表条件](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) |   | N | Y |
|[阻止执行可能混淆的脚本](#block-execution-of-potentially-obfuscated-scripts) |  AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 需要高云块级别的设备  | N \| Y <br> 需要高云块级别的设备 |
|[阻止 JavaScript 或 VBScript 启动下载的可执行内容](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | 阻止 | Y <br> 需要高云块级别的设备  | Y <br> 需要高云块级别的设备 |
|[阻止Office应用程序创建可执行内容](#block-office-applications-from-creating-executable-content) |   | N | Y |
|[阻止Office应用程序将代码注入其他进程](#block-office-applications-from-injecting-code-into-other-processes)  |   | N | Y |
|[阻止Office通信应用程序创建子进程](#block-office-communication-application-from-creating-child-processes) |  |  N | Y |
|[通过 WMI 事件订阅阻止持久性](#block-persistence-through-wmi-event-subscription) |  AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 需要高云块级别的设备  | N \| Y <br> 需要高云块级别的设备 |
|[阻止源自 PSExec 和 WMI 命令的进程创建](#block-process-creations-originating-from-psexec-and-wmi-commands) |   | N | Y |
|[阻止从 USB 运行的不受信任和未签名的进程](#block-untrusted-and-unsigned-processes-that-run-from-usb) | AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 需要高云块级别的设备  | N \| Y <br> 需要高云块级别的设备 |
|[阻止来自Office宏的 Win32 API 调用](#block-win32-api-calls-from-office-macros) |   | N | Y |
|[对勒索软件使用高级保护](#use-advanced-protection-against-ransomware) | AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 需要高云块级别的设备  | N \| Y <br> 需要高云块级别的设备 |
|   |   |   |   |
  
## <a name="asr-rules-and-guids-matrix"></a>ASR 规则和 GUID 矩阵

| 规则名称 | 规则 GUID |
|:-----|:-----|
| 阻止滥用被利用的易受攻击的签名驱动程序 | 56a863a9-875e-4185-98a7-b882c64b5ce5 |
| 阻止 Adobe Reader 创建子进程 | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c |
| 阻止所有Office应用程序创建子进程 | d4f940ab-401b-4efc-aadc-ad5f3c50688a |
| 阻止从Windows本地安全机构子系统 (lsass.exe) 窃取凭据 | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 |
| 阻止电子邮件客户端和 Webmail 中的可执行内容 | be9ba2d9-53ea-4cdc-84e5-9b1eeee46550 |
| 阻止可执行文件运行，除非它们满足普遍性、年龄或受信任的列表条件 | 01443614-cd74-433a-b99e-2ecdc07bfc25 |
| 阻止执行可能混淆的脚本 | 5beb7efe-fd9a-4556-801d-275e5ffc04cc |
| 阻止 JavaScript 或 VBScript 启动下载的可执行内容 | d3e037e1-3eb8-44c8-a917-57927947596d |
| 阻止Office应用程序创建可执行内容 | 3b576869-a4ec-4529-8536-b80a7769e899 |
| 阻止Office应用程序将代码注入其他进程 | 75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84 |
| 阻止Office通信应用程序创建子进程 | 26190899-1602-49e8-8b27-eb1d0a1ce869 |
| 通过 WMI 事件订阅阻止持久性 <br>* 不支持文件和文件夹排除项。 | e6db77e5-3df2-4cf1-b95a-636979351e5b |
| 阻止源自 PSExec 和 WMI 命令的进程创建 | d1e49aac-8f56-4280-b9ba-993a6d77406c |
| 阻止从 USB 运行的不受信任和未签名的进程 | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4 |
| 阻止来自Office宏的 Win32 API 调用 | 92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b |
| 对勒索软件使用高级保护 | c1db55ab-c21a-4637-bb3f-a12568109d35 |

## <a name="asr-rule-modes"></a>ASR 规则模式

- **未配置** 或 **禁用**：这是未启用或已禁用 ASR 规则的状态。 此状态的代码 = 0。
- **阻止**：这是启用 ASR 规则的状态。 此状态的代码为 1。
- **审核**：这是评估 ASR 规则对部署它的组织或环境的影响行为的状态。 此状态的代码为 2。
- **警告** 这是启用 ASR 规则并向最终用户显示通知的状态，但允许最终用户绕过该块。 此状态的代码为 6。

_警告模式_ 是一种块模式类型，向用户发出潜在风险操作的警报。 用户可以选择绕过阻止警告消息并允许基础操作。 用户可以通过块时生成的最终用户弹出 toast 通知选择 **"确定** "来强制执行该块，或选择旁路选项" **取消阻止** "。 取消阻止警告后，允许操作直到下一次发生警告消息，此时最终用户将需要重新格式化操作。

如果单击允许按钮，则该块将被抑制 24 小时。 24 小时后，最终用户需要再次允许该块。 ASR 规则的警告模式仅支持 RS5+ (1809+) 设备。 如果在具有较旧版本的设备上将旁路分配给 ASR 规则，则规则将处于阻止模式。

还可以通过 PowerShell 在警告模式下设置规则，只需将AttackSurfaceReductionRules_Actions指定为"Warn"。 例如：

```powershell
-command "& {&'Add-MpPreference' -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Warn"} 
```

## <a name="per-rule-descriptions"></a>按规则说明

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>阻止滥用被利用的易受攻击的签名驱动程序

此规则阻止应用程序将易受攻击的签名驱动程序写入磁盘。 具有 _足够权_\-限以获得内核访问权限的本地应用程序\-可以利用处于疯狂状态、易受攻击的签名驱动程序。 易受攻击的签名驱动程序使攻击者能够禁用或规避安全解决方案，最终导致系统入侵。

**阻止滥用受攻击的易受攻击的签名驱动程序** 规则不会阻止系统上已有的驱动程序被加载。

> [!NOTE]
>
> 可以使用 MEM OMA-URI 配置此规则。 有关配置自定义规则，请参阅 [MEM OMA-URI](enable-attack-surface-reduction.md#mem) 。
>
> 还可以使用 [PowerShell](enable-attack-surface-reduction.md#powershell) 配置此规则。
>
> 若要检查驱动程序，请使用此网站 [提交驱动程序进行分析](https://www.microsoft.com/en-us/wdsi/driversubmission)。

<!--The above link is the 'only link' that exists for having drivers examined. The 'en-us' component is required to make the link work. Any alterations to this link will result in a 404.
-->

Intune名称： `Block abuse of exploited vulnerable signed drivers` (尚不可用) 

Configuration Manager名称：尚不可用
  
GUID：  `56a863a9-875e-4185-98a7-b882c64b5ce5`

<!-- Hide this intro with no subsequent list items
Advanced hunting action type:
-->

<!-- 
Dependencies: none provided by engineering
-->

### <a name="block-adobe-reader-from-creating-child-processes"></a>阻止 Adobe Reader 创建子进程

此规则通过阻止 Adobe Reader 创建进程来防止攻击。

通过社会工程或攻击，恶意软件可以下载和启动有效负载，并打破 Adobe Reader。 通过阻止 Adobe Reader 生成子进程，无法将试图将其用作向量的恶意软件传播。

Intune名称：`Process creation from Adobe Reader (beta)`

Configuration Manager名称：尚不可用

GUID：`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

高级搜寻操作类型：

- AsrAdobeReaderChildProcessAudited
- AsrAdobeReaderChildProcessBlocked

依赖项：MDAV

### <a name="block-all-office-applications-from-creating-child-processes"></a>阻止所有Office应用程序创建子进程

此规则阻止Office应用创建子进程。 Office应用包括 Word、Excel、PowerPoint、OneNote 和 Access。

创建恶意子进程是一种常见的恶意软件策略。 滥用Office作为向量的恶意软件通常运行 VBA 宏并利用代码下载并尝试运行更多有效负载。 但是，一些合法的业务线应用程序也可能出于良性目的生成子进程：例如生成命令提示符或使用 PowerShell 配置注册表设置。

Intune名称：`Office apps launching child processes`

Configuration Manager名称：`Block Office application from creating child processes`

GUID：`d4f940ab-401b-4efc-aadc-ad5f3c50688a`

高级搜寻操作类型：

- AsrOfficeChildProcessAudited
- AsrOfficeChildProcessBlocked

依赖项：MDAV

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>阻止从Windows本地安全机构子系统窃取凭据

此规则通过锁定本地安全机构子系统服务 (LSASS) 来帮助防止凭据窃取。

LSASS 对登录Windows计算机的用户进行身份验证。 Windows中的 Microsoft Defender Credential Guard 通常会阻止尝试从 LSASS 提取凭据。 但是，由于自定义智能卡驱动程序或其他程序加载到本地安全机构 (LSA) 的兼容性问题，某些组织无法在其所有计算机上启用 Credential Guard。 在这些情况下，攻击者可以使用 Mimikatz 等黑客工具从 LSASS 中刮取明文密码和 NTLM 哈希。

> [!NOTE]
> 在某些应用中，代码枚举所有正在运行的进程，并尝试使用详尽的权限打开它们。 此规则拒绝应用的进程打开操作，并将详细信息记录到安全事件日志。 此规则可能会产生很多噪音。 如果应用只是枚举 LSASS，但对功能没有实际影响，则无需将其添加到排除列表。 此事件日志条目本身并不一定表示恶意威胁。
  
> [!IMPORTANT]
> 攻击面减少 (ASR) 规则"阻止从Windows本地安全机构子系统中窃取凭据 (lsass.exe) "的默认状态将从 **"未配置**"更改为 **"已配置"**，默认模式设置为 **"阻止**"。 所有其他 ASR 规则将保持其默认状态： **未配置**。 规则中已合并了其他筛选逻辑，以减少最终用户通知。 客户可以将规则配置为 **审核**、 **警告** 或 **禁用** 模式，这将覆盖默认模式。 无论规则是在默认模式下配置的，还是手动启用阻止模式，此规则的功能都是相同的。

Intune名称：`Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager名称：`Block credential stealing from the Windows local security authority subsystem`

GUID：`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

高级搜寻操作类型：

- AsrLsassCredentialTheftAudited
- AsrLsassCredentialTheftBlocked

依赖项：MDAV

### <a name="block-executable-content-from-email-client-and-webmail"></a>阻止电子邮件客户端和 Webmail 中的可执行内容

此规则阻止以下文件类型从 Microsoft Outlook 应用程序或 Outlook.com 和其他常用 Web 邮件提供商中打开的电子邮件启动：

- 可执行文件 (，例如.exe、.dll或 .scr) 
- 脚本文件 (如 PowerShell .ps、Visual Basic .vbs 或 JavaScript .js文件) 

Intune名称：`Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager名称：`Block executable content from email client and webmail`

GUID：`be9ba2d9-53ea-4cdc-84e5-9b1eeee46550`

高级搜寻操作类型：

- AsrExecutableEmailContentAudited
- AsrExecutableEmailContentBlocked

依赖项：MDAV

> [!NOTE]
> 规则 **阻止电子邮件客户端和 Webmail 中的可执行内容** 具有以下替代说明，具体取决于你使用的应用程序：
>
> - Intune (配置文件) ：执行可执行内容 (exe、dll、ps、js、vb 等，) 从电子邮件 (webmail/mail 客户端删除)  () 例外。
> - Endpoint Manager：阻止从电子邮件和 Webmail 客户端下载可执行内容。
> - 组策略：阻止电子邮件客户端和 Webmail 中的可执行内容。

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>阻止可执行文件运行，除非它们满足普遍性、年龄或受信任的列表条件

此规则阻止可执行文件（如 .exe、.dll 或 .scr）启动。 因此，启动不受信任或未知的可执行文件可能会有风险，因为最初可能不清楚这些文件是否为恶意文件。

> [!IMPORTANT]
> 必须 [启用云传递的保护](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 才能使用此规则。
>
> **规则阻止可执行文件运行，除非它们满足具有 GUID 的普遍性、年龄或受信任的列表条件**，该条件由 Microsoft 拥有，并且管理员未指定这些文件。`01443614-cd74-433a-b99e-2ecdc07bfc25` 此规则使用云提供的保护定期更新其受信任的列表。
>
> 可以使用文件夹路径或完全限定的资源名称 (指定单个文件或文件夹) 但不能指定适用于哪些规则或排除项。

Intune名称：`Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager名称：`Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID：`01443614-cd74-433a-b99e-2ecdc07bfc25`

高级搜寻操作类型：

- AsrUntrustedExecutableAudited
- AsrUntrustedExecutableBlocked

依赖项：MDAV、云保护

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>阻止执行可能混淆的脚本

此规则检测模糊脚本中的可疑属性。

脚本混淆是恶意软件作者和合法应用程序用来隐藏知识产权或减少脚本加载时间的常见技术。 恶意软件作者还使用混淆使恶意代码更难读取，从而防止人类和安全软件的密切审查。

Intune名称：`Obfuscated js/vbs/ps/macro code`

Configuration Manager名称：`Block execution of potentially obfuscated scripts`

GUID：`5beb7efe-fd9a-4556-801d-275e5ffc04cc`

高级搜寻操作类型：

- AsrObfuscatedScriptAudited
- AsrObfuscatedScriptBlocked

依赖项：MDAV、AMSI

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>阻止 JavaScript 或 VBScript 启动下载的可执行内容

此规则阻止脚本启动可能恶意下载的内容。 使用 JavaScript 或 VBScript 编写的恶意软件通常充当从 Internet 提取和启动其他恶意软件的下载程序。

虽然不常见，但业务线应用程序有时使用脚本来下载和启动安装程序。

Intune名称：`js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager名称：`Block JavaScript or VBScript from launching downloaded executable content`

GUID：`d3e037e1-3eb8-44c8-a917-57927947596d`

高级搜寻操作类型：

- AsrScriptExecutableDownloadAudited
- AsrScriptExecutableDownloadBlocked

依赖项：MDAV、AMSI

### <a name="block-office-applications-from-creating-executable-content"></a>阻止Office应用程序创建可执行内容

此规则阻止将恶意代码写入磁盘，从而阻止Office应用（包括 Word、Excel 和 PowerPoint）创建潜在的恶意可执行内容。

滥用Office作为向量的恶意软件可能会尝试中断Office并将恶意组件保存到磁盘。 这些恶意组件会在计算机重启后生存下来，并保留在系统上。 因此，此规则可以防御常见的持久性技术。

Intune名称：`Office apps/macros creating executable content`

SCCM 名称： `Block Office applications from creating executable content`

GUID：`3b576869-a4ec-4529-8536-b80a7769e899`

高级搜寻操作类型：

- AsrExecutableOfficeContentAudited
- AsrExecutableOfficeContentBlocked

依赖项：MDAV、RPC

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>阻止Office应用程序将代码注入其他进程

此规则阻止从Office应用到其他进程的代码注入尝试。

攻击者可能会尝试使用Office应用通过代码注入将恶意代码迁移到其他进程，以便代码可以伪装成一个干净的过程。

没有用于使用代码注入的已知合法业务目的。

此规则适用于 Word、Excel 和 PowerPoint。

Intune名称：`Office apps injecting code into other processes (no exceptions)`

Configuration Manager名称：`Block Office applications from injecting code into other processes`

GUID：`75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84`

高级搜寻操作类型：

- AsrOfficeProcessInjectionAudited
- AsrOfficeProcessInjectionBlocked

依赖项：MDAV

### <a name="block-office-communication-application-from-creating-child-processes"></a>阻止Office通信应用程序创建子进程

此规则阻止Outlook创建子进程，同时仍允许合法Outlook函数。

此规则可防范社会工程攻击，防止利用代码滥用Outlook中的漏洞。 它还可防止攻击者在用户凭据遭到入侵时可以使用的[Outlook规则和表单攻击](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)。

> [!NOTE]
> 此规则在Outlook中阻止 DLP 策略提示和工具提示。 此规则仅适用于 Outlook 和 Outlook.com。

Intune名称：`Process creation from Office communication products (beta)`

Configuration Manager名称：不可用

GUID：`26190899-1602-49e8-8b27-eb1d0a1ce869`

高级搜寻操作类型：

- AsrOfficeCommAppChildProcessAudited
- AsrOfficeCommAppChildProcessBlocked

依赖项：MDAV

### <a name="block-persistence-through-wmi-event-subscription"></a>通过 WMI 事件订阅阻止持久性

此规则可防止恶意软件滥用 WMI 来达到设备上的持久性。

> [!IMPORTANT]
> 文件和文件夹排除项不适用于此攻击面减少规则。

无文件威胁使用各种策略来保持隐藏状态，以避免在文件系统中被看到，并获得定期执行控制。 某些威胁可能会滥用 WMI 存储库和事件模型，使其保持隐藏状态。

Intune名称：不可用

Configuration Manager名称：不可用

GUID：`e6db77e5-3df2-4cf1-b95a-636979351e5b`

高级搜寻操作类型：

- AsrPersistenceThroughWmiAudited
- AsrPersistenceThroughWmiBlocked

依赖项：MDAV、RPC

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>阻止源自 PSExec 和 WMI 命令的进程创建

此规则阻止通过 [PsExec](/sysinternals/downloads/psexec) 和 [WMI](/windows/win32/wmisdk/about-wmi) 创建的进程运行。 PsExec 和 WMI 都可以远程执行代码，因此存在恶意软件出于命令和控制目的滥用此功能的风险，或者在整个组织的网络中传播感染。

> [!WARNING]
> 仅当使用[Intune](/intune)或其他 MDM 解决方案管理设备时，才使用此规则。 此规则与通过[Microsoft Endpoint Configuration Manager](/configmgr)的管理不兼容，因为此规则阻止客户端用来正常运行Configuration Manager WMI 命令。

Intune名称：`Process creation from PSExec and WMI commands`

Configuration Manager名称：不适用

GUID：`d1e49aac-8f56-4280-b9ba-993a6d77406c`

高级搜寻操作类型：

- AsrPsexecWmiChildProcessAudited
- AsrPsexecWmiChildProcessBlocked

依赖项：MDAV

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>阻止从 USB 运行的不受信任和未签名的进程

使用此规则，管理员可以防止未签名或不受信任的可执行文件从 USB 可移动驱动器（包括 SD 卡）运行。 阻止的文件类型包括可执行文件 (，例如.exe、.dll或 .scr) 

Intune名称：`Untrusted and unsigned processes that run from USB`

Configuration Manager名称：`Block untrusted and unsigned processes that run from USB`

GUID：`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

高级搜寻操作类型：

- AsrUntrustedUsbProcessAudited
- AsrUntrustedUsbProcessBlocked

依赖项：MDAV

### <a name="block-win32-api-calls-from-office-macros"></a>阻止来自Office宏的 Win32 API 调用

此规则阻止 VBA 宏调用 Win32 API。

Office VBA 启用 Win32 API 调用。 恶意软件可能会滥用此功能，例如 [调用 Win32 API 以启动恶意 shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) ，而无需将任何内容直接写入磁盘。 大多数组织不依赖于在日常运行中调用 Win32 API 的能力，即使他们以其他方式使用宏。

支持的操作系统：

- [Windows 10版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows服务器版本 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune名称：`Win32 imports from Office macro code`

Configuration Manager名称：`Block Win32 API calls from Office macros`

GUID：`92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b`

高级搜寻操作类型：

- AsrOfficeMacroWin32ApiCallsAudited
- AsrOfficeMacroWin32ApiCallsBlocked

依赖项：MDAV、AMSI

### <a name="use-advanced-protection-against-ransomware"></a>对勒索软件使用高级保护

此规则提供针对勒索软件的额外保护层。 它使用客户端和云启发式来确定文件是否类似于勒索软件。 此规则不会阻止具有以下一个或多个特征的文件：

- 此文件已在 Microsoft 云中发现是无和谐的。
- 该文件是有效的已签名文件。
- 该文件非常普遍，不能被视为勒索软件。

为了防止勒索软件，规则往往会出现问题。

> [!NOTE]
> 必须 [启用云传递的保护](enable-cloud-protection-microsoft-defender-antivirus.md) 才能使用此规则。

Intune名称：`Advanced ransomware protection`

Configuration Manager名称：`Use advanced protection against ransomware`

GUID：`c1db55ab-c21a-4637-bb3f-a12568109d35`

高级搜寻操作类型：

- AsrRansomwareAudited
- AsrRansomwareBlocked

依赖项：MDAV、云保护
