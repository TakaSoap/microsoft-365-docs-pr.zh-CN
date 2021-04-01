---
title: 从第三方 HIPS 迁移到 ASR 规则
description: 介绍如何从第三方主机入侵防护系统或 HIPS (解决方案) 迁移到 ASR 规则。
keywords: 攻击面减少规则， asr， asr 规则， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， Microsoft Defender for Endpoint， Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: ced969fdd3e8b63136f8bd3f043272e76d99bc5e
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476494"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>从第三方 HIPS 迁移到 ASR 规则

本文帮助你将通用规则映射到 Microsoft Defender for Endpoint。 下表显示了从第三方 HIPS 产品迁移到 ASR 规则的常见问题和方案。

|范围和操作|进程|操作|文件/文件夹、注册表项/值、进程、服务示例|攻击面减少规则|其他推荐功能|
|:--|:--|:--|:--|:--|:--|
|所有进程：阻止创建特定文件和注册表项||文件创建|*.zepto、*.odin、*.locky、*.jaff、*.lukitus、*.wnry、*.zeb|ASR 规则会阻止攻击技术，而不是 IOC (泄露) 。 阻止特定文件扩展名并非始终有用，因为它不会阻止设备泄漏。 它仅部分阻止攻击，直到攻击者为有效负载创建新的扩展类型。|强烈建议启用 Microsoft Defender AV 以及云保护和行为分析。 我们建议你使用其他防护，例如 ASR 规则"使用高级防护抵御勒索软件"。 这提供了针对勒索软件攻击的更高级别的保护。 此外，其中一些注册表项由 Microsoft Defender for Endpoint 进行监视，例如 ASEP 技术，这将触发特定警报。 使用的注册表项至少需要本地管理员或受信任的安装程序权限才能进行修改。 建议使用具有最低管理帐户或权限的锁定环境。 可以启用其他系统配置，包括"禁用非必需角色的 SeDebug"，这是更广泛的安全建议中的一部分。|
|所有进程：阻止创建特定文件和注册表项||注册表修改|*\Software \* ，HKCU\Environment\UserInitMprLogonScript，HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs \* \StartExe， HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options \* \Debugger，HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location，HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit \* \MonitorProcess|ASR 规则会阻止攻击技术，而不是 IOC (泄露) 。 阻止特定文件扩展名并非始终有用，因为它不会阻止设备泄漏。 它仅部分阻止攻击，直到攻击者为有效负载创建新的扩展类型。|强烈建议启用 Microsoft Defender AV 以及云保护和行为分析。 我们建议你使用其他防护，如 ASR 规则"使用高级防护抵御勒索软件"。 这提供了针对勒索软件攻击的更高级别的保护。 此外，其中一些注册表项由 Microsoft Defender for Endpoint 进行监视，例如 ASEP 技术，这将触发特定警报。 此外，使用的注册表项至少需要本地管理员或受信任的安装程序权限才能进行修改。 建议使用具有最低管理帐户或权限的锁定环境。 可以启用其他系统配置，包括"禁用非必需角色的 SeDebug"，这是更广泛的安全建议中的一部分。|
|来自 USB 的不受信任的程序：阻止不受信任的程序从可移动驱动器运行|*|进程执行|*|ASR 规则具有内置规则，可阻止从可移动驱动器启动不受信任的和未签名的程序："阻止从 USB 运行的不受信任的和未签名的进程"、GUID"b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4"。|请使用 Microsoft Defender for Endpoint 探索 USB 设备和其他可移动媒体的其他控件：如何使用 Microsoft Defender for Endpoint 控制 USB 设备和其他 [可移动媒体](https://docs.microsoft.com/windows/security/threat-protection/device-control/control-usb-devices-using-intune)。 |
|Mshta：阻止 Mshta 启动某些子进程|mshta.exe|进程执行|powershell.exe、cmd.exe、regsvr32.exe|ASR 规则不包含任何特定规则来阻止子进程"mshta.exe"。 此控件位于 Exploit Protection 或 Windows Defender 应用程序控制中。|启用Windows Defender应用程序控件mshta.exe完全执行该控件。 如果你的组织需要"mshta.exe应用"，请配置特定的 Windows Defender Exploit Protection 规则，以防止mshta.exe启动子进程。|
|Outlook：阻止 Outlook 启动子进程|outlook.exe|进程执行|powershell.exe|ASR 规则内置了阻止 Office 通信应用 (Outlook、Skype 和 Teams) 启动子进程的规则："阻止 Office 通信应用程序创建子进程"，GUID "26190899-1602-49e8-8b27-eb1d0a1ce869"。|我们建议启用 PowerShell 约束语言模式，以便最大程度地减少来自 PowerShell 的攻击面。|
|Office：阻止 Office 应用启动子进程和创建可执行内容|winword.exe、powerpnt.exe、excel.exe|进程执行|powershell.exe、cmd.exe、wscript.exe、mshta.exe、EQNEDT32.EXE、regsrv32.exe|ASR 规则内置了阻止 Office 应用启动子进程的规则："阻止所有 Office 应用程序创建子进程"、GUID "D4F940AB-401B-4EFC-AADC-AD5F3C50688A"。|无|
|Office：阻止 Office 应用启动子进程和创建可执行内容|winword.exe、powerpnt.exe、excel.exe|文件创建|C：\Users \* \* *\* \AppData .exe， \* C：\ProgramData* \* .exe， C：\ProgramData \* *\* .com， C：\Users \* AppData\Local\Temp \** \* .com， C：\Users \* *\Downloads \** \* .exe， C：\Users \* \AppData \* *\* .scf， C：\ProgramData \** \* .scf， C：\Users\Public \* \* \* * \* .exe， C：\Users \Desktop .exe|无|
|Wscript：阻止 Wscript 读取某些类型的文件|wscript.exe|文件读取|C：\Users \* \AppData \* *\* .js*， C：\Users \* \Downloads \* *\* .js*|由于可靠性和性能问题，ASR 规则无法阻止特定进程读取特定的脚本文件类型。 我们有一个规则来阻止可能源自这些方案的攻击途径。 规则名称为"阻止 JavaScript 或 VBScript 启动下载的可执行内容" (GUID "D3E037E1-3EB8-44C8-A917-57927947596D") "阻止执行可能混淆的脚本" (GUID" 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC") |尽管在这些方案中有特定的 ASR 规则可以缓解某些攻击途径，但需要指出的是，AV 默认情况下能够通过反恶意软件扫描接口 (AMSI) 实时检查脚本 (PowerShell、Windows 脚本主机、JavaScript、VBScript 等) 。 详细信息在此处可用： [反恶意软件扫描接口 (AMSI) ](https://docs.microsoft.com/windows/win32/amsi/antimalware-scan-interface-portal)。 |
|Adobe Acrobat：阻止启动子进程|AcroRd32.exe、Acrobat.exe|进程执行|cmd.exe、powershell.exe、wscript.exe|ASR 规则允许阻止 Adobe Reader 启动子进程。 规则名称为"阻止 Adobe Reader 创建子进程"、GUID"7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c"。|无|
|CertUtil：阻止下载或创建可执行内容|certutil.exe|文件创建|*.exe|ASR 规则不支持这些方案，因为它们是 Microsoft Defender 防病毒保护的一部分。|Microsoft Defender AV 阻止 CertUtil 创建或下载可执行内容。|
|所有进程：阻止进程停止关键系统组件|*|进程终止|MsSense.exe、MsMpEng.exe、NisSrv.exe、svchost.exe*、services.exe、csrss.exe、smss.exe、wininit.exe 等。|ASR 规则不支持这些方案，因为它们受 Windows 10 内置安全保护的保护。|ELAM (提前启动反恶意软件) 、PPL (Protection Process Light) 、PPL AntiMalware Light 和 System Guard。|
|特定进程：阻止特定启动进程尝试|"命名进程"|进程执行|tor.exe、bittorrent.exe、cmd.exe、powershell.exe等。|总的来说，ASR 规则并非旨在用作应用程序管理器。|若要防止用户启动特定进程或程序，建议Windows Defender应用程序控制。 Microsoft Defender for Endpoint File and Cert indicators， can be used in an Incident Response scenario (should not be seen as an application control mechanism) .|
|所有进程：阻止对 MDATP AV 配置进行未经授权的更改|*|注册表修改|HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware、HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring 等。|ASR 规则不涵盖这些类型的方案，因为它们是 Microsoft Defender for Endpoint 内置保护的一部分。|防篡改保护 (选择加入，从 Intune) 管理，可防止对 DisableAntiVirus、DisableAntiSpyware、DisableRealtimeMonitoring、DisableOnAccessProtection、DisableBehaviorMonitoring 和 DisableIOAVProtection 注册表项 (及更多) 进行未经授权的更改。 |



另请参阅

- [关于减少攻击面的常见问题解答](attack-surface-reduction-faq.md)
- [启用攻击面减少规则](enable-attack-surface-reduction.md)
- [评估减少攻击面规则](evaluate-attack-surface-reduction.md)
