---
title: McAfee 到 Microsoft Defender for Endpoint - 设置
description: 这是第 2 阶段，即安装程序，用于从 McAfee 迁移到 Microsoft Defender for Endpoint。
keywords: 迁移， windows defender 高级威胁防护， atp， edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: be39d64743979fe903193a388ce491523819f299
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185607"
---
# <a name="migrate-from-mcafee---phase-2-set-up-microsoft-defender-for-endpoint"></a>从 McAfee 迁移 - 第 2 阶段：为终结点设置 Microsoft Defender

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![阶段 1：准备](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[阶段 1：准备](mcafee-to-microsoft-defender-prepare.md) |![阶段 2：设置](images/phase-diagrams/setup.png)<br/>阶段 2：设置 |[![阶段 3：载入](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[阶段 3：载入](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
||*你在这里！* | |

**欢迎使用从 McAfee Endpoint Security ([McAfee) 迁移到 Microsoft Defender for Endpoint 的安装阶段](mcafee-to-microsoft-defender-migration.md#the-migration-process)**。 此阶段包括以下步骤：
1. [启用 Microsoft Defender 防病毒并确认它处于被动模式](#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)。
2. [获取 Microsoft Defender 防病毒的更新](#get-updates-for-microsoft-defender-antivirus)。
3. [将 Microsoft Defender for Endpoint 添加到 McAfee 的排除列表](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-mcafee)。
4. [将 McAfee 添加到 Microsoft Defender 防病毒的排除列表](#add-mcafee-to-the-exclusion-list-for-microsoft-defender-antivirus)。
5. [将 McAfee 添加到 Microsoft Defender for Endpoint 的排除列表](#add-mcafee-to-the-exclusion-list-for-microsoft-defender-for-endpoint)。
6. [设置设备组、设备集合和组织单位](#set-up-your-device-groups-device-collections-and-organizational-units)。
7. [配置反恶意软件策略和实时保护](#configure-antimalware-policies-and-real-time-protection)。

## <a name="enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode"></a>启用 Microsoft Defender 防病毒并确认它处于被动模式

在某些版本的 Windows（如 Windows Server）上，安装 McAfee 解决方案时，Microsoft Defender 防病毒可能已被卸载或禁用。 这是因为安装第三方防病毒产品（如 McAfee）时，Microsoft Defender 防病毒不会进入被动或禁用模式。  (若要了解有关此的详细信息，请参阅 Microsoft [Defender 防病毒兼容性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).) 

迁移过程的这一步包括以下任务：
- [在 Windows Server 上将 DisableAntiSpyware 设置为 false](#set-disableantispyware-to-false-on-windows-server)
- [在 Windows Server 上重新安装 Microsoft Defender 防病毒](#reinstall-microsoft-defender-antivirus-on-windows-server);
- [在 Windows Server 上将 Microsoft Defender 防病毒设置为被动模式](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)
- [在 Windows 客户端设备上启用 Microsoft Defender 防病毒](#enable-microsoft-defender-antivirus-on-your-windows-client-devices);和
- [确认 Microsoft Defender 防病毒已设置为被动模式](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode)。  

### <a name="set-disableantispyware-to-false-on-windows-server"></a>在 Windows Server 上将 DisableAntiSpyware 设置为 false

[过去使用 DisableAntiSpyware](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)注册表项禁用 Microsoft Defender 防病毒，并部署其他防病毒产品，如 McAfee。 通常，不应在 Windows 设备和终结点上具有此注册表项;但是，如果已 `DisableAntiSpyware` 配置，下面将说明如何将它的值设置为 false：

1. 在 Windows Server 设备上，打开注册表编辑器。

2. 导航到 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`。

3. 在文件夹中，查找名为 **DisableAntiSpyware** 的 DWORD 条目。

   - 如果看不到该条目，则已全部设置。

   - 如果看到 **DisableAntiSpyware，** 请继续执行步骤 4。

4. 右键单击 DisableAntiSpyware DWORD，然后选择"修改 **"。**

5. 将值设置为 `0` 。  (这会将注册表项的值设置为 *false*.) 

> [!TIP]
> 若要了解有关此注册表项的信息，请参阅 [DisableAntiSpyware](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)。

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>在 Windows Server 上重新安装 Microsoft Defender 防病毒

> [!NOTE]
> 以下过程仅适用于运行以下版本的 Windows 的终结点或设备：
> - Windows Server 2019
> - Windows Server 版本 1803 (仅核心模式) 
> - Windows Server 2016

1. 作为终结点或设备的本地管理员，打开Windows PowerShell。

2. 运行以下 PowerShell cmdlet： <br/>
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>

> [!NOTE]
> 在运行 PS 的任务序列内使用 DISM 命令时，需要以下cmd.exe路径。
> 示例：<br/>
> `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
> `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. 若要验证 Microsoft Defender 防病毒是否正在运行，请使用以下 PowerShell cmdlet： <br/>
   
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>是否正在使用 Windows Server 2016？

如果你使用的是 Windows Server 2016 并且无法启用 Microsoft Defender 防病毒，请使用以下 PowerShell cmdlet：

`mpcmdrun -wdenable`

> [!TIP]
> 仍然需要帮助？ 请参阅 [Windows Server 2016 和 Windows Server 2019 上的 Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016)。

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>在 Windows Server 上将 Microsoft Defender 防病毒设置为被动模式

由于你的组织仍在使用 McAfee，因此你必须将 Microsoft Defender 防病毒设置为被动模式。 这样，McAfee 和 Microsoft Defender 防病毒可以并行运行，直到你完成载入到 Microsoft Defender for Endpoint。

1. 打开注册表编辑器，然后导航到 <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. 编辑 (或) 名为 **ForceDefenderPassiveMode** 的 DWORD 条目，并指定以下设置：
   
   - 将 DWORD 的值设置为 **1。**
   
   - 在 **"基本**"下，**选择"十六进制"。**

> [!NOTE]
> 可以使用其他方法来设置注册表项，如下所示：
>- [组策略首选项](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [本地组策略对象工具](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Configuration Manager 中的程序包](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="enable-microsoft-defender-antivirus-on-your-windows-client-devices"></a>在 Windows 客户端设备上启用 Microsoft Defender 防病毒

由于贵组织一直将 McAfee 用作主要防病毒解决方案，因此 Microsoft Defender 防病毒最有可能在组织的 Windows 设备上被禁用。 迁移过程的这一步是启用 Microsoft Defender 防病毒。 

若要启用 Microsoft Defender 防病毒，建议使用 Intune。 但是，您可以采用下表中列出的任何方法：

|方法  |需执行的操作  |
|---------|---------|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/>**注意**：Intune 现在是 Microsoft Endpoint Manager。 |1. 转到 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431) 并登录。<br/><br/>2.**选择"设备**  >  **配置文件"，** 然后选择要配置的配置文件类型。 <br/>如果你尚未创建设备限制配置文件类型，或者如果你想要创建新的配置文件类型，请参阅在 Microsoft Intune 中配置设备[限制设置](https://docs.microsoft.com/intune/device-restrictions-configure)。<br/><br/>3. 选择 **"属性"，** 然后选择"**配置设置：编辑"。**<br/><br/>4. 展开 **Microsoft Defender 防病毒**。 <br/><br/>5. 启用 **云保护**。<br/><br/>6. 在"**在示例提交前提示用户"** 下拉列表中，选择"自动 **发送所有示例"。**<br/><br/>7. 在"**检测可能不需要的应用程序"** 下拉列表中，选择"**启用"** 或"审核 **"。**<br/><br/>8. 选择 **"审阅 + 保存"，** 然后选择"保存 **"。**<br/><br/>有关 Intune 设备配置文件（包括如何创建和配置其设置）的信息，请参阅[什么是 Microsoft Intune 设备配置文件？。](https://docs.microsoft.com/intune/device-profiles)|
|Windows 中的控制面板     |请按照以下指南： [打开 Microsoft Defender 防病毒](https://docs.microsoft.com/mem/intune/user-help/turn-on-defender-windows)。 <br/><br/>**注意**：你可能会在某些 *版本的* Windows Windows Defender *看到防病毒，而不是 Microsoft Defender* 防病毒。        |
|[高级组策略管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) <br/>或者<br/>[组策略管理控制台](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. 转到 `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` 。 <br/><br/>2. 查找名为"关闭 Microsoft Defender 防病毒 **"的策略**。<br/> <br/>3. 选择 **"编辑策略设置**"，并确保策略已禁用。 这将启用 Microsoft Defender 防病毒。 <br/><br/>**注意**：你可能会在某些 *版本的* Windows Windows Defender *看到防病毒，而不是 Microsoft Defender* 防病毒。 |

### <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>确认 Microsoft Defender 防病毒处于被动模式

如果将 Microsoft Defender 防病毒设置为被动模式，Microsoft Defender 防病毒可以与 McAfee 一起运行。 可以使用命令提示符或 PowerShell 执行此任务，如下表所述：

|方法  |需执行的操作  |
|---------|---------|
|命令提示符     |1. 在 Windows 设备上，以管理员角色打开命令提示符。 <br/><br/>2. 键入 `sc query windefend` ，然后按 Enter。<br/><br/>3. 查看结果以确认 Microsoft Defender 防病毒正在被动模式下运行。         |
|PowerShell     |1.在 Windows 设备上，以Windows PowerShell打开"登录"。<br/><br/>2. 运行 [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/Get-MpComputerStatus) cmdlet。 <br/><br/>3. 在结果列表中，查找 **AMRunningMode：被动模式** 或 **AMRunningMode：SxS 被动模式**。|

> [!NOTE]
> 你可能会在某些版本的 Windows *Windows Defender* 防病毒而不是 *Microsoft Defender* 防病毒。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>获取 Microsoft Defender 防病毒的更新

使 Microsoft Defender 防病毒保持最新至关重要，可确保你的设备具有防止新的恶意软件和攻击技术所需的最新技术和功能，即使 Microsoft Defender 防病毒在被动模式下 [运行](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。

有两种类型的更新与使 Microsoft Defender 防病毒保持最新有关：
- 安全智能更新
- 产品更新

若要获取更新，请按照管理 Microsoft [Defender 防病毒更新和应用基线中的指南。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-mcafee"></a>将 Microsoft Defender for Endpoint 添加到 McAfee 排除列表

设置过程的这一步是将 Microsoft Defender for Endpoint 添加到 McAfee 的排除列表和组织使用的其他任何安全产品。 

> [!TIP]
> 若要获取有关配置排除项的帮助，请参阅 McAfee 文档，如以下文章 [：McAfee Endpoint Security 10.5.0 - 威胁防护模块产品指南 (McAfee ePolicy Orchestrator) - Windows：配置](https://docs.mcafee.com/bundle/endpoint-security-10.5.0-threat-prevention-product-guide-epolicy-orchestrator-windows/page/GUID-71C5FB4B-A143-43E6-8BF0-8B2C16ABE6DA.html)排除项。

要配置的特定排除项取决于终结点或设备运行的 Windows 版本，下表中列出了这些排除项：

|操作系统 |排除项 |
|--|--|
|- Windows 10[版本 1803](https://docs.microsoft.com/windows/release-health/status-windows-10-1803)或 (请参阅[Windows 10 版本) ](https://docs.microsoft.com/windows/release-health/release-information)<br/>- Windows 10 版本 1703 或[1709（](https://docs.microsoft.com/windows/release-health/status-windows-10-1709)已安装[KB4493441）](https://support.microsoft.com/help/4493441) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 版本 1803](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>  |
|- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/><br/>**注意**：监视主机临时文件 6\45 可以是不同的编号子文件夹。<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-mcafee-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>将 McAfee 添加到 Microsoft Defender 防病毒的排除列表

在设置过程的这一步中，将 McAfee 和其他安全解决方案添加到 Microsoft Defender 防病毒排除列表。 

将排除 [项添加到 Microsoft Defender 防病毒扫描时](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)，应添加路径和进程排除项。 请记住以下几点：
- 路径排除项排除特定文件以及这些文件访问的任何内容。
- 进程排除排除排除进程涉及的任何内容，但不排除进程本身。
- 如果将每个可执行 (.exe) 作为路径排除和进程排除，则进程及其涉及的任何内容都将被排除。
- 使用进程排除项的完整路径而不是仅按名称列出进程排除项。  (仅名称方法安全性较低。) 

你可以选择多种方法将排除项添加到 Microsoft Defender 防病毒，如下表所列：

|方法 | 需执行的操作|
|--|--|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/>**注意**：Intune 现在是 Microsoft Endpoint Manager。 |1. 转到 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431) 并登录。<br/><br/>2.**选择"设备**  >  **配置文件"，** 然后选择要配置的配置文件。<br/><br/>3. 在"**管理"下**，选择"**属性"。** <br/><br/>4. 选择 **配置设置：编辑**。<br/><br/>5. 展开 **"Microsoft Defender 防病毒**"，然后展开 **"Microsoft Defender 防病毒排除项"。**<br/><br/>6. 指定要从 Microsoft Defender 防病毒扫描中排除的文件和文件夹、扩展名和进程。 有关参考，请参阅 [Microsoft Defender 防病毒排除项](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)。<br/><br/>7. 选择 **"审阅 + 保存"，** 然后选择"保存 **"。**  |
|[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/) |1. 使用 [Configuration Manager 控制台](https://docs.microsoft.com/mem/configmgr/core/servers/manage/admin-console)，转到"资产和 **合规性**  >  **终结点** 保护反恶意软件策略"，然后选择要  >  修改的策略。 <br/><br/>2. 为要从 Microsoft Defender 防病毒扫描中排除的文件和文件夹、扩展和进程指定排除设置。 |
|[组策略对象](https://docs.microsoft.com/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. 在组策略管理计算机上，打开组策略管理 [控制台](https://technet.microsoft.com/library/cc731212.aspx)，右键单击要配置的组策略对象， **然后单击编辑**。<br/><br/>2. 在组 **策略管理编辑器** 中，转到"**计算机配置"，** 然后单击"**管理模板"。**<br/><br/>3. 将树展开到 Microsoft Defender 防病毒 **>排除**> Windows 组件。<br/>**注意**：你可能会在某些 *版本的* Windows Windows Defender *看到防病毒，而不是 Microsoft Defender* 防病毒。<br/><br/>4. 双击" **路径排除项"** 设置并添加排除项。<br/>- 将选项设置为 **已启用**。<br/>- 在"选项 **"部分** 下，单击"**显示..."。**<br/>- 在"值名称"列下的其自己的 **行中指定每个** 文件夹。<br/>- 如果指定文件，请确保输入该文件的完全限定路径，包括驱动器号、文件夹路径、文件名和扩展名。 在 **"值"****列中输入** 0。<br/><br/>5. 单击"**确定"。**<br/><br/>6. 双击扩展 **排除** 项设置并添加排除项。<br/>- 将选项设置为 **已启用**。<br/>- 在"选项 **"部分** 下，单击"**显示..."。**<br/>- 在"值名称"列下，在其自己的 **行中输入每个文件** 扩展名。  在 **"值"****列中输入** 0。<br/><br/>7. 单击"**确定"。** |
|本地组策略对象 |1. 在终结点或设备上，打开"本地组策略编辑器"。 <br/><br/>2. 转到计算机 **配置**  >  **管理模板**  >  **Windows 组件** Microsoft Defender  >  **防病毒**  >  **排除项**。 <br/>**注意**：你可能会在某些 *版本的* Windows Windows Defender *看到防病毒，而不是 Microsoft Defender* 防病毒。<br/><br/>3. 指定路径和进程排除项。 |
|注册表项 |1. 导出以下注册表项 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` ：。<br/><br/>2. 导入注册表项。 下面是两个示例：<br/>- 本地路径： `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- 网络共享： `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-mcafee-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>将 McAfee 添加到 Microsoft Defender for Endpoint 的排除列表

若要将排除项添加到 Microsoft Defender for Endpoint，请创建 [指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files)。

1. 转到 Microsoft Defender 安全中心 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () 并登录。

2. 在导航窗格中，选择"**设置**  >  **""规则**  >  **指示器"。**

3.  在"**文件哈希"选项卡上**，选择"**添加指示器"。**

3. 在" **指示器"** 选项卡上，指定以下设置：
   - 文件哈希 (需要帮助？ 请参阅 [本文中的使用 CMPivot](#find-a-file-hash-using-cmpivot) 查找文件哈希。) 
   - Under **Expires on (UTC) ，** choose **Never**.

4. 在" **操作"** 选项卡上，指定以下设置：
   - **响应操作**： **允许**
   - 标题和说明

5. 在"**范围"** 选项卡上的"**设备组"下**，选择"我的作用域内的所有 **设备**"或"**从列表中选择"。**

6. 在"**摘要"选项卡** 上，查看设置，然后单击"保存 **"。**

### <a name="find-a-file-hash-using-cmpivot"></a>使用 CMPivot 查找文件哈希

CMPivot 是 Configuration Manager 的控制台内实用工具。 CMPivot 提供对环境中设备实时状态的访问权限。 它立即在目标集合中所有当前连接的设备上运行查询并返回结果。 若要了解更多信息，请参阅 [CMPivot overview](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot-overview)。

若要使用 CMPivot 获取文件哈希，请按照以下步骤操作：

1. 查看 [先决条件](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#prerequisites)。

2. [启动 CMPivot](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot)。 

3. 连接到 Configuration Manager (`SCCM_ServerName.DomainName.com`) 。

4. 选择" **查询"** 选项卡。
 
5. 在"**设备集合"** 列表中，选择"所有系统 **" ("默认) "。**

6. 在查询框中，键入以下查询：<br/>

```kusto
File(c:\\windows\\notepad.exe)
| project Hash
```
> [!NOTE]
> 在以上查询中 *，notepad.exe第* 三方安全产品进程名称。 

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>设置设备组、设备集合和组织单位

| 集合类型 | 需执行的操作 |
|--|--|
|[设备组](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) (以前称为计算机) 组，使安全运营团队可以配置安全性功能，例如自动调查和修正。<br/><br/> 设备组还可用于分配对这些设备的访问权限，以便安全运营团队可根据需要采取修正操作。 <br/><br/>设备组是在 Microsoft Defender 安全中心中创建的。 |1. 转到 Microsoft Defender 安全中心 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () 。<br/><br/>2. 在左侧导航窗格中，**选择"设置**  >  **""权限""**  >  **设备组"。**  <br/><br/>3. 选择 **" + 添加设备组"。**<br/><br/>4. 指定设备组的名称和说明。<br/><br/>5. 在 **"自动化级别"** 列表中，选择一个选项。  (建议完全 **- 自动** 修正威胁 。) 若要了解有关各种自动化级别的完整信息，请参阅如何 [修正威胁](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)。<br/><br/>6. 指定匹配规则的条件以确定属于设备组的设备。 例如，可以选择域、操作系统版本，甚至可以使用 [设备标记](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags)。 <br/><br/>7. 在" **用户访问** "选项卡上，指定应有权访问设备组中包含的设备的角色。 <br/><br/>8. 选择"完成 **"。** |
|[设备集合](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/introduction-to-collections) 使安全运营团队能够管理应用程序、部署合规性设置或在组织的设备上安装软件更新。 <br/><br/>设备集合是使用 [Configuration Manager 创建的](https://docs.microsoft.com/mem/configmgr/)。 |按照创建集合 [中的步骤操作](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create)。 |
|[组织](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) 单位使您能够对用户帐户、服务帐户或计算机帐户等对象进行逻辑分组。 然后，可以将管理员分配给特定的组织单位，并应用组策略以强制执行目标配置设置。<br/><br/> 组织单位在 [Azure Active Directory 域服务 中定义](https://docs.microsoft.com/azure/active-directory-domain-services)。 | 按照在 Azure Active Directory 域服务托管域中创建组织 [单位中的步骤操作](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou)。 |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>配置反恶意软件策略和实时保护

使用 Configuration Manager 和设备集合 (，) 反恶意软件策略。

- 请参阅 [在 Configuration Manager 中为 Endpoint Protection 创建和部署反恶意软件策略](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)。

- 创建和配置反恶意软件策略时，请确保查看实时保护设置并启用"[](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)[首次看到时阻止"。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> 你可以先部署策略，然后再载入组织的设备。

## <a name="next-step"></a>后续步骤

**恭喜！** 你已完成从 McAfee 迁移到 [Microsoft Defender for Endpoint 的安装阶段](mcafee-to-microsoft-defender-migration.md#the-migration-process)！

- [继续执行阶段 3：载入 Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-onboard.md)
