---
title: Windows Server 上的 Microsoft Defender 防病毒软件
description: 了解如何在 Windows Server 2016 和 Windows Server 2019 上启用和配置 Microsoft Defender 防病毒。
keywords: windows defender， 服务器， scep， system center endpoint protection， server 2016， current branch， server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269488"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上的 Microsoft Defender 防病毒软件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Windows Server 的以下版本/版本上提供了 Microsoft Defender 防病毒：
- Windows Server 2019
- Windows Server 版本 1803 或更高版本
- Windows Server 2016。 

在某些情况下，Microsoft Defender 防病毒称为 Endpoint *Protection*;但是，保护引擎是相同的。 尽管 [Windows 10](microsoft-defender-antivirus-in-windows-10.md)上的 Microsoft Defender 防病毒的功能、配置和管理基本相同，但 Windows Server 上有几个主要区别：

- 在 Windows Server [上，](configure-server-exclusions-microsoft-defender-antivirus.md) 根据定义的服务器角色应用自动排除项。
 
- 在 Windows Server 上，如果运行的是非 Microsoft 防病毒/反恶意软件解决方案，Microsoft Defender 防病毒不会自动进入被动模式或禁用模式。 但是，你可以手动将 Microsoft Defender 防病毒设置为被动或禁用模式。

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>在 Windows Server 上设置 Microsoft Defender 防病毒

在服务器平台上设置和运行 Microsoft Defender 防病毒的过程包括几个步骤：

