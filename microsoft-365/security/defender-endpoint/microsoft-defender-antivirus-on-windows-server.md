---
title: Windows Server 上的 Microsoft Defender 防病毒软件
description: 了解如何在 Microsoft Defender 防病毒 Server 2019 Windows Server 2016 Windows Server 2022 上启用和配置Windows配置。
keywords: windows defender， 服务器， scep， system center endpoint protection， server 2016， current branch， server 2012
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
ms.date: 10/18/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: d06793cbc0742e3f24ac09d1f9dd64680013eecd
ms.sourcegitcommit: 2e05865beeb2051fd9ece212a46179310b946a46
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2021
ms.locfileid: "61148912"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Windows Server 上的 Microsoft Defender 防病毒软件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防病毒 Server 的以下版本/版本中提供Windows版本：

- Windows Server 2022
- Windows Server 2019
- Windows Server 版本 1803 或更高版本
- Windows Server 2016
- Windows Server 2012 R2 (需要 Microsoft Defender for Endpoint) 

在某些情况下，Microsoft Defender 防病毒称为Endpoint Protection;*但是*，保护引擎是相同的。 尽管 Microsoft Defender 防病毒 和[Windows 11](microsoft-defender-antivirus-windows.md)上的 Microsoft Defender 防病毒 功能、配置和管理基本相同Windows 10 Windows 11但 Windows Server 上存在一些关键差异：

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

默认情况下，Microsoft Defender 防病毒服务器上安装并Windows功能。 有时，用户界面会 (GUI) 安装，但不需要 GUI。 可以使用 PowerShell、组策略或其他方法来管理Microsoft Defender 防病毒。

如果服务器上未安装 GUI，并且要安装 GUI，则使用"添加角色 **和功能** "向导或 PowerShell cmdlet。

