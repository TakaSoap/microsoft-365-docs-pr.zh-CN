---
title: 从第三方 HIPS 迁移到 ASR 规则
description: 介绍如何将第三方主机入侵防护系统或 HIPS (解决方案) 迁移到 ASR 规则。
keywords: 攻击面减少规则， asr， asr 规则， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， Microsoft Defender for Endpoint
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: lovina-saldanha
ms.author: dansimp
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 8f9f79b5db7a29e908838bacdce798609a9f2422
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60659552"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>从第三方 HIPS 迁移到 ASR 规则

本文帮助你将通用规则映射到 Microsoft Defender for Endpoint。

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>从第三方 HIPS 产品迁移到 ASR 规则时的方案

### <a name="block-creation-of-specific-files"></a>阻止创建特定文件

- **适用于**- 所有进程
- **操作**- 文件创建
- **文件/文件夹、注册表项/值、进程、服务**- *.zepto、*.odin、*.locky、*.jaff、*.lukitus、*.wnry、*.zeb 的示例
- **攻击面减少规则**- ASR 规则阻止攻击技术，而不是 IOC (泄露) 。 阻止特定文件扩展名并非始终有用，因为它不会阻止设备泄漏。 它仅部分阻止攻击，直到攻击者为有效负载创建新的扩展类型。
- **其他推荐功能**- 强烈建议启用 Microsoft Defender AV 以及云保护和行为分析。 我们建议你使用其他防护，例如 ASR 规则"使用高级防护抵御勒索软件"。 这提供了针对勒索软件攻击的更高级别的保护。 此外，这些注册表项中的许多项由 Microsoft Defender for Endpoint 监视，例如 ASEP 技术，这将触发特定警报。 使用的注册表项至少需要本地管理员权限或受信任的安装程序权限才能进行修改。 建议使用具有最低管理帐户或权限的锁定环境。 可以启用其他系统配置，包括"禁用非必需角色的 SeDebug"，这是更广泛的安全建议中的一部分。

### <a name="block-creation-of-specific-registry-keys"></a>阻止创建特定注册表项

- **应用于**- 所有进程
- **进程**- N/A
- **操作**- 注册表修改
- **文件/文件夹、注册表项/值、进程、服务示例** - *\Software*，HKCU\Environment\UserInitMprLogonScript，HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs *\StartExe， HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options*\Debugger， HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location， HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\MonitorProcess
- **攻击面减少规则**- ASR 规则阻止攻击技术，而不是 IOC (泄露) 。 阻止特定文件扩展名并非始终有用，因为它不会阻止设备泄漏。 它仅部分阻止攻击，直到攻击者为有效负载创建新的扩展类型。
- **其他推荐功能**- 强烈建议启用 Microsoft Defender AV 以及云保护和行为分析。 我们建议你使用其他防护，如 ASR 规则"使用高级防护抵御勒索软件"。 这提供了针对勒索软件攻击的更高级别的保护。 此外，其中一些注册表项由 Microsoft Defender for Endpoint 进行监视，例如 ASEP 技术，这将触发特定警报。 此外，使用的注册表项至少需要本地管理员权限或受信任的安装程序权限才能进行修改。 建议使用具有最低管理帐户或权限的锁定环境。 可以启用其他系统配置，包括"禁用非必需角色的 SeDebug"，这是更广泛的安全建议中的一部分。

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>阻止不受信任的程序从可移动驱动器运行

- **适用于**- 来自 USB 的不受信任的程序
- **进程**- *
- **操作**- 进程执行
- **文件/文件夹、注册表项/值、进程、服务的示例：-*
- **攻击面** 减少规则 - ASR 规则具有内置规则，可阻止从可移动驱动器启动不受信任的和未签名的程序："阻止从 USB 运行的不受信任的和未签名的进程"、GUID"b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4"。
- **其他推荐功能**- 请使用 Microsoft Defender for Endpoint 探索 USB 设备和其他可移动媒体的其他控件：如何使用 Microsoft Defender for Endpoint 控制 USB 设备和其他 [可移动媒体](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)。

