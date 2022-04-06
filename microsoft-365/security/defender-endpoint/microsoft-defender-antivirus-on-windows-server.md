---
title: Windows Server 上的 Microsoft Defender 防病毒软件
description: 了解如何在 Windows Server 2016、Windows Server 2019 和 Windows Server 2022 上启用和配置Microsoft Defender 防病毒。
keywords: windows defender， server， scep， system center endpoint protection， server 2016， current branch， server 2012
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/01/2022
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: b93595375982e3ed61d1ac94ae410575b0d72307
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666979"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上的 Microsoft Defender 防病毒软件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender 防病毒在以下版本/版本的Windows服务器中可用：

- Windows Server 2022
- Windows Server 2019
- Windows服务器版本 1803 或更高版本
- Windows Server 2016
- Windows Server 2012 R2 (需要Microsoft Defender for Endpoint) 

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>在 Windows 服务器上设置Microsoft Defender 防病毒

在Windows服务器上设置和运行Microsoft Defender 防病毒的过程包括以下步骤：

1. [启用接口](#enable-the-user-interface-on-windows-server)。
2. [安装Microsoft Defender 防病毒](#install-microsoft-defender-antivirus-on-windows-server)。
3. [验证Microsoft Defender 防病毒是否正在运行](#verify-microsoft-defender-antivirus-is-running)。
4. [更新反恶意软件安全智能](#update-antimalware-security-intelligence)。
5.  (根据需要) [提交示例](#submit-samples)。
6.  (根据需要) [配置自动排除](#configure-automatic-exclusions)。
7.  (仅在必要时) 将[Windows服务器设置为被动模式](#passive-mode-and-windows-server)。

## <a name="enable-the-user-interface-on-windows-server"></a>在Windows服务器上启用用户界面

> [!IMPORTANT]
> 如果使用的是 Windows Server 2012 R2，请参阅[安装Microsoft Defender for Endpoint的选项](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)。

默认情况下，Microsoft Defender 防病毒已安装并在Windows服务器上正常运行。 有时，默认情况下会安装用户界面 (GUI) 。 GUI 不是必需的;可以使用 PowerShell、组策略 或其他方法来管理Microsoft Defender 防病毒。 但是，许多组织更喜欢将 GUI 用于Microsoft Defender 防病毒。 若要安装 GUI，请使用下表中的其中一个过程：

| Procedure | 需执行的操作 |
|:---|:---|
| 使用"添加角色和功能向导"打开 GUI | 1.使用 ["添加角色和功能向导"查看"安装角色、角色服务和功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)"，并使用 **"添加角色和功能向导**"。 <br/><br/>2. 转到向导的 **"功能**"步骤时，**请在Windows Defender"功能**"下，选择 **"Windows Defender"选项的 GUI**。 |
| 使用 PowerShell 打开 GUI | 1. 在Windows服务器上，以管理员身份打开Windows PowerShell。 <br/><br/>2. 运行以下 PowerShell cmdlet： `Install-WindowsFeature -Name Windows-Defender-GUI` |

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>在 Windows Server 上安装Microsoft Defender 防病毒

如果需要在Windows服务器上安装或重新安装Microsoft Defender 防病毒，请使用下表中的其中一个过程：

| Procedure | 需执行的操作 |
|:---|:---|
| 使用"添加角色和功能向导"安装Microsoft Defender 防病毒 | 1.请参阅 ["安装或卸载角色"、"角色服务"或"功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)"，并使用 **"添加角色和功能向导**"。 <br/><br/>2. 转到向导的 **"功能**"步骤时，选择Microsoft Defender 防病毒选项。 另请选择 **gui for Windows Defender** 选项。 |
| 使用 PowerShell 安装Microsoft Defender 防病毒 | 1. 在Windows服务器上，以管理员身份打开Windows PowerShell。 <br/><br/>2. 运行以下 PowerShell cmdlet： `Install-WindowsFeature -Name Windows-Defender` |

> [!NOTE]
> 可在Microsoft Defender 防病毒事件中找到包含在Microsoft Defender 防病毒中的反恶意软件引擎[的事件](troubleshoot-microsoft-defender-antivirus.md)消息。

## <a name="verify-microsoft-defender-antivirus-is-running"></a>验证Microsoft Defender 防病毒是否正在运行

安装 (或重新安装) Microsoft Defender 防病毒后，下一步是验证它是否正在运行。 使用下表中的 PowerShell cmdlet：

| Procedure | PowerShell cmdlet |
|:---|:---|
| 验证Microsoft Defender 防病毒是否正在运行 | `Get-Service -Name windefend` |
| 验证是否已启用防火墙保护 | `Get-Service -Name mpssvc` |

作为 PowerShell 的替代方法，可以使用命令提示符来验证Microsoft Defender 防病毒是否正在运行。 为此，请从命令提示符运行以下命令：

```cmd
sc query Windefend
```

该`sc query`命令返回有关Microsoft Defender 防病毒服务的信息。 运行Microsoft Defender 防病毒时，将显示`RUNNING`该`STATE`值。

若要查看未运行的所有服务，请运行以下 PowerShell cmdlet：

```cmd
sc query state= all
```

## <a name="update-antimalware-security-intelligence"></a>更新反恶意软件安全智能

若要获取常规的安全智能更新，必须运行Windows 更新服务。 如果使用更新管理服务（如 Windows Server Update Services (WSUS) ），请确保针对所管理的计算机批准Microsoft Defender 防病毒安全智能的更新。

默认情况下，Windows 更新不会在 Windows Server 2019 或 Windows Server 2022 或 Windows Server 2016 上自动下载和安装更新。 可以使用以下方法之一更改此配置：

| 方法 | 说明 |
|---|---|
| **控制面板** 中的Windows 更新 | **安装更新会自动** 安装所有更新，包括Windows Defender安全智能更新。 <br/><br/> **下载更新，但让我选择是否安装这些更新** 允许Windows Defender自动下载和安装安全智能更新，但不会自动安装其他更新。 |
| **组策略** | 可以在以下路径中使用组策略中提供的设置来设置和管理Windows 更新：**管理模板\Windows组件\Windows 更新\配置自动更新** |
| **AUOptions** 注册表项 | 以下两个值允许Windows 更新自动下载和安装安全智能更新： <br/><br/> **4** - **自动安装更新**。 此值会导致自动安装所有更新，包括Windows Defender安全智能更新。 <br/><br/> **3** - **下载更新，但让我选择是否安装更新**。 此值允许Windows Defender自动下载和安装安全智能更新，但不会自动安装其他更新。 |

若要确保维护恶意软件保护，请启用以下服务：

- Windows 错误报告服务
- Windows 更新服务

下表列出了Microsoft Defender 防病毒服务和依赖服务。

| 服务名称 | 文件位置 | 说明 |
|---|---|---|
| Windows Defender服务 (WinDefend)  | `C:\Program Files\Windows Defender\MsMpEng.exe` | 这是需要始终运行的主要Microsoft Defender 防病毒服务。|
| Windows 错误报告服务 (Wersvc)  | `C:\WINDOWS\System32\svchost.exe -k WerSvcGroup` | 此服务将错误报告发送回 Microsoft。 |
| Windows Defender防火墙 (MpsSvc)  | `C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork` | 建议保持启用Windows Defender防火墙服务。 |
| Windows 更新 (wuauserv)  | `C:\WINDOWS\system32\svchost.exe -k netsvcs`| 需要Windows 更新才能获取安全智能更新和反恶意软件引擎更新 |

## <a name="submit-samples"></a>提交示例

示例提交允许 Microsoft 收集潜在恶意软件的示例。 为了帮助提供持续和最新的保护，Microsoft 研究人员使用这些示例来分析可疑活动并生成更新的反恶意软件安全智能。 我们收集程序可执行文件，例如.exe文件和.dll文件。 我们不收集包含个人数据的文件，例如Microsoft Word文档和 PDF 文件。

### <a name="submit-a-file"></a>提交文件

1. 查看 [提交指南](/windows/security/threat-protection/intelligence/submission-guide)。

2. 访问 [示例提交门户](https://www.microsoft.com/wdsi/filesubmission)并提交文件。

### <a name="enable-automatic-sample-submission"></a>启用自动示例提交

若要启用自动示例提交，请以管理员身份启动Windows PowerShell控制台，并根据以下设置之一设置 **SubmitSamplesConsent** 值数据：

|设置|说明|
|---|---|
| **0** - **始终提示** | Microsoft Defender 防病毒服务会提示你确认提交所有必需的文件。 这是Microsoft Defender 防病毒的默认设置，但不建议在 Windows Server 2016 或 2019 上安装，也不建议在没有 GUI 的情况下Windows服务器 2022。 |
| **1**  - **自动发送安全示例** | Microsoft Defender 防病毒服务发送标记为"安全"的所有文件，并提示其余文件。 |
| **2** - **从不发送** | Microsoft Defender 防病毒服务不会提示，也不会发送任何文件。 |
| **3** - **自动发送所有示例** | Microsoft Defender 防病毒服务发送所有文件，但未提示确认。 |

> [!NOTE]
> 此选项不适用于 Windows Server 2012 R2。 

## <a name="configure-automatic-exclusions"></a>配置自动排除项

为了帮助确保安全性和性能，根据在 Windows Server 2016 或 2019 或 Windows Server 2022 上使用Microsoft Defender 防病毒时安装的角色和功能自动添加某些排除项。

请参阅[Windows服务器上的Microsoft Defender 防病毒中配置排除项](configure-server-exclusions-microsoft-defender-antivirus.md)。

## <a name="passive-mode-and-windows-server"></a>被动模式和Windows服务器

如果在Windows服务器上使用非 Microsoft 防病毒产品作为主要防病毒解决方案，则必须将Microsoft Defender 防病毒设置为被动模式或禁用模式。 如果Windows服务器终结点已载入到Microsoft Defender for Endpoint，则可以将Microsoft Defender 防病毒设置为被动模式。 如果不使用Microsoft Defender for Endpoint，请将Microsoft Defender 防病毒设置为禁用模式。 

> [!TIP]
> 请参阅[Microsoft Defender 防病毒与其他安全产品的兼容性](microsoft-defender-antivirus-compatibility.md)。

下表介绍了将Microsoft Defender 防病毒设置为被动模式、禁用Microsoft Defender 防病毒和卸载Microsoft Defender 防病毒的方法：

| Procedure | 说明 |
|---|---|
| 使用注册表项将Microsoft Defender 防病毒设置为被动模式 | 按如下所示设置 ForceDefenderPassiveMode 注册表项： <br/>- 路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` <br/>- 名称： `ForceDefenderPassiveMode` <br/>- 类型： `REG_DWORD` <br/>- 值： `1` |
| 使用 PowerShell 关闭Microsoft Defender 防病毒用户界面 | 以管理员身份打开Windows PowerShell，并运行以下 PowerShell cmdlet：`Uninstall-WindowsFeature -Name Windows-Defender-GUI`
| 使用 PowerShell 禁用Microsoft Defender 防病毒 | 使用以下 PowerShell cmdlet： `Set-MpPreference -DisableRealtimeMonitoring $true` |
| 使用"删除角色和功能"向导禁用Microsoft Defender 防病毒 | 请参阅 ["安装或卸载角色"、"角色服务"或"功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)"，并使用 **"删除角色和功能向导**"。 <br/><br/>转到向导的 **"功能**"步骤时，请清除 **Windows Defender功能** 选项。 <br/><br/> 如果 **在"Windows Defender** 功能"部分下自行清除 **Windows Defender**，系统会提示删除 **Windows Defender的** 接口选项 GUI。<br/><br/>如果没有用户界面，Microsoft Defender 防病毒仍会正常运行，但如果禁用核心 **Windows Defender** 功能，则无法启用用户界面。 |
| 使用 PowerShell 卸载Microsoft Defender 防病毒 | 使用以下 PowerShell cmdlet： `Uninstall-WindowsFeature -Name Windows-Defender` |
| 使用组策略禁用Microsoft Defender 防病毒 | 在本地组策略编辑器中，导航到管理 **模板** > **Windows组件** > **Endpoint Protection** > **可视化Endpoint Protection**，然后选择 **EnabledOK** > 。 |

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>是使用 Windows Server 2012 R2 还是Windows Server 2016？

如果Windows服务器载入到Microsoft Defender for Endpoint，现在可以在 Windows Server 2012 R2 和 Windows Server 2016 上以被动模式运行Microsoft Defender 防病毒。 另请参阅以下文章：

- [安装Microsoft Defender for Endpoint的选项](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)

- [Microsoft Defender 防病毒与其他安全产品的兼容性](microsoft-defender-antivirus-compatibility.md)

## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-windows.md)

