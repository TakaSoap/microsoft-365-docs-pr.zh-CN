---
title: 使用 PowerShell、WMI 和 MPCmdRun.exe
description: 了解如何使用 PowerShell、WMI 和 MPCmdRun.exe
keywords: 迁移后， 管理， 操作， 维护， 利用率， PowerShell， WMI， MPCmdRun.exe， Microsoft Defender for Endpoint， edr
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/23/2020
ms.reviewer: chventou
ms.openlocfilehash: 2fe421e79efa7da204209e2df35d3be51bdbf6d1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154766"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>使用 PowerShell、WMI 和 MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

> [!NOTE]
> 我们建议使用[Microsoft Endpoint Manager](/mem)管理组织对也称为终结点 (的设备的威胁防护) 。 Endpoint Manager包括[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)和[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)。
>
> - [详细了解Endpoint Manager](/mem/endpoint-manager-overview)
> - [使用 Configuration Manager 和 Intune 在 Windows 10 和 Windows 11 设备上共同管理 Microsoft Defender for Endpoint](manage-atp-post-migration-intune.md)
> - [使用 Intune 管理 Microsoft Defender for Endpoint](manage-atp-post-migration-intune.md)

可以使用[PowerShell、Windows](#configure-microsoft-defender-for-endpoint-with-powershell) [Management Instrumentation](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI) 和[Microsoft 恶意软件](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe)防护命令行实用工具 (MPCmdRun.exe) 在设备上管理某些 (MPCmdRun.exe) 。 Microsoft Defender 防病毒 例如，你可以管理一些Microsoft Defender 防病毒设置。 在某些情况下，你可以自定义攻击面减少规则和 Exploit Protection 设置。

> [!IMPORTANT]
> 使用 PowerShell、WMI 或 MCPmdRun.exe配置配置设置可能会覆盖使用 Intune 或 Configuration Manager 配置配置功能。

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>使用 PowerShell 配置 Microsoft Defender for Endpoint

可以使用 PowerShell 管理Microsoft Defender 防病毒、Exploit Protection 和攻击面减少规则。<br/><br/>

|任务|了解详细信息的资源|
|---|---|
|**管理Microsoft Defender 防病毒** <br/><br/> 查看反恶意软件保护的状态、配置防病毒扫描的首选项&更新，以及对防病毒保护进行其他更改。*|[使用 PowerShell cmdlet 配置和管理Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus) <br/><br/> [使用 PowerShell cmdlet 启用云保护](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)|
|**配置 Exploit Protection** 以缓解组织设备上的威胁 <br/><br/> *我们建议首先在审核模式下 [使用](/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) Exploit Protection。这样，你可以了解 Exploit Protection 如何影响组织使用的应用。*|[自定义漏洞保护](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/> [用于 Exploit Protection 的 PowerShell cmdlet](/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)|
|**使用** PowerShell 配置攻击面减少规则 <br/><br/> *可以使用 PowerShell 从攻击面减少规则中排除文件和文件夹。*|[自定义攻击面减少规则：使用 PowerShell 排除文件夹中&文件](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders) <br/><br/> 另请参阅 [Antio Vasconcelo 的图形](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)用户界面工具，以使用 PowerShell 设置攻击面减少规则。|
|**使用** PowerShell 启用网络保护 <br/><br/> *可以使用 PowerShell 启用网络保护。*|[使用 PowerShell 打开网络保护](/microsoft-365/security/defender-endpoint/enable-network-protection#powershell)|
|**配置受控文件夹访问权限** 以防范勒索软件 <br/><br/> *[受控文件夹访问权限](/microsoft-365/security/defender-endpoint/controlled-folders) 也称为反反somware保护。*|[使用 PowerShell 启用受控文件夹访问权限](/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell)|
|**配置 Microsoft Defender 防火墙** 以阻止未经授权的网络流量流入或流出组织的设备|[使用高级安全管理 Microsoft Defender 防火墙Windows PowerShell](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell)|
|**配置加密和 BitLocker** 以保护在组织中运行加密Windows|[BitLocker PowerShell 参考指南](/powershell/module/bitlocker/)|

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>使用 Windows Management Instrumentation (WMI) 配置 Microsoft Defender for Endpoint

WMI 是一个脚本界面，允许您检索、修改和更新设置。 若要了解更多信息，请参阅[使用 WMI。](/windows/win32/wmisdk/using-wmi)<br/><br/>

|任务|了解详细信息的资源|
|---|---|
|**在设备上启用** 云保护|[使用 Windows Management Instruction (WMI) 启用云保护](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)|
|**检索、修改和更新 Microsoft Defender 防病毒**|[使用 WMI 配置和管理 Microsoft Defender 防病毒] (/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus <br/><br/> [查看可用 WMI 类和示例脚本的列表](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/> 另请参阅已存档的[Windows Defender WMIv2 提供程序参考信息](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)|

## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>使用 Microsoft 恶意软件防护实用程序配置 Microsoft Defender Command-Line终结点 (MPCmdRun.exe) 

在单台设备上，可以使用命令行工具运行扫描、启动诊断跟踪、检查安全mpcmdrun.exe更新等。 可以在 中查找此实用工具 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。 从命令提示符运行它。

若要了解更多信息，请参阅使用[Microsoft Defender 防病毒 配置mpcmdrun.exe。 ](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)

## <a name="configure-your-microsoft-365-defender-portal"></a>配置Microsoft 365 Defender门户

如果尚未配置，请配置 Microsoft 365 Defender 门户以查看[](https://security.microsoft.com/)警报、配置威胁防护功能，并查看有关组织整体安全状况的详细信息。

您还可以配置最终用户是否可以在网站中查看这些功能Microsoft Defender 安全中心。

- [概述Microsoft Defender 安全中心](/microsoft-365/security/defender-endpoint/use)

- [终结点保护：Microsoft Defender 安全中心](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>后续步骤

- [获取威胁和漏洞管理的概述](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [访问Microsoft Defender 安全中心操作仪表板](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [使用 Intune 管理 Microsoft Defender for Endpoint](manage-atp-post-migration-intune.md)