### <a name="block-mshta-from-launching-certain-child-processes"></a>阻止 Mshta 启动某些子进程

- **适用于**- Mshta
- **进程**- mshta.exe
- **操作**- 进程执行
- **文件/文件夹、注册表项/** 值、进程、服务 - powershell.exe、cmd.exe、regsvr32.exe
- **攻击面减少规则**- ASR 规则不包含任何特定规则来阻止子进程"mshta.exe"。 此控件位于 Exploit Protection 或 Windows Defender 应用程序控制中。
- **其他建议的功能**- Windows Defender应用程序控制以防止mshta.exe完全执行。 如果你的组织需要"mshta.exe应用"，请配置特定的Windows Defender Exploit Protection 规则，以防止mshta.exe启动子进程。

### <a name="block-outlook-from-launching-child-processes"></a>阻止Outlook启动子进程

- **适用于**- Outlook
- **进程**- outlook.exe
- **操作**- 进程执行
- **文件/文件夹、注册表项/值、进程、服务**- powershell.exe
- **攻击面** 减少规则 - ASR 规则具有内置规则，可阻止 Office 通信应用 (Outlook、Skype 和 Teams) 启动子进程："阻止 Office 通信应用程序创建子进程"，GUID "26190899-1602-49e8-8b27-eb1d0a1ce869"。
- **其他推荐功能**- 我们建议启用 PowerShell 约束语言模式，以最大限度地降低 PowerShell 的攻击面。

### <a name="block-office-apps-from-launching-child-processes"></a>阻止Office应用启动子进程

- **适用于**- Office
- **进程**- winword.exe、powerpnt.exe、excel.exe
- **操作**- 进程执行
- **文件/文件夹、注册表项/** 值、进程、服务 - powershell.exe、cmd.exe、wscript.exe、mshta.exe、EQNEDT32.EXE、regsrv32.exe
- **攻击面** 减少规则 - ASR 规则内置了阻止 Office 应用启动子进程的规则："阻止所有 Office 应用程序创建子进程"、GUID "d4f940ab-401b-4efc-aadc-ad5f3c50688a"。
- **其他推荐功能**- N/A

### <a name="block-office-apps-from-creating-executable-content"></a>阻止Office应用创建可执行内容

- **适用于**- Office
- **进程**- winword.exe、powerpnt.exe、excel.exe
- **操作**- 文件创建
- **文件/文件夹、注册表项/值的示例 进程、** 服务 - C：\Users *\AppData **.exe、C：\ProgramData**.exe、C：\ProgramData**.com、C：\Users* AppData\Local\Temp **.com、C：\Users*\Downloads**.exe、C：\Users ***\AppData .scf、C：\ProgramData**.scf、C：\Users\Public*.exe、C：\Users*\Desktop***.exe
- **攻击面减少规则**- N/A。

### <a name="block-wscript-from-reading-certain-types-of-files"></a>阻止 Wscript 读取某些类型的文件

- **适用于**- Wscript
- **进程**- wscript.exe
- **操作**- 文件读取
- **文件/文件夹、注册表项/** 值、进程、服务 - C：\Users *\AppData**.js、C：\Users*\Downloads**.js
- **攻击面减少** 规则 - 由于可靠性和性能问题，ASR 规则无法阻止特定进程读取特定脚本文件类型。 我们有一个规则来阻止可能源自这些方案的攻击途径。 规则名称为"阻止 JavaScript 或 VBScript 启动下载的可执行内容" (GUID "d3e037e1-3eb8-44c8-a917-57927947596d") 和"阻止执行可能混淆的脚本" (GUID" 5beb7efe-fd9a-4556-801d-275e5ffc04cc") 。
- 其他推荐功能 **-** 尽管存在在这些方案中缓解某些攻击途径的特定 ASR 规则，但需要指出的是，AV 默认情况下能够通过反恶意软件扫描接口 ( (AMSI) 实时检查脚本 (PowerShell、Windows Script Host、JavaScript、VBScript 等) 。 详细信息在此处提供： [反恶意软件扫描接口 (AMSI) ](/windows/win32/amsi/antimalware-scan-interface-portal)。

### <a name="block-launch-of-child-processes"></a>阻止启动子进程

- **适用于**- Adobe Acrobat
- **进程**- AcroRd32.exe、Acrobat.exe
- **操作**- 进程执行
- **文件/文件夹、注册表项/** 值、进程、服务 - cmd.exe、powershell.exe、wscript.exe
- **攻击面减少规则**- ASR 规则允许阻止 Adobe Reader 启动子进程。 规则名称为"阻止 Adobe Reader 创建子进程"、GUID"7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c"。
- **其他推荐功能**- N/A

### <a name="block-download-or-creation-of-executable-content"></a>阻止下载或创建可执行内容

- **适用于**- CertUtil：阻止下载或创建可执行文件
- **进程**- certutil.exe
- **操作**- 文件创建
- **文件/文件夹、注册表项/值、进程、服务**- *.exe
- **攻击面减少规则**- ASR 规则不支持这些方案，因为它们是防护Microsoft Defender 防病毒一部分。
- **其他推荐功能**- Microsoft Defender AV 阻止 CertUtil 创建或下载可执行内容。

### <a name="block-processes-from-stopping-critical-system-components"></a>阻止进程停止关键系统组件

- **应用于**- 所有进程
- **进程**- *
- **操作**- 进程终止
- **文件/** 文件夹、注册表项/值、进程、服务 - MsSense.exe、MsMpEng.exe、NisSrv.exe、svchost.exe*、services.exe、csrss.exe、smss.exe、wininit.exe 等示例。
- **攻击面** 减少规则 - ASR 规则不支持这些方案，因为它们受内置Windows保护。
- **其他推荐功能**- ELAM (提前启动反恶意软件) 、PPL (Protection Process Light) 、PPL AntiMalware Light 和 System Guard。

### <a name="block-specific-launch-process-attempt"></a>阻止特定启动进程尝试

- **适用于**- 特定流程
- **进程**- "命名你的进程"
- **操作**- 进程执行
- **文件/文件夹、注册表项/** 值、进程、服务 - tor.exe、bittorrent.exe、cmd.exe、powershell.exe 等示例
- **攻击面减少规则**- 总的来说，ASR 规则不能作为应用程序管理器工作。
- **其他推荐功能**- 若要阻止用户启动特定进程或程序，建议Windows Defender应用程序控制。 Microsoft Defender for Endpoint File and Cert indicators， can be used in an Incident Response scenario ( (shouldn't be seen as an application control mechanism) .

### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>阻止未经授权更改Microsoft Defender 防病毒配置

- **应用于**- 所有进程
- **进程**- *
- **操作**- 注册表修改
- 文件/文件夹、**注册表项/** 值、进程、服务 - HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware、HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring 等的示例。
- **攻击面** 减少规则 - ASR 规则不包括这些方案，因为它们是 Microsoft Defender for Endpoint 内置保护的一部分。
- 其他推荐功能 **-** 防篡改保护 (选择加入，从 Intune) 管理，可防止对 DisableAntiVirus、DisableAntiSpyware、DisableRealtimeMonitoring、DisableOnAccessProtection、DisableBehaviorMonitoring 和 DisableIOAVProtection 注册表项 (及更多) 进行未经授权的更改。

另请参阅

- [关于攻击面减少的常见问题解答](attack-surface-reduction-faq.yml)
- [启用攻击面减少规则](enable-attack-surface-reduction.md)
- [评估攻击面减少规则](evaluate-attack-surface-reduction.md)
