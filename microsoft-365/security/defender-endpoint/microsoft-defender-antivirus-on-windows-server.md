---
title: Windows Server 上的 Microsoft Defender 防病毒软件
description: 了解如何在 Microsoft Defender 防病毒 Server 2019 Windows Server 2016 Windows Server 2022 Windows和配置应用程序。
keywords: windows defender， 服务器， scep， system center endpoint protection， server 2016， current branch， server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 08/05/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: df73543f0aaf5ac03508e6239e850f7a8d3034c9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210945"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上的 Microsoft Defender 防病毒软件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防病毒以下版本/版本的 Windows Server 上提供：

- Windows Server 2019
- Windows Server 2022
- Windows服务器版本 1803 或更高版本
- Windows Server 2016。

在某些情况下，Microsoft Defender 防病毒称为 *"Endpoint Protection";* 但是，保护引擎是相同的。 尽管 Microsoft Defender 防病毒 上的配置和管理基本相同Windows 10，但 Windows [](microsoft-defender-antivirus-in-windows-10.md)Server 上存在一些关键差异：

- 在 Windows 服务器上，[根据](configure-server-exclusions-microsoft-defender-antivirus.md)定义的服务器角色应用自动排除项。

- 在 Windows 服务器上，如果运行的是非 Microsoft 防病毒/反恶意软件解决方案，Microsoft Defender 防病毒不会自动进入被动模式或禁用模式。 但是，你可以手动Microsoft Defender 防病毒被动或禁用模式。

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>在 Microsoft Defender 防病毒 服务器上Windows服务器

在服务器平台上设置和运行Microsoft Defender 防病毒包括几个步骤：

