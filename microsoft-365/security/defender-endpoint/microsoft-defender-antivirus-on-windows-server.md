---
title: Windows Server 上的 Microsoft Defender 防病毒软件
description: 了解如何在 Microsoft Defender 防病毒 Server 2019 Windows Server 2016 Windows Server 2022 上启用和配置 Windows。
keywords: windows defender， 服务器， scep， system center endpoint protection， server 2016， current branch， server 2012
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
ms.openlocfilehash: 412033e274cce22b9350292c612b91ef6e34e209
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634836"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上的 Microsoft Defender 防病毒软件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender 防病毒以下版本的 Windows Server 中提供：

- Windows Server 2022
- Windows Server 2019
- Windows Server 版本 1803 或更高版本
- Windows Server 2016
- Windows Server 2012 R2 (需要Microsoft Defender for Endpoint) 

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>在 Microsoft Defender 防病毒 服务器上Windows服务器

在 Microsoft Defender 防病毒 Server 上Windows和运行应用程序的过程包括以下步骤：

1. [启用接口](#enable-the-user-interface-on-windows-server)。
2. [安装Microsoft Defender 防病毒](#install-microsoft-defender-antivirus-on-windows-server)。
3. [验证Microsoft Defender 防病毒是否正在运行](#verify-microsoft-defender-antivirus-is-running)。
4. [更新反恶意软件安全智能](#update-antimalware-security-intelligence)。
5.  (根据需要) [提交示例。](#submit-samples)
6.  (根据需要) [配置自动排除项](#configure-automatic-exclusions)。
7.  (仅在必要) 将Windows[服务器设置为被动模式](#passive-mode-and-windows-server)。

## <a name="enable-the-user-interface-on-windows-server"></a>在 Windows 服务器上启用用户界面

> [!IMPORTANT]
> 如果你使用的是 R2 Windows Server 2012，请参阅[安装 Microsoft Defender for Endpoint](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)。

默认情况下，Microsoft Defender 防病毒服务器上已安装并Windows功能。 有时，默认情况下会 (用户界面) 用户界面。 GUI 不是必需的;可以使用 PowerShell、组策略或其他方法来管理Microsoft Defender 防病毒。 但是，许多组织倾向于将 GUI 用于Microsoft Defender 防病毒。 若要安装 GUI，请使用下表中的过程之一：

| Procedure | 需执行的操作 |
|:---|:---|
| 使用添加角色和功能向导打开 GUI | 1. 请参阅 [使用](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)添加角色和功能向导安装角色、角色服务和功能，并使用 **添加角色和功能向导**。 <br/><br/>2. 当您进入向导的"功能"步骤时，在"Windows Defender **"下**，选择"**Windows Defender** GUI"选项。 |
| 使用 PowerShell 打开 GUI | 1. 在 Windows 服务器上，Windows PowerShell管理员打开" <br/><br/>2. 运行以下 PowerShell cmdlet： `Install-WindowsFeature -Name Windows-Defender-GUI` |

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>在 Microsoft Defender 防病毒 服务器上Windows服务器

如果需要在 Microsoft Defender 防病毒 Server Windows或重新安装安装程序，请使用下表中的以下过程之一：

| Procedure | 需执行的操作 |
|:---|:---|
| 使用添加角色和功能向导安装Microsoft Defender 防病毒 | 1. 请参阅 [安装或卸载角色、角色服务或功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)，并使用 **添加角色和功能向导**。 <br/><br/>2. 当您进入向导的 **"功能**"步骤时，选择"Microsoft Defender 防病毒选项。 另外，选择 **"Windows Defender** GUI"选项。 |
| 使用 PowerShell 安装Microsoft Defender 防病毒 | 1. 在 Windows 服务器上，Windows PowerShell管理员打开" <br/><br/>2. 运行以下 PowerShell cmdlet： `Install-WindowsFeature -Name Windows-Defender` |

> [!NOTE]
> 可以在"事件"中Microsoft Defender 防病毒反恶意软件引擎[Microsoft Defender 防病毒消息](troubleshoot-microsoft-defender-antivirus.md)。

## <a name="verify-microsoft-defender-antivirus-is-running"></a>验证Microsoft Defender 防病毒是否正在运行

安装或重新安装 () Microsoft Defender 防病毒，下一步是验证它是否正在运行。 使用下表中的 PowerShell cmdlet：

| Procedure | PowerShell cmdlet |
|:---|:---|
| 验证Microsoft Defender 防病毒正在运行 | `Get-Service -Name windefend` |
| 验证防火墙保护是否打开 | `Get-Service -Name mpssvc` |

作为 PowerShell 的替代方法，可以使用命令提示符验证Microsoft Defender 防病毒运行。 为此，请从命令提示符运行以下命令：

```cmd
sc query Windefend
```

该命令`sc query`返回有关 Microsoft Defender 防病毒 的信息。 当Microsoft Defender 防病毒运行时，值`STATE`将显示 `RUNNING`。

若要查看所有未运行的服务，请运行以下 PowerShell cmdlet：

```cmd
sc query state= all
```

## <a name="update-antimalware-security-intelligence"></a>更新反恶意软件安全智能

若要获取常规安全智能更新，Windows 更新服务必须正在运行。 如果使用更新管理服务（如 Windows Server Update Services (WSUS) ，请确保已针对你管理的计算机批准 Microsoft Defender 防病毒 安全智能的更新。

默认情况下，Windows 更新 Server 2019 或 Windows Windows Server 2022 或 Windows Server 2016 自动下载和安装更新。 可以使用以下方法之一更改此配置：

| 方法 | 说明 |
|---|---|
| **Windows 更新** 控制面板 | **自动安装更新** 会导致自动安装所有更新，Windows Defender安全智能更新。 <br/><br/> **下载更新，但允许我** 选择是否安装它们Windows Defender自动下载和安装安全智能更新，但不会自动安装其他更新。 |
| **组策略** | 您可以使用 组策略 中提供的设置设置和管理 Windows 更新，路径如下：**管理模板\Windows 组件\Windows 更新\配置自动更新** |
| **AUOptions** 注册表项 | 以下两个值允许Windows 更新下载并安装安全智能更新： <br/><br/> **4** - **自动安装更新**。 此值会导致自动安装所有更新，包括Windows Defender更新。 <br/><br/> **3** - **下载更新，但允许我选择是否安装它们**。 此值允许Windows Defender下载和安装安全智能更新，但不会自动安装其他更新。 |

若要确保保持对恶意软件的保护，请启用以下服务：

- Windows 错误报告服务
- Windows 更新服务

下表列出了服务相关的Microsoft Defender 防病毒服务。

| 服务名称 | 文件位置 | 说明 |
|---|---|---|
| Windows Defender Service (WinDefend)  | `C:\Program Files\Windows Defender\MsMpEng.exe` | 这是需要始终Microsoft Defender 防病毒的主要服务。|
| Windows 错误报告 Service (Wersvc)  | `C:\WINDOWS\System32\svchost.exe -k WerSvcGroup` | 此服务将错误报告发送回 Microsoft。 |
| Windows Defender MpsSvc (防火墙)  | `C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork` | 我们建议保持启用Windows Defender防火墙服务。 |
| Windows 更新 (Wuauserv)  | `C:\WINDOWS\system32\svchost.exe -k netsvcs`| Windows 更新安全智能更新和反恶意软件引擎更新时需要此组件 |

## <a name="submit-samples"></a>提交示例

示例提交允许 Microsoft 收集潜在恶意软件的示例。 为了帮助提供持续且最新的保护，Microsoft 研究人员使用这些示例来分析可疑活动并生成更新的反恶意软件安全智能。 我们收集程序可执行文件，例如.exe文件和.dll文件。 我们不会收集包含个人数据的文件，例如Microsoft Word和 PDF 文件。

### <a name="submit-a-file"></a>提交文件

1. 查看 [提交指南](/windows/security/threat-protection/intelligence/submission-guide)。

2. 访问 [示例提交门户，](https://www.microsoft.com/wdsi/filesubmission)并提交文件。

### <a name="enable-automatic-sample-submission"></a>启用自动提交示例

若要启用自动示例提交，请以管理员Windows PowerShell启动一个自定义控制台，然后根据以下设置之一设置 **SubmitSamplesConsent** 值数据：

|设置|说明|
|---|---|
| **0** - **始终提示** | the Microsoft Defender 防病毒 service prompts you to confirm submission of all required files. 这是 Microsoft Defender 防病毒 的默认设置，但不建议在 Windows Server 2016 或 2019 或 Windows Server 2022 上安装不带 GUI。 |
| **1**  - **自动发送安全示例** | 该服务Microsoft Defender 防病毒发送标记为"安全"的所有文件，并提示您输入其余文件。 |
| **2** - **从不发送** | the Microsoft Defender 防病毒 service doesn't prompt and doesn't send any files. |
| **3** - **自动发送所有示例** | 该服务Microsoft Defender 防病毒发送所有文件，而不提示确认。 |

> [!NOTE]
> 此选项不适用于 Windows Server 2012 R2。 

## <a name="configure-automatic-exclusions"></a>配置自动排除项

为了帮助确保安全性和性能，根据在 Windows Server 2016 或 Windows Server 2016 Server 2022 或 Windows Server 2022 上使用 Microsoft Defender 防病毒 时安装的角色和功能，会自动添加某些排除项。

请参阅 [Configure exclusions in Microsoft Defender 防病毒 on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)。

## <a name="passive-mode-and-windows-server"></a>被动模式和Windows服务器

如果你使用非 Microsoft 防病毒产品作为 Windows Server 上的主要防病毒解决方案，则必须Microsoft Defender 防病毒被动模式或禁用模式。 如果你的 Windows Server 终结点已载入Microsoft Defender for Endpoint，你可以将Microsoft Defender 防病毒设置为被动模式。 如果不使用"已禁用Microsoft Defender for Endpoint，Microsoft Defender 防病毒禁用模式。 

> [!TIP]
> 请参阅[Microsoft Defender 防病毒安全产品的兼容性](microsoft-defender-antivirus-compatibility.md)。

下表介绍了用于将Microsoft Defender 防病毒被动模式、禁用Microsoft Defender 防病毒和卸载Microsoft Defender 防病毒：

| Procedure | 说明 |
|---|---|
| 使用Microsoft Defender 防病毒设置被动模式 | 按如下所示设置 ForceDefenderPassiveMode 注册表项： <br/>- 路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` <br/>- 名称： `ForceDefenderPassiveMode` <br/>- 类型： `REG_DWORD` <br/>- 值： `1` |
| 使用 PowerShell Microsoft Defender 防病毒用户界面 | 以Windows PowerShell管理员角色打开"PowerShell"，然后运行以下 PowerShell cmdlet：`Uninstall-WindowsFeature -Name Windows-Defender-GUI`
| 使用 PowerShell Microsoft Defender 防病毒禁用应用程序 | 使用以下 PowerShell cmdlet： `Set-MpPreference -DisableRealtimeMonitoring $true` |
| 使用Microsoft Defender 防病毒角色和功能"向导禁用角色 | 请参阅 [安装或卸载角色、角色服务或功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)，并使用 **删除角色和功能向导**。 <br/><br/>当您进入向导的 **"功能**"步骤时，请清除"Windows Defender **"选项**。 <br/><br/> 如果在"**Windows Defender** 功能"部分下自行清除Windows Defender **，** 系统将提示您删除用于"Windows Defender **"的界面选项 GUI**。<br/><br/>Microsoft Defender 防病毒用户界面，用户界面仍将正常运行，但如果您禁用核心用户界面功能，**Windows Defender启用。** |
| 使用 PowerShell Microsoft Defender 防病毒卸载应用程序 | 使用以下 PowerShell cmdlet： `Uninstall-WindowsFeature -Name Windows-Defender` |
| 使用Microsoft Defender 防病毒禁用组策略 | In your Local 组策略 Editor， navigate to **Administrative Template** >  **Windows Component** >  **Endpoint Protection** >  **Disable Endpoint Protection**， and then select **EnabledOK** > . |

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>是否正在使用 Windows Server 2012 R2 或 Windows Server 2016？

如果你的 Windows 服务器已载入Microsoft Defender for Endpoint，你现在可以在 Microsoft Defender 防病毒 R2 和 Windows Server 2016 上以被动Windows Server 2012运行 Windows Server 2016。 另请参阅以下文章：

- [用于安装Microsoft Defender for Endpoint](configure-server-endpoints.md#options-to-install-the-microsoft-defender-for-endpoint-packages)

- [Microsoft Defender 防病毒安全产品的兼容性](microsoft-defender-antivirus-compatibility.md)

## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-windows.md)

