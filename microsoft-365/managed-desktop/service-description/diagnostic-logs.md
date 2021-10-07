---
title: 诊断日志
description: 在疑难解答期间可能从设备收集的日志及其存储方式
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5c890ea42da4bb13c163e7b8b123080e0264d025
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201525"
---
# <a name="diagnostic-logs"></a>诊断日志

当我们在由 Microsoft 托管桌面 管理的设备上解决问题时，无论你已报告问题还是由服务识别的问题，我们可能需要从设备中收集某些诊断日志，而无需用户干预。 我们不会从用户目录中收集任何用户生成的内容或信息。 我们仅收集与设备运行状况和状态有关诊断和日志数据。

我们将收集的任何日志存储 28 天，然后将其删除。 我们将按照数据处理标准处理从设备 [收集的任何日志](privacy-personal-data.md)。

## <a name="data-collected"></a>收集的数据

此列表包括所有文件夹、事件日志、可执行文件或注册表位置，Microsoft 托管桌面收集诊断日志。 收集的实际数据将是此列表的子集，具体取决于已识别的问题。

### <a name="registry-keys"></a>注册表项

- HKLM \\ SYSTEM \\ CurrentControlSet \\ Services
- HKLM \\ 软件 \\ Microsoft \\ Surface
- HKLM \\ SOFTWARE Policies Microsoft Windows \\ \\ \\ \\ WindowsUpdate
- HKLM \\ SYSTEM \\ CurrentControlSet \\ 控件 \\ MUI \\ UILanguages
- HKLM \\ 软件 \\ 策略 Microsoft \\ \\ WindowsStore
- HKLM \\ 软件 Microsoft Windows \\ \\ \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ AppModel
- HKLM \\ SYSTEM \\ CurrentControlSet \\ 控件 \\ FirmwareResources
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Appx
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion \\ Superfetch
- HKLM \\ 系统 \\ 设置
- HKLM \\ 软件 \\ Microsoft \\ IntuneManagementExtension
- HKLM \\ 软件 \\ Microsoft \\ SystemCertificates \\ AuthRoot
- HKLM \\ SOFTWARE \\ Microsoft \\ Windows高级威胁防护
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Authentication \\ \\ LogonUI
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion Internet \\ 设置
- HKLM \\ 软件 Microsoft Windows \\ \\ \\ CurrentVersion \\ 卸载
- HKLM \\ 软件 \\ 策略
- HKLM \\ 软件 \\ 策略 Microsoft \\ \\ 加密配置 \\ \\ SSL
- HKLM \\ 软件 \\ 策略 Microsoft \\ \\ Windows高级威胁防护
- HKLM \\ 软件 \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ 卸载
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL

### <a name="commands"></a>命令

- %programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles
- %windir% \\ system32 \\certutil.exe -store
- %windir% \\ system32 \\certutil.exe -store -user my
- %windir% \\ system32 \\Dsregcmd.exe /status
- %windir% \\ system32 \\ipconfig.exe /all
- %windir% \\ system32 \\ipconfig.exe /displaydns
- %windir% \\ system32 \\mdmdiagnosticstool.exe
- %windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log
- %windir% \\ system32 \\netsh.exe advfirewall 显示所有文件
- %windir% \\ system32 \\netsh.exe advfirewall 显示全局
- %windir% \\ system32 \\netsh.exe lan 显示配置文件
- %windir% \\ system32 \\netsh.exe winhttp 显示代理
- %windir% \\ system32 \\netsh.exe wlan 显示配置文件
- %windir% \\ system32 \\netsh.exe wlan 显示 wlanreport
- %windir% \\ system32 \\ping.exe -n 50 localhost
- %windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html
- %windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html
- bitsadmin /list /allusers /verbose
- fltMC.exe
- bcdedit /enum all /v
- manage-bde -protectors -get
- Windows PowerShell命令：
    - Get-appxpackage -allusers
    - Get-appxpackage -packagetype bundle
    - Get-Service wuauserv
    - Get-NetFirewallRule
    - Get-WmiObject -Class win32 \_ 产品
    - Get-ComputerInfo
    - Get-Service
    - Get-Process
    - Get-WmiObject Win32 \_ PnPSignedDriver

### <a name="event-logs"></a>事件日志

- Application
- Microsoft-Windows-AppLocker/EXE 和 DLL
- Microsoft-Windows-AppLocker/MSI 和脚本
- Microsoft-Windows-AppLocker/封装应用部署
- Microsoft-Windows-AppLocker/封装应用执行
- Microsoft-Windows-Bitlocker/Bitlocker Management
- Microsoft-Windows-SENSE/Operational
- Microsoft-Windows-SenseIR/Operational
- 设置
- System

### <a name="files"></a>文件

- %ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ Collectors \\ \* .etl
- %ProgramData% \\ Microsoft \\ IntuneManagementExtension \\ Logs \\ \* .\*
- %ProgramData% \\ Microsoft Windows Defender Support \\ \\ \\MpSupportFiles.cab
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport -SourceFileName wlan-report-latest.html
- %windir% \\ ccm \\ logs \* .log
- %windir% \\ ccmsetup \\ logs \* .log
- %windir% \\ logs \\ CBS \\ cbs.log
- %windir% \\ logs \\ measuredboot \* .\*
- %windir% \\ Logs \\ WindowsUpdate \* .etl
- %windir% \\ inf \\ \* .log
- %windir% \\ \\ 服务 \\ 会话ActionList.xml
- %windir% \\ \\ 服务 \\ 会话Sessions.xml
- %windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log
- %windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb
- %windir% \\ logs \\ dism \\ dism.log
- %SystemRoot% \\ System32 \\ Winevt \\ 日志\\
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl
- %appdata% \\ Microsoft \\ Teams \\logs.txt
- %windir% \\ Windows \\ System32 \\ winevt \\ \* 。\*