---
title: 攻击面减少规则参考
description: 列出每个规则关于攻击面减少规则的详细信息。
keywords: 攻击面减少规则， ASR， asr 规则， hips， 主机入侵防护系统， 保护规则， 反攻击规则， 攻击规则， 感染防护规则， Microsoft Defender for Endpoint， 配置 ASR 规则， ASR 规则说明
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
ms.openlocfilehash: 377ae12eb2436dcafe84e521fd4b35d712283e74
ms.sourcegitcommit: 7aa2441c1f2cc5b4b5495d6fdb993e563f86647f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64637975"
---
# <a name="attack-surface-reduction-rules-reference"></a>攻击面减少规则参考

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

本文提供有关攻击减少规则的信息：

- [支持的操作系统版本](#supported-operating-systems)
- [支持的配置管理系统](#supported-configuration-management-systems)
- [每规则通知和通知详细信息](#per-rule-alert-and-notification-details)
- [ASR 规则和 GUID 矩阵](#asr-rules-and-guids-matrix)
- [ASR 规则模式](#asr-rule-modes)
- [每规则说明](#per-rule-descriptions)
  - 规则说明
  - 配置管理系统规则名称

## <a name="public-preview-supported-operating-systems"></a>公共预览版：支持的操作系统

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

下表列出了当前已预发布产品的受支持攻击面减少规则的操作系统。 规则按字母顺序列出。 除非另有说明，否则最低 Windows&nbsp; 10 内部版本为版本 1709 (RS3，内部版本 16299) 或更高版本;最低 Windows&nbsp; Server 内部版本为版本 1809 或更高版本。

> [!NOTE]
> Windows&nbsp; Server2012R2&nbsp;&nbsp; 和 Windows&nbsp; Server2016&nbsp; 中的攻击面减少规则适用于使用新式统一解决方案包载入的设备。 有关详细信息，请参阅适用于 [Windows Server 2012 R2 和 2016 Preview](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview) 的新式统一解决方案中的新功能。
>

| 规则名称 | &nbsp;Windows Server 2016 <sup>[[1](#fn1)]<sup></sup> | &nbsp;Windows Server 2012 R2 <sup>[[1](#fn1)]<sup></sup> |
|---|:---:|:---:|
|[阻止滥用被攻击的易受攻击的已签名驱动程序](#block-abuse-of-exploited-vulnerable-signed-drivers) | Y | Y |
|[阻止 Adobe Reader 创建子进程](#block-adobe-reader-from-creating-child-processes) | Y | Y |
|[阻止所有Office应用程序创建子进程](#block-all-office-applications-from-creating-child-processes) | Y | Y |
|[阻止从本地安全Windows (lsass.exe) ](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Y | Y |
|[阻止来自电子邮件客户端和 Webmail 的可执行内容](#block-executable-content-from-email-client-and-webmail) | Y | Y |
|[阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Y | Y |
|[阻止执行可能混淆的脚本](#block-execution-of-potentially-obfuscated-scripts) | Y | Y |
|[阻止 JavaScript 或 VBScript 启动下载的可执行内容](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | N | N |
|[阻止Office应用程序创建可执行内容](#block-office-applications-from-creating-executable-content) | Y | Y |
|[阻止Office将代码注入其他进程](#block-office-applications-from-injecting-code-into-other-processes)  | Y | Y |
|[阻止Office应用程序创建子进程](#block-office-communication-application-from-creating-child-processes) | Y | Y |
|[通过 WMI 事件订阅阻止持久性](#block-persistence-through-wmi-event-subscription) \*_不支持文件和文件夹排除项。_ | N | N |
|[阻止源自 PSExec 和 WMI 命令的进程创建](#block-process-creations-originating-from-psexec-and-wmi-commands) | Y | Y |
|[阻止从 USB 运行的不受信任的和未签名的进程](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Y | Y |
|[阻止从宏Office Win32 API 调用](#block-win32-api-calls-from-office-macros) | N | N |
|[使用高级防护抵御勒索软件](#use-advanced-protection-against-ransomware) | Y | Y |
|  |  |  |

 (<a id="fn1">1</a>) 2016 的新式统一Windows Server 2012解决方案。 有关详细信息，请参阅将 [Windows 服务器载入到 Defender for Endpoint 服务](configure-server-endpoints.md)。

_结束公共预览版：支持的操作系统_

## <a name="supported-operating-systems"></a>支持的操作系统 

下表列出了当前公开发布的规则的受支持操作系统。 规则按字母顺序列出。

> [!Note]
>
> 除非另有说明，否则最低 Windows&nbsp; 10 内部版本为版本 1709 (RS3，内部版本 16299) 或更高版本;最低 Windows&nbsp; Server 内部版本为版本 1809 或更高版本。
>

|规则名称|&nbsp;Windows 10|&nbsp;Windows Server 2019|&nbsp;Windows Server|
|---|:---:|:---:|:---:|
|[阻止滥用被攻击的易受攻击的已签名驱动程序](#block-abuse-of-exploited-vulnerable-signed-drivers) | Y | Y | Y <br><br> 版本 1803 (半年频道) 或更高版本 |
|[阻止 Adobe Reader 创建子进程](#block-adobe-reader-from-creating-child-processes) | Y 版本 1809 或更高版本 | Y | Y  <br><br> |
|[阻止所有Office应用程序创建子进程](#block-all-office-applications-from-creating-child-processes) | Y | Y | Y <br><br> |
|[阻止从本地安全Windows (lsass.exe) ](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Y 版本 1803 或更高版本 | Y <br><br> | Y <br><br> |
|[阻止来自电子邮件客户端和 Webmail 的可执行内容](#block-executable-content-from-email-client-and-webmail) | Y | Y <br><br> | Y <br><br> |
|[阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Y 版本 1803 或更高版本 | Y <br><br> | Y <br><br> |
|[阻止执行可能混淆的脚本](#block-execution-of-potentially-obfuscated-scripts) | Y | Y <br><br> | Y <br><br> |
|[阻止 JavaScript 或 VBScript 启动下载的可执行内容](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | Y | Y <br><br> | Y <br><br> |
|[阻止Office应用程序创建可执行内容](#block-office-applications-from-creating-executable-content) | Y | Y <br><br> | Y <br><br> |
|[阻止Office将代码注入其他进程](#block-office-applications-from-injecting-code-into-other-processes)  | Y | Y <br><br> | Y <br><br> |
|[阻止Office应用程序创建子进程](#block-office-communication-application-from-creating-child-processes) | Y | Y <br><br> | Y <br><br> |
|[通过 WMI 事件订阅阻止持久性](#block-persistence-through-wmi-event-subscription) <br><br> \*_不支持文件和文件夹排除项。_ | Y 版本 1903 (版本 18362) 或更高版本| Y | Y <br><br> 版本 1903 (版本 18362) 或更高版本 |
|[阻止源自 PSExec 和 WMI 命令的进程创建](#block-process-creations-originating-from-psexec-and-wmi-commands) | Y 版本 1803 或更高版本 | Y <br><br> | Y <br><br>  |
|[阻止从 USB 运行的不受信任的和未签名的进程](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Y | Y <br><br> | Y <br><br> |
|[阻止从宏Office Win32 API 调用](#block-win32-api-calls-from-office-macros) | Y | Y <br><br> | Y <br><br> |
|[使用高级防护抵御勒索软件](#use-advanced-protection-against-ransomware) | Y 版本 1803 或更高版本 | Y <br><br> | Y <br><br> |
|  |  |  |  |

## <a name="supported-configuration-management-systems"></a>支持的配置管理系统

下表列出了有关此表中引用的配置管理系统版本的信息的链接。

|规则名称 | Intune | Microsoft Endpoint Manager |Microsoft Endpoint Configuration Manager |<sup>组策略[[1](#fn1)]<sup></sup> | PowerShell<sup>[[1](#fn1)]<sup></sup>  |
|---|:---:|:---:|:---:|:---:|:---:|
|[阻止滥用被攻击的易受攻击的已签名驱动程序](#block-abuse-of-exploited-vulnerable-signed-drivers) | Y  | Y MEM OMA-URI |   | Y  |  Y  |
|[阻止 Adobe Reader 创建子进程](#block-adobe-reader-from-creating-child-processes) | Y |   |  | Y  | Y  |
|[阻止所有Office应用程序创建子进程](#block-all-office-applications-from-creating-child-processes) | Y |   |Y <br><br> CB 1710 | Y  | Y  |
|[阻止从本地安全Windows (lsass.exe) ](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Y  |   | Y <br><br>CB 1802 | Y  | Y  |
|[阻止来自电子邮件客户端和 Webmail 的可执行内容](#block-executable-content-from-email-client-and-webmail) | Y |  |Y <br><br> CB 1710 | Y | Y  |
|[阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Y |   | Y <br><br> CB 1802 |  Y |  Y |
|[阻止执行可能混淆的脚本](#block-execution-of-potentially-obfuscated-scripts) | Y |   |  Y  <br><br> CB 1710 | Y  | Y  |
|[阻止 JavaScript 或 VBScript 启动下载的可执行内容](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | Y |   | Y <br><br> CB 1710 | Y  | Y  |
|[阻止Office应用程序创建可执行内容](#block-office-applications-from-creating-executable-content) | Y |  |Y <br><br> CB 1710 | Y  | Y  |
|[阻止Office将代码注入其他进程](#block-office-applications-from-injecting-code-into-other-processes) | Y |  | Y <br><br> CB 1710 | Y  | Y  |
|[阻止Office应用程序创建子进程](#block-office-communication-application-from-creating-child-processes) | Y |  |Y <br><br> CB 1710 | Y  | Y  |
|[通过 WMI 事件订阅阻止持久性](#block-persistence-through-wmi-event-subscription) |  |  |  |Y   | Y  |
|[阻止源自 PSExec 和 WMI 命令的进程创建](#block-process-creations-originating-from-psexec-and-wmi-commands) | Y |   |   |  Y | Y  |
|[阻止从 USB 运行的不受信任的和未签名的进程](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Y |   |Y <br><br> CB 1802  | Y  | Y  |
|[阻止从宏Office Win32 API 调用](#block-win32-api-calls-from-office-macros) | Y |   | Y <br><br> CB 1710  | Y  |  Y |
|[使用高级防护抵御勒索软件](#use-advanced-protection-against-ransomware) | Y |   | Y <br><br> CB 1802 | Y  | Y  |
|  |  |  |  |  |  |

   (<a id="fn1">1</a>) 可以使用任何规则的 GUID 基于每个规则配置攻击面减少规则。

- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)
- [System Center Configuration Manager (SCCM) CB 1710](/configmgr/core/servers/manage/updates) <br>_SCCM 现已Microsoft Endpoint Configuration Manager。_

## <a name="per-rule-alert-and-notification-details"></a>每个规则通知和通知详细信息

在阻止模式下为所有规则生成 Toast 通知。 任何其他模式下的规则不会生成 Toast 通知

对于指定了"规则状态"的规则：

- ASR 规则\<ASR Rule, Rule State\>与组合一起用于显示警报 (toast 通知) Microsoft Defender for Endpoint仅针对高云阻止级别的设备。 未处于高云阻止级别的设备不会生成任何 ASR 规则<规则状态或>警报
- EDR为处于指定状态（但仅适用于高云阻止级别的设备）的 ASR 规则生成通知。

| 规则名称： | 规则状态： | 在警报中生成EDR？ <br>  (是&nbsp;\|&nbsp;无)  | 生成 Toast 通知 <br>  (是&nbsp;\|&nbsp;无)  |
|---|:---:|:---:|:---:|
|   |   |  _仅适用于高云阻止级别的设备_ | _仅在阻止模式下_ |
|[阻止滥用被攻击的易受攻击的已签名驱动程序](#block-abuse-of-exploited-vulnerable-signed-drivers) |   | N  | Y |
|[阻止 Adobe Reader 创建子进程](#block-adobe-reader-from-creating-child-processes) | 阻止  | Y <br> 需要处于高云阻止级别的设备  | Y <br> 需要处于高云阻止级别的设备 |
|[阻止所有Office应用程序创建子进程](#block-all-office-applications-from-creating-child-processes) |   | N | Y |
|[阻止从本地安全Windows (lsass.exe) ](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) |   | N | Y |
|[阻止来自电子邮件客户端和 Webmail 的可执行内容](#block-executable-content-from-email-client-and-webmail) |   | Y <br> 需要处于高云阻止级别的设备 | Y <br> 需要处于高云阻止级别的设备 |
|[阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) |   | N | Y |
|[阻止执行可能混淆的脚本](#block-execution-of-potentially-obfuscated-scripts) |  AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 需要处于高云阻止级别的设备  | N \| Y <br> 需要处于高云阻止级别的设备 |
|[阻止 JavaScript 或 VBScript 启动下载的可执行内容](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | 阻止 | Y <br> 需要处于高云阻止级别的设备  | Y <br> 需要处于高云阻止级别的设备 |
|[阻止Office应用程序创建可执行内容](#block-office-applications-from-creating-executable-content) |   | N | Y |
|[阻止Office将代码注入其他进程](#block-office-applications-from-injecting-code-into-other-processes)  |   | N | Y |
|[阻止Office应用程序创建子进程](#block-office-communication-application-from-creating-child-processes) |  |  N | Y |
|[通过 WMI 事件订阅阻止持久性](#block-persistence-through-wmi-event-subscription) |  AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 需要处于高云阻止级别的设备  | N \| Y <br> 需要处于高云阻止级别的设备 |
|[阻止源自 PSExec 和 WMI 命令的进程创建](#block-process-creations-originating-from-psexec-and-wmi-commands) |   | N | Y |
|[阻止从 USB 运行的不受信任的和未签名的进程](#block-untrusted-and-unsigned-processes-that-run-from-usb) | AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 需要处于高云阻止级别的设备  | N \| Y <br> 需要处于高云阻止级别的设备 |
|[阻止从宏Office Win32 API 调用](#block-win32-api-calls-from-office-macros) |   | N | Y |
|[使用高级防护抵御勒索软件](#use-advanced-protection-against-ransomware) | AuditBlock&nbsp;\|&nbsp; | Y \| Y <br> 需要处于高云阻止级别的设备  | N \| Y <br> 需要处于高云阻止级别的设备 |
|   |   |   |   |
  
## <a name="asr-rules-and-guids-matrix"></a>ASR 规则和 GUID 矩阵

| 规则名称 | 规则 GUID |
|:-----|:-----|
| 阻止滥用被攻击的易受攻击的已签名驱动程序 | 56a863a9-875e-4185-98a7-b882c64b5ce5 |
| 阻止 Adobe Reader 创建子进程 | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c |
| 阻止所有Office应用程序创建子进程 | d4f940ab-401b-4efc-aadc-ad5f3c50688a |
| 阻止从本地安全Windows (lsass.exe)  | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 |
| 阻止来自电子邮件客户端和 Webmail 的可执行内容 | be9ba2d9-53ea-4cdc-84e5-9b1eeee46550 |
| 阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件 | 01443614-cd74-433a-b99e-2ecdc07bfc25 |
| 阻止执行可能混淆的脚本 | 5beb7efe-fd9a-4556-801d-275e5ffc04cc |
| 阻止 JavaScript 或 VBScript 启动下载的可执行内容 | d3e037e1-3eb8-44c8-a917-57927947596d |
| 阻止Office应用程序创建可执行内容 | 3b576869-a4ec-4529-8536-b80a7769e899 |
| 阻止Office将代码注入其他进程 | 75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84 |
| 阻止Office应用程序创建子进程 | 26190899-1602-49e8-8b27-eb1d0a1ce869 |
| 通过 WMI 事件订阅阻止持久性 <br>* 不支持文件和文件夹排除项。 | e6db77e5-3df2-4cf1-b95a-636979351e5b |
| 阻止源自 PSExec 和 WMI 命令的进程创建 | d1e49aac-8f56-4280-b9ba-993a6d77406c |
| 阻止从 USB 运行的不受信任的和未签名的进程 | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4 |
| 阻止从宏Office Win32 API 调用 | 92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b |
| 使用高级防护抵御勒索软件 | c1db55ab-c21a-4637-bb3f-a12568109d35 |

## <a name="asr-rule-modes"></a>ASR 规则模式

- **未配置** 或 **禁用**：这是未启用或已禁用 ASR 规则的状态。 此状态的代码 = 0。
- **Block**：这是启用 ASR 规则的状态。 此状态的代码为 1。
- **审核**：这是评估 ASR 规则对部署它的组织或环境的影响行为的状态。 此状态的代码为 2。
- **Warn** 这是启用 ASR 规则并通知最终用户但允许最终用户绕过阻止的状态。 此状态的代码为 6。

_警告模式_ 是一种阻止模式类型，可提醒用户存在潜在危险的操作。 用户可以选择绕过阻止警告消息并允许基础操作。 用户可以选择 **"确定**"以强制执行阻止，或者通过阻止时生成的最终用户  弹出 Toast 通知选择绕过选项-取消阻止。 取消阻止警告后，将允许该操作，直到下次出现警告消息，此时最终用户将需要重新执行该操作。

如果单击允许按钮，阻止将隐藏 24 小时。 24 小时后，最终用户将需要再次允许阻止。 ASR 规则的警告模式仅支持 RS5+ (1809) 设备。 如果在具有较旧版本的设备上将绕过分配给 ASR 规则，则规则将进入阻止模式。

您还可以通过 PowerShell 在警告模式下设置规则，只需将AttackSurfaceReductionRules_Actions指定为"Warn"。 例如：

```powershell
-command "& {&'Add-MpPreference' -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Warn"} 
```

## <a name="per-rule-descriptions"></a>每个规则说明

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>阻止滥用被攻击的易受攻击的已签名驱动程序

此规则阻止应用程序将易受攻击的已签名驱动程序写入磁盘。 具有获取内核\-  \-访问权限的足够权限的本地应用程序可能会利用通配符、易受攻击的已签名驱动程序。 易受攻击的已签名驱动程序使攻击者能够禁用或规避安全解决方案，并最终导致系统泄露。

阻止 **滥用被攻击的易受攻击的** 已签名驱动程序规则不会阻止加载系统中已存在的驱动程序。

> [!NOTE]
>
> 可以使用 MEM OMA-URI 配置此规则。 请参阅 [MEM OMA-URI](enable-attack-surface-reduction.md#mem) 以配置自定义规则。
>
> 您还可以使用 [PowerShell](enable-attack-surface-reduction.md#powershell) 配置此规则。
>
> 若要检查驱动程序，请使用此网站提交 [驱动程序进行分析](https://www.microsoft.com/en-us/wdsi/driversubmission)。

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

此规则通过阻止 Adobe Reader 创建进程来阻止攻击。

通过社交工程或攻击，恶意软件可以下载和启动有效负载，并退出 Adobe Reader。 通过阻止 Adobe Reader 生成子进程，尝试将其用作矢量的恶意软件可防止传播。

Intune名称：`Process creation from Adobe Reader (beta)`

Configuration Manager名称：尚不可用

GUID：`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

高级搜寻操作类型：

- AsrAdobeReaderChildProcessAudited
- AsrAdobeReaderChildProcessBlocked

依赖项：MDAV

### <a name="block-all-office-applications-from-creating-child-processes"></a>阻止所有Office应用程序创建子进程

此规则阻止Office创建子进程。 Office应用程序包括 Word、Excel、PowerPoint、OneNote 和 Access。

创建恶意子进程是常见的恶意软件策略。 滥用作为Office的恶意软件通常会运行 VBA 宏并攻击代码以下载并尝试运行更多有效负载。 但是，某些合法的业务线应用程序也可能出于恶意目的生成子进程;例如生成命令提示符或使用 PowerShell 配置注册表设置。

Intune名称：`Office apps launching child processes`

Configuration Manager名称：`Block Office application from creating child processes`

GUID：`d4f940ab-401b-4efc-aadc-ad5f3c50688a`

高级搜寻操作类型：

- AsrOfficeChildProcessAudited
- AsrOfficeChildProcessBlocked

依赖项：MDAV

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>阻止从本地安全Windows窃取凭据

此规则通过锁定 LSASS 应用程序的本地安全机构子系统服务 (凭据) 。

LSASS 对登录 Windows进行身份验证。 Microsoft Defender Credential Guard Windows通常会阻止尝试从 LSASS 中提取凭据。 但是，某些组织无法在所有计算机上启用 Credential Guard，因为自定义智能卡驱动程序或其他加载到本地安全机构 (LSA) 。 在这些情况下，攻击者可以使用 Mimikatz 等黑客工具从 LSASS 中清除明文密码和 NTLM 哈希。

> [!NOTE]
> 在某些应用中，该代码枚举所有正在运行的进程，并尝试以详尽的权限打开它们。 此规则拒绝应用的进程打开操作，将详细信息记录到安全事件日志中。 此规则会产生大量噪音。 如果你的应用仅枚举 LSASS，但在功能方面没有实际影响，则无需将其添加到排除列表。 此事件日志条目本身不一定表示恶意威胁。
  
> [!IMPORTANT]
> 攻击面减少 (ASR) 规则"阻止从 Windows 本地安全机构子系统 (lsass.exe) 窃取凭据"的默认状态会从"未配置"更改为"已配置"，默认模式将设置为"阻止"。  所有其他 ASR 规则将保持其默认状态： **未配置**。 规则中已包含其他筛选逻辑，以减少最终用户通知。 客户可以将规则配置为 **审核****、警告** 或 **禁用** 模式，这将覆盖默认模式。 无论规则是在默认状态下配置的，还是手动启用阻止模式，此规则的功能都是相同的。  

Intune名称：`Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager名称：`Block credential stealing from the Windows local security authority subsystem`

GUID：`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

高级搜寻操作类型：

- AsrLsassCredentialTheftAudited
- AsrLsassCredentialTheftBlocked

依赖项：MDAV

### <a name="block-executable-content-from-email-client-and-webmail"></a>阻止来自电子邮件客户端和 Webmail 的可执行内容

此规则阻止从 Microsoft Outlook 应用程序、Outlook.com 和其他热门 Web 邮件提供程序内打开的电子邮件启动以下文件类型：

- 可执行文件 (，如 .exe、.dll 或 .scr) 
- 脚本文件 (如 PowerShell .ps、Visual Basic .vbs 或 JavaScript .js文件) 

Intune名称：`Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager名称：`Block executable content from email client and webmail`

GUID：`be9ba2d9-53ea-4cdc-84e5-9b1eeee46550`

高级搜寻操作类型：

- AsrExecutableEmailContentAudited
- AsrExecutableEmailContentBlocked

依赖项：MDAV

> [!NOTE]
> 规则 **"阻止来自电子邮件客户端和 Webmail** 的可执行内容"具有以下替代说明，具体取决于你使用的应用程序：
>
> - Intune (配置文件) ：执行从电子邮件 (webmail/mail 客户端)  (删除的可执行内容 (exe、dll、ps、js、vbs 等 ) ) 。
> - Endpoint Manager：阻止从电子邮件和 Webmail 客户端下载可执行内容。
> - 组策略：阻止来自电子邮件客户端和 Webmail 的可执行内容。

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件

此规则阻止可执行文件（.exe、.dll 或 .scr）启动。 因此，启动不受信任的或未知的可执行文件可能会存在风险，因为这些文件是否恶意最初可能不明确。

> [!IMPORTANT]
> 必须 [启用云保护才能](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 使用此规则。
>
> 规则 **阻止可执行文件运行** ，除非它们符合普遍程度、年龄或受信任列表条件（具有 GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` ）归 Microsoft 所有，且未由管理员指定。 此规则使用云提供的保护定期更新其受信任列表。
>
> 可以使用文件夹路径或完全限定的资源 (指定单个文件或文件夹) 但无法指定适用于哪些规则或排除项。

Intune名称：`Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager名称：`Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID：`01443614-cd74-433a-b99e-2ecdc07bfc25`

高级搜寻操作类型：

- AsrUntrustedExecutableAudited
- AsrUntrustedExecutableBlocked

依赖项：MDAV、云保护

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>阻止执行可能混淆的脚本

此规则在混淆的脚本中检测可疑属性。

脚本模糊处理是恶意软件作者和合法应用程序都用于隐藏知识产权或缩短脚本加载次数的常见技术。 恶意软件作者还使用模糊处理使恶意代码更难阅读，这可防止人员和安全软件进行严格的审查。

Intune名称：`Obfuscated js/vbs/ps/macro code`

Configuration Manager名称：`Block execution of potentially obfuscated scripts`

GUID：`5beb7efe-fd9a-4556-801d-275e5ffc04cc`

高级搜寻操作类型：

- AsrObfuscatedScriptAudited
- AsrObfuscatedScriptBlocked

依赖项：MDAV、AMSI

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>阻止 JavaScript 或 VBScript 启动下载的可执行内容

此规则阻止脚本启动潜在恶意下载的内容。 用 JavaScript 或 VBScript 编写的恶意软件通常充当从 Internet 提取和启动其他恶意软件的下载程序。

虽然不常见，但业务线应用程序有时会使用脚本下载和启动安装程序。

Intune名称：`js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager名称：`Block JavaScript or VBScript from launching downloaded executable content`

GUID：`d3e037e1-3eb8-44c8-a917-57927947596d`

高级搜寻操作类型：

- AsrScriptExecutableDownloadAudited
- AsrScriptExecutableDownloadBlocked

依赖项：MDAV、AMSI

### <a name="block-office-applications-from-creating-executable-content"></a>阻止Office应用程序创建可执行内容

此规则Office Word、Excel 和 PowerPoint 等应用阻止恶意代码写入磁盘，从而阻止这些应用创建潜在恶意可执行内容。

滥用作为Office的恶意软件可能会尝试Office恶意组件保存到磁盘。 这些恶意组件在计算机重新启动后将一直保留于系统。 因此，此规则可防御常见的持久性技术。

Intune名称：`Office apps/macros creating executable content`

SCCM 名称： `Block Office applications from creating executable content`

GUID：`3b576869-a4ec-4529-8536-b80a7769e899`

高级搜寻操作类型：

- AsrExecutableOfficeContentAudited
- AsrExecutableOfficeContentBlocked

依赖项：MDAV、RPC

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>阻止Office将代码注入其他进程

此规则阻止代码注入尝试Office应用注入其他进程。

攻击者可能会尝试使用Office代码注入将恶意代码迁移到其他进程中，因此代码可以伪装成一个干净流程。

使用代码注入没有已知的合法业务用途。

此规则适用于 Word、Excel 和 PowerPoint。

Intune名称：`Office apps injecting code into other processes (no exceptions)`

Configuration Manager名称：`Block Office applications from injecting code into other processes`

GUID：`75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84`

高级搜寻操作类型：

- AsrOfficeProcessInjectionAudited
- AsrOfficeProcessInjectionBlocked

依赖项：MDAV

### <a name="block-office-communication-application-from-creating-child-processes"></a>阻止Office应用程序创建子进程

此规则阻止Outlook子进程，同时仍允许合法Outlook进程。

此规则可防止社会工程攻击，并防止利用代码滥用Outlook。 它还[可Outlook用户](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)凭据泄露时攻击者可能使用的规则和表单攻击。

> [!NOTE]
> 此规则阻止 DLP 策略提示和工具提示Outlook。 此规则仅适用于 Outlook Outlook.com。

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

此规则阻止通过 [PsExec](/sysinternals/downloads/psexec) 和 [WMI 创建](/windows/win32/wmisdk/about-wmi) 的进程运行。 PsExec 和 WMI 都可以远程执行代码，因此存在恶意软件滥用此功能以用于命令和控制目的，或在整个组织的网络中传播感染的风险。

> [!WARNING]
> 仅在使用你的设备或其他 MDM 解决方案管理[Intune使用此规则](/intune)。 此规则与通过 [Microsoft Endpoint Configuration Manager 管理不兼容](/configmgr)，因为此规则阻止客户端Configuration Manager的 WMI 命令。

Intune名称：`Process creation from PSExec and WMI commands`

Configuration Manager名称：不适用

GUID：`d1e49aac-8f56-4280-b9ba-993a6d77406c`

高级搜寻操作类型：

- AsrPsexecWmiChildProcessAudited
- AsrPsexecWmiChildProcessBlocked

依赖项：MDAV

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>阻止从 USB 运行的不受信任的和未签名的进程

通过此规则，管理员可以阻止未签名或不受信任的可执行文件从 USB 可移动驱动器（包括 SD 卡）运行。 阻止的文件类型包括可执行 (文件，.exe、.dll或 .scr) 

Intune名称：`Untrusted and unsigned processes that run from USB`

Configuration Manager名称：`Block untrusted and unsigned processes that run from USB`

GUID：`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

高级搜寻操作类型：

- AsrUntrustedUsbProcessAudited
- AsrUntrustedUsbProcessBlocked

依赖项：MDAV

### <a name="block-win32-api-calls-from-office-macros"></a>阻止从宏Office Win32 API 调用

此规则阻止 VBA 宏调用 Win32 API。

Office VBA 启用 Win32 API 调用。 恶意软件可能会滥用此功能，例如调用 [Win32 API 以启动恶意 shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) ，而无需将任何内容直接写入磁盘。 大多数组织不依赖于在日常运行中调用 Win32 API 的功能，即使它们以其他方式使用宏。

支持的操作系统：

- [Windows 10，版本 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server 版本 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune名称：`Win32 imports from Office macro code`

Configuration Manager名称：`Block Win32 API calls from Office macros`

GUID：`92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b`

高级搜寻操作类型：

- AsrOfficeMacroWin32ApiCallsAudited
- AsrOfficeMacroWin32ApiCallsBlocked

依赖项：MDAV、AMSI

### <a name="use-advanced-protection-against-ransomware"></a>使用高级防护抵御勒索软件

此规则提供针对勒索软件的额外保护层。 它使用客户端和云启发来确定文件是否类似于勒索软件。 此规则不会阻止具有以下一个或多个特征的文件：

- 已在 Microsoft 云中发现该文件未共享。
- 文件是有效的签名文件。
- 该文件非常流行，不被视为勒索软件。

该规则倾向于谨慎阻止勒索软件。

> [!NOTE]
> 必须 [启用云保护才能](enable-cloud-protection-microsoft-defender-antivirus.md) 使用此规则。

Intune名称：`Advanced ransomware protection`

Configuration Manager名称：`Use advanced protection against ransomware`

GUID：`c1db55ab-c21a-4637-bb3f-a12568109d35`

高级搜寻操作类型：

- AsrRansomwareAudited
- AsrRansomwareBlocked

依赖项：MDAV、云保护