> [!NOTE]
> 此选项不适用于 Windows Server 2012 R2。 有关详细信息，请参阅安装 [Microsoft Defender for Endpoint 的选项](configure-server-endpoints.md#options-to-install-microsoft-defender-for-endpoint)。

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>使用添加角色和功能向导打开 GUI

1. 请参阅 [使用添加角色和功能向导](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)安装角色、角色服务和功能，并使用 **添加角色和功能向导**。

2. 当您进入向导的"**功能**"步骤时，在"Windows Defender **功能"** 下，选择 **"Windows Defender** GUI"选项。

   在Windows Server 2016中，添加 **角色和功能向导** 如下所示：

   ![添加显示自定义选项的 GUI 的角色Windows Defender向导。](images/server-add-gui.png)

   在 Windows Server 2019 和 Windows Server 2022 中，添加 **角色和功能向导** 类似。

### <a name="turn-on-the-gui-using-powershell"></a>使用 PowerShell 打开 GUI

以下 PowerShell cmdlet 将启用该接口：

```powershell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>在 Microsoft Defender 防病毒 服务器上Windows服务器

如果需要在 Microsoft Defender 防病毒 服务器上安装或重新安装Windows，可以使用"添加角色 **和功能** 向导"或 PowerShell 完成这一操作。

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>使用添加角色和功能向导安装Microsoft Defender 防病毒

1. 请参阅 [本文 ，并使用](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)添加 **角色和功能向导**。

2. When you get to the **Features** step of the wizard， select the Microsoft Defender 防病毒 option. 另外，选择 **"管理Windows Defender** GUI。

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>使用 PowerShell 安装Microsoft Defender 防病毒

若要使用 PowerShell 安装Microsoft Defender 防病毒，请运行以下 cmdlet：

```powershell
Install-WindowsFeature -Name Windows-Defender
```

Microsoft Defender AV 事件 中Microsoft Defender 防病毒[包含的反恶意软件引擎的事件消息](troubleshoot-microsoft-defender-antivirus.md)。

## <a name="verify-microsoft-defender-antivirus-is-running"></a>验证Microsoft Defender 防病毒是否正在运行

安装Microsoft Defender 防病毒后，下一步是验证它是否正在运行。 在 Windows Server 终结点上，运行以下 PowerShell cmdlet：

```powershell
Get-Service -Name windefend
```

若要验证防火墙保护是否打开，请运行以下 PowerShell cmdlet：

```powershell
Get-Service -Name mpssvc
```

作为 PowerShell 的替代方法，可以使用命令提示符验证Microsoft Defender 防病毒运行。 为此，请从命令提示符运行以下命令：

```console
sc query Windefend
```

该命令 `sc query` 返回有关 Microsoft Defender 防病毒 的信息。 当Microsoft Defender 防病毒运行时， `STATE` 值将显示 `RUNNING` 。

## <a name="update-antimalware-security-intelligence"></a>更新反恶意软件安全智能

若要获取更新的反恶意软件安全智能，必须运行 Windows Update 服务。 如果使用更新管理服务（如 Windows Server Update Services (WSUS) ，请确保已针对你管理的计算机Microsoft Defender 防病毒安全智能的更新。

默认情况下，Windows Update 不会在 Windows Server 2019、Windows Server 2022 或 Windows Server 2016 上自动下载和安装Windows Server 2016。 可以使用以下方法之一更改此配置：

<br/><br/>

| 方法 | 说明 |
|---|---|
| **Windows控制面板** 中的更新 | **自动安装更新** 会导致自动安装所有更新，Windows Defender安全智能更新。 <br/><br/> **下载更新，但允许我** 选择是否安装它们Windows Defender自动下载和安装安全智能更新，但不会自动安装其他更新。 |
| **组策略** | 可以使用组策略中提供的设置设置和管理 Windows 更新，路径如下：**管理模板\Windows 组件\Windows 更新\配置自动更新** |
| **AUOptions** 注册表项 | 以下两个值允许Windows更新自动下载和安装安全智能更新： <br/><br/> **4**  - **自动安装更新**。 此值会导致自动安装所有更新，包括Windows Defender更新。 <br/><br/> **3**  - **下载更新，但允许我选择是否安装它们**。 此值允许Windows Defender下载和安装安全智能更新，但不会自动安装其他更新。 |

为了确保对恶意软件的保护得到维护，我们建议您启用以下服务：

- Windows 错误报告服务
- Windows Update Service

下表列出了服务相关的Microsoft Defender 防病毒服务。

<br/><br/>


| 服务名称 | 文件位置 | 说明 |
|---|---|---|
| Windows Defender Service (WinDefend)  | `C:\Program Files\Windows Defender\MsMpEng.exe` | 这是需要Microsoft Defender 防病毒运行的主要服务。|
| Windows 错误报告 Service (Wersvc)  | `C:\WINDOWS\System32\svchost.exe -k WerSvcGroup` | 此服务将错误报告发送回 Microsoft。 |
| Windows Defender MpsSvc (防火墙)  | `C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork` | 我们建议使防火墙Windows Defender启用。 |
| Windows Wuauserv (更新)  | `C:\WINDOWS\system32\svchost.exe -k netsvcs`| Windows更新才能获取安全智能更新和反恶意软件引擎更新 |

## <a name="submit-samples"></a>提交示例

示例提交允许 Microsoft 收集潜在恶意软件的示例。 为了帮助提供持续且最新的保护，Microsoft 研究人员使用这些示例来分析可疑活动并生成更新的反恶意软件安全智能。 我们收集程序可执行文件，例如.exe文件.dll文件。 我们不会收集包含个人数据的文件，如Microsoft Word和 PDF 文件。

### <a name="submit-a-file"></a>提交文件

1. 查看 [提交指南](/windows/security/threat-protection/intelligence/submission-guide)。
2. 访问 [示例提交门户 ，](https://www.microsoft.com/wdsi/filesubmission)并提交文件。

### <a name="enable-automatic-sample-submission"></a>启用自动提交示例

若要启用自动示例提交，请以管理员Windows PowerShell启动示例提交控制台，然后根据以下设置之一设置 **SubmitSamplesConsent** 值数据：

<br/><br/>

|设置|说明|
|---|---|
| **0**  - **始终提示** | the Microsoft Defender 防病毒 service prompts you to confirm submission of all required files. 这是 Microsoft Defender 防病毒 的默认设置，但不建议在 Windows Server 2016 或 2019 或 Windows Server 2022 上安装不带 GUI。 |
| **1**   - **自动发送安全示例** | 该服务Microsoft Defender 防病毒发送标记为"安全"的所有文件，并提示您输入其余文件。 |
| **2**  - **从不发送** | the Microsoft Defender 防病毒 service does not prompt and does not send any files. |
| **3**  - **自动发送所有示例** | 该服务Microsoft Defender 防病毒发送所有文件，而不提示确认。 |

> [!NOTE]
> 此选项不适用于 Windows Server 2012 R2。 


## <a name="configure-automatic-exclusions"></a>配置自动排除项

为了帮助确保安全性和性能，根据在 Windows Server 2016 或 Windows Server 2016 Server 2022 或 Windows Server 2022 上使用 Microsoft Defender 防病毒 时安装的角色和功能，会自动添加某些排除项。

请参阅[Configure exclusions in Microsoft Defender 防病毒 on Windows Server。](configure-server-exclusions-microsoft-defender-antivirus.md)

## <a name="passive-mode-and-windows-server"></a>被动模式和Windows服务器

如果要将非 Microsoft 防病毒产品用作 Windows Server 上的主要防病毒解决方案，则必须Microsoft Defender 防病毒被动模式或禁用模式。

有关详细信息，请参阅 Install [Microsoft Defender 防病毒 on Windows Server。](microsoft-defender-antivirus-on-windows-server.md#install-microsoft-defender-antivirus-on-windows-server)


### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>使用Microsoft Defender 防病毒将用户设置为被动模式

可以通过设置Microsoft Defender 防病毒注册表项来将用户设置为被动模式：
- 路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名称：`ForceDefenderPassiveMode`
- 类型： `REG_DWORD`
- 值：`1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>使用Microsoft Defender 防病毒角色和功能向导禁用配置

1. 请参阅 [安装或卸载角色、角色服务或功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)，并使用 **删除角色和功能向导**。

2. 当您进入向导的 **"功能**"步骤时，请清除"Windows Defender"选项。 

    如果在 **"Windows Defender** 功能"部分下自行清除 **Windows Defender，** 系统将提示您删除"功能"的界面 **选项 GUI Windows Defender。**

    Microsoft Defender 防病毒用户界面，用户界面仍将正常运行，但如果您禁用核心用户界面功能，Windows Defender **启用。**

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>使用 PowerShell Microsoft Defender 防病毒用户界面

若要关闭此Microsoft Defender 防病毒 GUI，请使用以下 PowerShell cmdlet：

```powershell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>是使用 Windows Server 2012 R2 还是 Windows Server 2016？

现在，可以在 Microsoft Defender 防病毒 R2 Windows Server 2012被动模式下运行Windows Server 2016。 有关详细信息，请参阅安装 [Microsoft Defender for Endpoint 的选项](configure-server-endpoints.md#options-to-install-microsoft-defender-for-endpoint)。

<br/><br/>

| Procedure | 说明 |
|---|---|
| 禁用Microsoft Defender 防病毒组策略 | 在本地组策略编辑器中，导航到"管理模板Windows  >  **组件** Endpoint Protection  >    >  **禁用Endpoint Protection"，** 然后选择"启用确定  >  **"。** |
| 禁用Microsoft Defender 防病毒注册表项的注册表项 | 若要使用 [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 注册表项，请导航到 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` ，并设置或创建名为 的 DWORD 项 `DisableAntiSpyware` 。 将注册表项 `1` (，这将注册表项的值设置为 *true*) 。 |
| 使用 PowerShell Microsoft Defender 防病毒应用程序 | 使用以下 PowerShell cmdlet： `Set-MpPreference -DisableRealtimeMonitoring $true` |
| 使用 PowerShell Microsoft Defender 防病毒卸载应用程序 | 使用以下 PowerShell cmdlet： `Uninstall-WindowsFeature -Name Windows-Defender` |


## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-windows.md)
- [Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md)