1. [启用接口](#enable-the-user-interface-on-windows-server)。
2. [安装 Microsoft Defender 防病毒](#install-microsoft-defender-antivirus-on-windows-server)。
3. [验证 Microsoft Defender 防病毒是否正在运行](#verify-microsoft-defender-antivirus-is-running)。
4. [更新反恶意软件安全智能](#update-antimalware-security-intelligence)。
5.  (根据需要) [提交示例。](#submit-samples)
6.  (根据需要) [配置自动排除项](#configure-automatic-exclusions)。
7.  (仅在必要) [将 Microsoft Defender 防病毒设置为被动模式](#need-to-set-microsoft-defender-antivirus-to-passive-mode)。

## <a name="enable-the-user-interface-on-windows-server"></a>在 Windows Server 上启用用户界面

默认情况下，Microsoft Defender 防病毒已安装且在 Windows Server 上正常运行。 有时，用户界面会 (GUI) 安装，但不需要 GUI。 可以使用 PowerShell、组策略或其他方法来管理 Microsoft Defender 防病毒。 

如果服务器上未安装 GUI，并且要安装 GUI，则使用"添加角色 **和功能** "向导或 PowerShell cmdlet。

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>使用添加角色和功能向导打开 GUI

1. 请参阅 [使用添加角色和功能向导](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)安装角色、角色服务和功能，并使用 **添加角色和功能向导**。

2. 当您进入向导的 **"功能** "步骤时，在"Windows Defender **功能"** 下，选择 **"Windows Defender** GUI"选项。

   在 Windows Server 2016 中，添加 **角色和功能向导** 如下所示：

   ![添加显示选项 GUI 的角色Windows Defender向导](images/server-add-gui.png)

   在 Windows Server 2019 中，添加 **角色和功能向导** 类似。

### <a name="turn-on-the-gui-using-powershell"></a>使用 PowerShell 打开 GUI

以下 PowerShell cmdlet 将启用该接口： 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>在 Windows Server 上安装 Microsoft Defender 防病毒

如果你需要在 Windows Server 上安装或重新安装 Microsoft Defender 防病毒，可以使用添加角色 **和功能** 向导或 PowerShell 来这样做。

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>使用添加角色和功能向导安装 Microsoft Defender 防病毒

1. 请参阅 [本文 ，并使用](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)添加 **角色和功能向导**。

2. 当你进入向导的 **"功能"** 步骤时，选择"Microsoft Defender 防病毒"选项。 另外，选择 **"用于Windows Defender** GUI"选项。

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>使用 PowerShell 安装 Microsoft Defender 防病毒

若要使用 PowerShell 安装 Microsoft Defender 防病毒，请运行以下 cmdlet：

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

Microsoft Defender 防病毒中包含的反恶意软件引擎的事件消息可以在 [Microsoft Defender AV 事件找到](troubleshoot-microsoft-defender-antivirus.md)。


## <a name="verify-microsoft-defender-antivirus-is-running"></a>验证 Microsoft Defender 防病毒是否正在运行

安装 Microsoft Defender 防病毒后，下一步是验证其是否正在运行。 在 Windows Server 终结点上，运行以下 PowerShell cmdlet：

```PowerShell
Get-Service -Name windefend
```

若要验证防火墙保护是否打开，请运行以下 PowerShell cmdlet：

```PowerShell 
Get-Service -Name mpssvc
```

作为 PowerShell 的替代方法，可以使用命令提示符验证 Microsoft Defender 防病毒是否正在运行。 为此，请从命令提示符运行以下命令： 

```console
sc query Windefend
```

该命令 `sc query` 返回有关 Microsoft Defender 防病毒服务的信息。 当 Microsoft Defender 防病毒正在运行时， `STATE` 值将显示 `RUNNING` 。

## <a name="update-antimalware-security-intelligence"></a>更新反恶意软件安全智能 

若要获取更新的反恶意软件安全智能，必须运行 Windows 更新服务。 如果使用更新管理服务，如 Windows Server Update Services (WSUS) ，请确保已针对你管理的计算机批准 Microsoft Defender 防病毒安全智能的更新。

默认情况下，Windows 更新不会在 Windows Server 2019 或 Windows Server 2016 上自动下载和安装更新。 可以使用以下方法之一更改此配置：


|方法  |说明  |
|---------|---------|
|**控制面板中的 Windows** 更新     |- **自动安装更新** 会导致自动安装所有更新，Windows Defender安全智能更新。 <br/>- **下载更新，但允许我** 选择是否安装它们Windows Defender自动下载和安装安全智能更新，但不会自动安装其他更新。       |
|**组策略**     | 可以通过以下路径中的组策略中提供的设置来设置和管理 Windows **更新：管理模板\Windows 组件\Windows 更新\配置自动更新**         |
|**AUOptions** 注册表项     |以下两个值允许 Windows 更新自动下载和安装安全智能更新： <br/>- **4**  - **自动安装更新**。 此值会导致自动安装所有更新，包括Windows Defender更新。 <br/>- **3**  - **下载更新，但允许我选择是否安装它们**。  此值允许Windows Defender下载和安装安全智能更新，但不会自动安装其他更新。         |

为了确保对恶意软件的保护得到维护，我们建议您启用以下服务：

- Windows 错误报告服务

- Windows 更新服务

下表列出了 Microsoft Defender 防病毒的服务和从属服务。

|服务名称|文件位置|说明|
|--------|---------|--------|
|Windows Defender Service (WinDefend) |`C:\Program Files\Windows Defender\MsMpEng.exe`|这是需要一定时间运行的主要 Microsoft Defender 防病毒服务。|
|Windows 错误报告服务 (Wersvc) |`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|此服务将错误报告发送回 Microsoft。|
|Windows Defender MpsSvc (防火墙) |`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|我们建议使防火墙Windows Defender启用。|
|Windows 更新 (Wuauserv) |`C:\WINDOWS\system32\svchost.exe -k netsvcs`|需要 Windows 更新才能获取安全智能更新和反恶意软件引擎更新|

## <a name="submit-samples"></a>提交示例

示例提交允许 Microsoft 收集潜在恶意软件的示例。 为了帮助提供持续且最新的保护，Microsoft 研究人员使用这些示例来分析可疑活动并生成更新的反恶意软件安全智能。 我们收集程序可执行文件，例如.exe文件.dll文件。 我们不会收集包含个人数据的文件，如 Microsoft Word 文档和 PDF 文件。

### <a name="submit-a-file"></a>提交文件

1. 查看 [提交指南](/windows/security/threat-protection/intelligence/submission-guide)。

2. 访问 [示例提交门户 ，](https://www.microsoft.com/wdsi/filesubmission)并提交你的文件。


### <a name="enable-automatic-sample-submission"></a>启用自动提交示例

若要启用自动示例提交，请以管理员Windows PowerShell启动示例提交控制台，然后根据以下设置之一设置 **SubmitSamplesConsent** 值数据：

|设置  |说明  |
|---------|---------|
|**0**  - **始终提示**     |Microsoft Defender 防病毒服务会提示你确认提交所有必需文件。 这是 Microsoft Defender 防病毒的默认设置，但不建议在没有 GUI 的情况下在 Windows Server 2016 或 2019 上安装。         |
|**1**   - **自动发送安全示例**     |Microsoft Defender 防病毒服务发送标记为"安全"的所有文件，并提示输入其余文件。         |
|**2**  - **从不发送**      |Microsoft Defender 防病毒服务不提示也不发送任何文件。         |
|**3**  - **自动发送所有示例**     |Microsoft Defender 防病毒服务发送所有文件，而不提示确认。         |

## <a name="configure-automatic-exclusions"></a>配置自动排除项

为了帮助确保安全性和性能，某些排除项根据你在 Windows Server 2016 或 2019 上使用 Microsoft Defender 防病毒时安装的角色和功能自动添加。

请参阅 [在 Windows Server 上配置 Microsoft Defender 防病毒中的排除项](configure-server-exclusions-microsoft-defender-antivirus.md)。 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>需要将 Microsoft Defender 防病毒设置为被动模式？

如果你使用非 Microsoft 防病毒产品作为 Windows Server 上的主要防病毒解决方案，则必须将 Microsoft Defender 防病毒设置为被动模式或禁用模式。

- 在 Windows Server 版本 1803 或更高版本或 Windows Server 2019 上，可以将 Microsoft Defender 防病毒设置为被动模式。  

- 在 Windows Server 2016 上，Microsoft Defender 防病毒与非 Microsoft 防病毒/反恶意软件产品一起不受支持。 在这些情况下，必须将 Microsoft Defender 防病毒设置为禁用模式。

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a>使用 PowerShell 将 Microsoft Defender 防病毒设置为被动模式

如果你使用的是 Windows Server 版本 1803 或 Windows Server 2019，可以使用以下 PowerShell cmdlet 将 Microsoft Defender 防病毒设置为被动模式：

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a>使用组策略将 Microsoft Defender 防病毒设置为被动模式

所需的过程

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>使用注册表项将 Microsoft Defender 防病毒设置为被动模式

如果你使用的是 Windows Server 版本 1803 或 Windows Server 2019，可以通过设置以下注册表项将 Microsoft Defender 防病毒设置为被动模式：
- 路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名称：`ForceDefenderPassiveMode`
- 类型： `REG_DWORD`
- 值：`1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>使用"删除角色和功能"向导禁用 Microsoft Defender 防病毒

1. 请参阅 [安装或卸载角色、角色服务或功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)，并使用 **删除角色和功能向导**。 

2. 当您进入向导的 **"功能**"步骤时，请清除"Windows Defender"选项。  

    如果在 **"Windows Defender** 功能"部分下自行清除 **Windows Defender，** 系统将提示您删除"Windows Defender"**的界面选项 GUI。** 
    
    Microsoft Defender 防病毒在没有用户界面的情况下仍可以正常运行，但如果禁用核心防病毒功能，将无法 **Windows Defender** 用户界面。

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>使用 PowerShell 关闭 Microsoft Defender 防病毒用户界面

若要关闭 Microsoft Defender 防病毒 GUI，请使用以下 PowerShell cmdlet：

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>是否正在使用 Windows Server 2016？

如果你使用的是 Windows Server 2016 以及 Microsoft 未提供或开发的第三方反恶意软件/防病毒产品，则需要禁用/卸载 Microsoft Defender 防病毒。 

> [!NOTE]
> 无法卸载 Windows 安全应用，但可以使用以下说明禁用界面。

以下 PowerShell cmdlet 卸载 Windows Server 2016 上的 Microsoft Defender 防病毒：

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

若要在 Windows Server 2016 上禁用 Microsoft Defender 防病毒，请使用以下 PowerShell cmdlet：

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md)