1. [启用接口](#enable-the-user-interface-on-windows-server)。
2. [安装 Microsoft Defender 防病毒](#install-microsoft-defender-antivirus-on-windows-server)。
3. [验证Microsoft Defender 防病毒是否正在运行](#verify-microsoft-defender-antivirus-is-running)。
4. [更新反恶意软件安全智能](#update-antimalware-security-intelligence)。
5.  (根据需要) [提交示例。](#submit-samples)
6.  (根据需要) [配置自动排除项](#configure-automatic-exclusions)。
7.  (仅在必要) 将Windows[服务器设置为被动模式。](#passive-mode-and-windows-server)

## <a name="enable-the-user-interface-on-windows-server"></a>在 Windows 服务器上启用用户界面

默认情况下，Microsoft Defender 防病毒服务器上安装并Windows功能。 有时，默认情况下会 (GUI) 用户界面，但不需要 GUI。 可以使用 PowerShell、组策略或其他方法来管理Microsoft Defender 防病毒。

如果服务器上未安装 GUI，并且要安装 GUI，则使用"添加角色 **和功能** "向导或 PowerShell cmdlet。

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>使用添加角色和功能向导打开 GUI

1. 请参阅 [使用添加角色和功能向导](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)安装角色、角色服务和功能，并使用 **添加角色和功能向导**。

2. 当您进入向导的"**功能**"步骤时，在"Windows Defender **功能"** 下，选择 **"Windows Defender** GUI"选项。

   在Windows Server 2016中，添加 **角色和功能向导** 如下所示：

   ![添加显示选项的 GUI 的角色Windows Defender向导。](images/server-add-gui.png)

   在 Windows Server 2019 和 Windows Server 2022中，"添加角色"和"功能向导"类似。

### <a name="turn-on-the-gui-using-powershell"></a>使用 PowerShell 打开 GUI

以下 PowerShell cmdlet 将启用该接口：

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>在 Microsoft Defender 防病毒 服务器上Windows服务器

如果需要在 Microsoft Defender 防病毒 服务器上安装或重新安装Windows，可以使用"添加角色 **和功能** 向导"或 PowerShell 完成这一操作。

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>使用添加角色和功能向导安装Microsoft Defender 防病毒

1. 请参阅 [本文 ，并使用](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)添加 **角色和功能向导**。

2. When you get to the **Features** step of the wizard， select the Microsoft Defender 防病毒 option. 另外，为"**用户"选项Windows Defender** GUI。

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>使用 PowerShell 安装Microsoft Defender 防病毒

若要使用 PowerShell 安装Microsoft Defender 防病毒，请运行以下 cmdlet：

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

Microsoft Defender AV 事件 Microsoft Defender 防病毒包含的反恶意软件引擎[的事件消息](troubleshoot-microsoft-defender-antivirus.md)。

## <a name="verify-microsoft-defender-antivirus-is-running"></a>验证Microsoft Defender 防病毒是否正在运行

安装Microsoft Defender 防病毒后，下一步是验证它是否正在运行。 在 Windows Server 终结点上，运行以下 PowerShell cmdlet：

```PowerShell
Get-Service -Name windefend
```

若要验证防火墙保护是否打开，请运行以下 PowerShell cmdlet：

```PowerShell
Get-Service -Name mpssvc
```

作为 PowerShell 的替代方法，可以使用命令提示符验证Microsoft Defender 防病毒运行。 为此，请从命令提示符运行以下命令：

```console
sc query Windefend
```

该命令 `sc query` 返回有关 Microsoft Defender 防病毒 的信息。 当Microsoft Defender 防病毒运行时，值 `STATE` 将显示 `RUNNING` 。

## <a name="update-antimalware-security-intelligence"></a>更新反恶意软件安全智能

若要获取更新的反恶意软件安全智能，必须运行Windows更新服务。 如果使用更新管理服务（如 Windows Server Update Services (WSUS) ，请确保已针对你管理的计算机Microsoft Defender 防病毒安全智能的更新。

默认情况下，Windows Update 不会在 Windows Server 2019、Windows Server 2022 或 Windows Server 2016 上自动下载和安装Windows Server 2016。 可以使用以下方法之一更改此配置：

<br/><br/>

|方法|说明|
|---|---|
|**Windows控制面板** 中的更新|**自动安装更新** 会导致自动安装所有更新，Windows Defender安全智能更新。 <p> **下载更新，但允许我** 选择是否安装它们Windows Defender自动下载和安装安全智能更新，但不会自动安装其他更新。|
|**组策略**|您可以使用组策略中提供的设置设置和管理 Windows 更新，路径如下：**管理模板\Windows 组件\Windows更新\配置自动更新**|
|**AUOptions** 注册表项|以下两个值允许Windows更新自动下载和安装安全智能更新： <p> **4**  - **自动安装更新**。 此值会导致自动安装所有更新，Windows Defender安全智能更新。 <p> **3**  - **下载更新，但允许我选择是否安装它们**。 此值允许Windows Defender下载和安装安全智能更新，但不会自动安装其他更新。|

为了确保对恶意软件的保护得到维护，我们建议您启用以下服务：

- Windows 错误报告服务
- Windows更新服务

下表列出了用于服务Microsoft Defender 防病毒服务。

<br>

****

|服务名称|文件位置|说明|
|---|---|---|
|Windows DefenderWinDefend (服务) |`C:\Program Files\Windows Defender\MsMpEng.exe`|这是需要Microsoft Defender 防病毒运行的主要服务。|
|Windows 错误报告Service (Wersvc) |`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|此服务将错误报告发送回 Microsoft。|
|Windows DefenderMpsSvc (防火墙) |`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|我们建议使防火墙Windows Defender启用。|
|Windows更新 (Wuauserv) |`C:\WINDOWS\system32\svchost.exe -k netsvcs`|Windows需要更新才能获取安全智能更新和反恶意软件引擎更新|
|

## <a name="submit-samples"></a>提交示例

示例提交允许 Microsoft 收集潜在恶意软件的示例。 为了帮助提供持续且最新的保护，Microsoft 研究人员使用这些示例来分析可疑活动并生成更新的反恶意软件安全智能。 我们收集程序可执行文件，例如.exe文件.dll文件。 我们不会收集包含个人数据的文件，如Microsoft Word和 PDF 文件。

### <a name="submit-a-file"></a>提交文件

1. 查看 [提交指南](/windows/security/threat-protection/intelligence/submission-guide)。
2. 访问 [示例提交门户 ，](https://www.microsoft.com/wdsi/filesubmission)并提交文件。

### <a name="enable-automatic-sample-submission"></a>启用自动提交示例

若要启用自动示例提交，请以管理员Windows PowerShell启动示例提交控制台，然后根据以下设置之一设置 **SubmitSamplesConsent** 值数据：

<br>

****

|设置|说明|
|---|---|
|**0**  - **始终提示**|the Microsoft Defender 防病毒 service prompts you to confirm submission of all required files. 这是 Microsoft Defender 防病毒 的默认设置，但不建议在 Windows Server 2016 或 2019 或 Windows Server 2022 上安装不带 GUI。|
|**1**   - **自动发送安全示例**|该服务Microsoft Defender 防病毒发送标记为"安全"的所有文件，并提示您输入其余文件。|
|**2**  - **从不发送**|Microsoft Defender 防病毒服务不会提示，也不发送任何文件。|
|**3**  - **自动发送所有示例**|该服务Microsoft Defender 防病毒发送所有文件，而不提示确认。|
|

## <a name="configure-automatic-exclusions"></a>配置自动排除项

为了帮助确保安全性和性能，根据在 Windows Server 2016 或 Windows Server 2016 Server 2022 或 Windows Server 2022 上使用 Microsoft Defender 防病毒 时安装的角色和功能，会自动添加某些排除项。

请参阅[Configure exclusions in Microsoft Defender 防病毒 on Windows Server。](configure-server-exclusions-microsoft-defender-antivirus.md)

## <a name="passive-mode-and-windows-server"></a>被动模式和Windows服务器

如果要将非 Microsoft 防病毒产品用作 Windows Server 上的主要防病毒解决方案，则必须Microsoft Defender 防病毒被动模式或禁用模式。

- 在 Windows Server、版本 1803 或更高版本、Windows Server 2019 或 Windows Server 2022 上，可以将 Microsoft Defender 防病毒 设置为被动模式。 请参阅以下部分：
  - [使用Microsoft Defender 防病毒将用户设置为被动模式](#set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key)
  - [使用Microsoft Defender 防病毒角色和功能向导禁用配置](#disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard)
  - [使用 PowerShell Microsoft Defender 防病毒用户界面](#turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell)

- 在Windows Server 2016，Microsoft Defender 防病毒 Microsoft 防病毒/反恶意软件产品不支持此产品。 在这些情况下，你必须将Microsoft Defender 防病毒设置为禁用模式。 请参阅[卸载或禁用Microsoft Defender 防病毒上Windows Server 2016](#uninstalling-or-disabling-microsoft-defender-antivirus-on-windows-server-2016)

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>使用Microsoft Defender 防病毒将用户设置为被动模式

如果使用的是 Windows Server 版本 1803 或 Windows Server 2019 或 Windows Server 2022，则可以通过设置以下注册表项将 Microsoft Defender 防病毒 设置为被动模式：

- 路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名称：`ForceDefenderPassiveMode`
- 类型： `REG_DWORD`
- 值：`1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>使用Microsoft Defender 防病毒角色和功能"向导禁用角色设置

1. 请参阅 [安装或卸载角色、角色服务或功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)，并使用 **删除角色和功能向导**。

2. 当您进入向导的 **"功能**"步骤时，请清除"Windows Defender"选项。 

    如果在 **"Windows Defender** 功能"部分下自行清除 **Windows Defender，** 系统将提示您删除"Windows Defender"**的界面选项 GUI。**

    Microsoft Defender 防病毒用户界面仍将正常运行，但如果禁用核心用户界面功能，将无法 **Windows Defender** 用户界面。

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>使用 PowerShell Microsoft Defender 防病毒用户界面

若要关闭Microsoft Defender 防病毒 GUI，请使用以下 PowerShell cmdlet：

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="uninstalling-or-disabling-microsoft-defender-antivirus-on-windows-server-2016"></a>卸载或禁用Microsoft Defender 防病毒上的Windows Server 2016

如果要将Windows Server 2016 Microsoft 反恶意软件/防病毒产品一起使用，则需要禁用或卸载Microsoft Defender 防病毒。 可以使用多种方法之一：

<br>

****

|Procedure|说明|
|---|---|
|禁用Microsoft Defender 防病毒组策略|在本地组策略编辑器中，导航到 **"Windows Defender"，** 然后选择"**关闭Windows Defender 防病毒"。**|
|禁用Microsoft Defender 防病毒注册表项的注册表项|若要使用 [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 注册表项，请导航到 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` ，并设置或创建名为 的 DWORD 项 `DisableAntiSpyware` 。 将注册表项 `1` (，这将注册表项的值设置为 *true*) 。|
|使用 PowerShell Microsoft Defender 防病毒应用程序|使用以下 PowerShell cmdlet： `Set-MpPreference -DisableRealtimeMonitoring $true`|
|使用 PowerShell Microsoft Defender 防病毒卸载应用程序|使用以下 PowerShell cmdlet： `Uninstall-WindowsFeature -Name Windows-Defender`|
|

## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md)
