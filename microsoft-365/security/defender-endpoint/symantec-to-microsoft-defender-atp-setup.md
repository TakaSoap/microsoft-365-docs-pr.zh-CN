---
title: Symantec 到 Microsoft Defender for Endpoint - 第 2 阶段，设置
description: 这是从 Symantec 迁移到 Microsoft Defender for Endpoint 的第 2 阶段（安装程序）
keywords: migration， Microsoft Defender for Endpoint， edr
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 05/14/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: ee4324c77653d9d82ef613ff88d31cfb94ee3218
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539151"
---
# <a name="migrate-from-symantec---phase-2-set-up-microsoft-defender-for-endpoint"></a>从 Symantec 迁移 - 阶段 2：为终结点设置 Microsoft Defender

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![阶段 1：准备](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[阶段 1：准备](symantec-to-microsoft-defender-atp-prepare.md) |![阶段 2：设置](images/phase-diagrams/setup.png)<br/>阶段 2：设置 |[![阶段 3：开始使用](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[阶段 3：开始使用](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
||*你在这里！* | |


**欢迎使用从 [Symantec 迁移到 Defender for Endpoint 的安装阶段](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**。 此阶段包括以下步骤：

1. [在终结点上Microsoft Defender 防病毒/启用客户端。](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)

2. [为终结点配置 Defender。](#configure-defender-for-endpoint)

3. [将 Microsoft Defender for Endpoint 添加到 Symantec 的排除列表](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec)。

4. [将 Symantec 添加到列表的排除Microsoft Defender 防病毒。](#add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus)

5. [设置设备组、设备集合和组织单位](#set-up-your-device-groups-device-collections-and-organizational-units)。

6. [配置反恶意软件策略和实时保护](#configure-antimalware-policies-and-real-time-protection)。 

## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>在终结点上Microsoft Defender 防病毒/启用配置

在某些版本的 Windows，Microsoft Defender 防病毒安装非 Microsoft 防病毒/反恶意软件解决方案时，可能会卸载或禁用此软件。 有关详细信息，请参阅兼容性[Microsoft Defender 防病毒兼容性](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。 

在Windows客户端上，安装非 Microsoft 防病毒/反恶意软件解决方案时，Microsoft Defender 防病毒将自动禁用，直到这些设备载入 Defender for Endpoint。 当客户端终结点载入 Defender for Endpoint 时，Microsoft Defender 防病毒进入被动模式，直到卸载非 Microsoft 防病毒解决方案。 Microsoft Defender 防病毒仍应安装，但在迁移过程的此时可能处于禁用状态。 除非Microsoft Defender 防病毒，否则无需对客户端执行任何Windows操作。

在Windows服务器上，安装非 Microsoft 防病毒/反恶意软件时，Microsoft Defender 防病毒如果尚未卸载 (，则手动禁用) 。 以下任务有助于确保在 Microsoft Defender 防病毒 服务器上安装并设置为被动Windows模式。

- 仅在必要时，才在 Windows Server (将 DisableAntiSpyware 设置为 false) 

- 在 Microsoft Defender 防病毒 服务器上重新安装 Windows

- 将Microsoft Defender 防病毒服务器设置为被动Windows模式

### <a name="set-disableantispyware-to-false-on-windows-server"></a>在 Windows 服务器上将 DisableAntiSpyware 设置为 false

过去使用 DisableAntiSpyware 注册表项来禁用Microsoft Defender 防病毒防病毒产品 Symantec。 通常，不应在设备上和终结点上Windows注册表项;但是，如果已 `DisableAntiSpyware` 配置，下面将说明如何将它的值设置为 false：

1. 在 Windows Server 设备上，打开注册表编辑器。

2. 导航到 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`。

3. 在文件夹中，查找名为 **DisableAntiSpyware** 的 DWORD 条目。

   - 如果看不到该条目，则已全部设置。
   - 如果看到 DisableAntiSpyware，请继续执行步骤 4。

4. 右键单击 DisableAntiSpyware DWORD，然后选择"修改 **"。**

5. 将值设置为 `0` 。  (此操作将注册表项的值设置为 *false*.) 

> [!TIP]
> 若要了解有关此注册表项的信息，请参阅 **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**。

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>在 Microsoft Defender 防病毒 服务器上重新安装 Windows

> [!NOTE]
> 以下过程仅适用于运行以下版本的 Windows：
> - Windows Server 2019
> - Windows服务器版本 1803 (仅核心模式) 
> - Windows Server 2016

1. 作为终结点或设备的本地管理员，打开Windows PowerShell。

1. 运行以下 PowerShell cmdlet：

   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` 
   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`

    > [!NOTE]
    > 在运行 PS 的任务序列内使用 DISM 命令时，需要以下cmd.exe路径。
    > 示例：
    >
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
    >
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. 若要验证Microsoft Defender 防病毒运行，请使用以下 PowerShell cmdlet： <br/>
   `Get-Service -Name windefend`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>将Microsoft Defender 防病毒服务器设置为被动Windows模式

1. 打开注册表编辑器，然后导航到 <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. 编辑 (或创建) **ForcePassiveMode** 的 DWORD 条目，并指定以下设置：
   - 将 DWORD 的值设置为 **1。**
   - 在 **"基本**"下，**选择"十六进制"。**

> [!NOTE]
> 可以使用其他方法来设置注册表项，如下所示：
>- [组策略首选项](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [本地组策略对象工具](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Configuration Manager 中的程序包](/mem/configmgr/apps/deploy-use/packages-and-programs)
>
> 载入适用于终结点的 Defender 后，可能需要在 Microsoft Defender 防病毒 服务器上将 Windows 模式。

### <a name="are-you-using-windows-server-2016"></a>是否正在使用Windows Server 2016？

如果你的终结点在Windows Server 2016，则不能Microsoft Defender 防病毒 Microsoft 防病毒/反恶意软件解决方案一起运行。 Microsoft Defender 防病毒无法以被动模式在Windows Server 2016。 在这种情况下，你需要卸载非 Microsoft 防病毒/反恶意软件解决方案，并安装/启用Microsoft Defender 防病毒解决方案。 若要了解更多信息，请参阅防病毒 [解决方案与 Defender for Endpoint 的兼容性](microsoft-defender-antivirus-compatibility.md)。

如果您使用的是 Windows Server 2016且无法启用Microsoft Defender 防病毒，请使用以下 PowerShell cmdlet：

`mpcmdrun -wdenable`

有关详细信息，请参阅 Microsoft Defender 防病毒[server Windows。](microsoft-defender-antivirus-on-windows-server.md)

## <a name="configure-defender-for-endpoint"></a>为终结点配置 Defender

迁移过程的这一步涉及为Microsoft Defender 防病毒配置策略。 我们建议使用 Intune;但是，您可以采用下表中列出的任何方法：

|方法  |需执行的操作  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**注意**：Intune 现在是该Microsoft Endpoint Manager。 |1. 转到Microsoft Endpoint Manager[中心并](https://go.microsoft.com/fwlink/?linkid=2109431)登录。<p>2.**选择"设备**  >  **配置文件"，** 然后选择要配置的配置文件类型。 如果你尚未创建设备限制配置文件类型，或者如果你想要创建新的配置文件类型，请参阅配置设备限制设置[Microsoft Intune。](/intune/device-restrictions-configure)<p>3. 选择 **"属性"，** 然后选择"**配置设置：编辑"。**<p>4. 展开 **"Microsoft Defender 防病毒"。** <p>5. 启用 **云保护**。<p>6. 在"**在示例提交前提示用户"** 下拉列表中，选择"自动 **发送所有示例"。**<p>7. 在"**检测可能不需要的应用程序"** 下拉列表中，选择"**启用"** 或"审核 **"。**<p>8. 选择 **"审阅 + 保存"，** 然后选择"保存 **"。**<br/>有关 Intune 设备配置文件（包括如何创建和配置其设置）的信息，请参阅什么是Microsoft Intune[配置文件？。](/intune/device-profiles)|
|控制面板Windows     |请按照以下指南：[打开"Microsoft Defender 防病毒"。](/mem/intune/user-help/turn-on-defender-windows) <br/>**注意**：你可能会在 *Windows Defender 防病毒* 版本中看到 Microsoft Defender 防病毒 而不是Windows。        |
|[高级组策略管理](/microsoft-desktop-optimization-pack/agpm/) <br/>或<br/>[组策略管理控制台](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. 转到 `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` 。 <p>2. 查找名为"关闭策略 **Microsoft Defender 防病毒。**<p>3. 选择 **"编辑策略设置**"，并确保策略已禁用。 这将启用Microsoft Defender 防病毒。 <p>**注意**：你可能会在 *Windows Defender 防病毒* 版本中看到 Microsoft Defender 防病毒 而不是Windows。 |

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec"></a>将 Microsoft Defender for Endpoint 添加到 Symantec 排除列表

设置过程的这一步是将 Defender for Endpoint 添加到 Symantec 的排除列表和组织使用的其他任何安全产品。 要配置的特定排除项取决于您Windows或设备运行的是哪个版本，下表中列出了这些排除项：

|操作系统 |排除项 |
|--|--|
| Windows 10[版本 1803](/windows/release-health/status-windows-10-1803)或更高版本 (请参阅 Windows 10 release [information) ](/windows/release-health/release-information)<p> Windows 10，版本 1703 或 1709（已安装[KB4493441）](https://support.microsoft.com/help/4493441) <p> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p> [Windows服务器版本 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<p>  |
| [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p> [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p> [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<p> [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p> [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<p>**注意**：监视主机临时文件 6\45 可以是不同的编号子文件夹。<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>将 Symantec 添加到列表的排除Microsoft Defender 防病毒

在设置过程的这一步中，将现有解决方案添加到Microsoft Defender 防病毒列表中。 可以从多种方法中选择将排除项添加到Microsoft Defender 防病毒，如下表所列：

> [!NOTE]
> 若要了解要排除的进程和服务，请参阅 Broadcom 的 Processes [and services used by Endpoint Protection 14](https://knowledge.broadcom.com/external/article/170706/processes-and-services-used-by-endpoint.html)。

|方法 | 需执行的操作|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**注意**：Intune 现在是该Microsoft Endpoint Manager。 |1. 转到Microsoft Endpoint Manager[中心并](https://go.microsoft.com/fwlink/?linkid=2109431)登录。<p>2.**选择"设备**  >  **配置文件"，** 然后选择要配置的配置文件。<p>3. 在"**管理"下**，选择"**属性"。** <p>4. 选择 **配置设置：编辑**。<p>5. 展开 **Microsoft Defender 防病毒，** 然后展开 **"Microsoft Defender 防病毒排除"。**<p>6. 指定要从扫描中排除的文件和文件夹、扩展Microsoft Defender 防病毒进程。 有关参考，请参阅[Microsoft Defender 防病毒排除项](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)。<p>7. 选择 **"审阅 + 保存"，** 然后选择"保存 **"。**  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) |1. 使用[Configuration Manager](/mem/configmgr/core/servers/manage/admin-console)控制台，转到"资产和Endpoint Protection反恶意软件策略"，然后选择  >    >  要修改的策略。 <p>2. 为要从扫描中排除的文件和文件夹、扩展和进程指定排除Microsoft Defender 防病毒设置。 |
|[组策略对象](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. 在组策略管理计算机上，打开组 [](https://technet.microsoft.com/library/cc731212.aspx)策略管理控制台，右键单击要配置的组策略对象，**然后选择编辑**。<p>2. 在组 **策略管理编辑器** 中，转到"**计算机配置"，** 然后选择"**管理模板"。**<p>3. 展开树以Windows **排除> Microsoft Defender 防病毒 >组件**。<br/>**注意**：你可能会在 *Windows Defender 防病毒* 版本中看到 Microsoft Defender 防病毒 而不是Windows。<p>4. 双击" **路径排除项"** 设置并添加排除项。<br/>- 将选项设置为 **已启用**。<br/>- 在"选项 **"部分** 下，选择"**显示..."。**<br/>- 在"值名称"列下的其自己的 **行中指定每个** 文件夹。<br/>- 如果指定文件，请确保输入该文件的完全限定路径，包括驱动器号、文件夹路径、文件名和扩展名。 在 **"值"****列中输入** 0。<p>5. 选择"**确定"。**<p>6. 双击扩展 **排除** 项设置并添加排除项。<br/>- 将选项设置为 **已启用**。<br/>- 在"选项 **"部分** 下，选择"**显示..."。**<br/>- 在"值名称"列下，在其自己的 **行中输入每个文件** 扩展名。<br/>- 在"值"列中 **输入** **0。**<p>7. 选择"**确定"。** |
|本地组策略对象 |1. 在终结点或设备上，打开"本地组策略编辑器"。 <p>2. 转到计算机 **配置** 管理模板  >    >  **Windows组件**  >  **Microsoft Defender 防病毒**  >  **排除项**。 <br/>**注意**：你可能会在 *Windows Defender 防病毒* 版本中看到 Microsoft Defender 防病毒 而不是Windows。<p>3. 指定路径和进程排除项。 |
|注册表项 |1. 导出以下注册表项 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` ：。<p>2. 导入注册表项。 下面是两个示例：<br/>- 本地路径： `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- 网络共享： `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

向扫描[中添加排除项Microsoft Defender 防病毒，](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)应添加路径和进程排除项。 请记住以下几点：
- 路径排除项排除特定文件以及这些文件访问的任何内容。
- 进程排除排除排除进程涉及的任何内容，但不排除进程本身。
- 如果将每个可执行文件 (.exe) 路径排除和进程排除，将排除进程及其涉及的任何内容。
- 使用进程排除项的完整路径而不是仅按名称列出进程排除项。  (仅名称方法安全性较低。) 

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>设置设备组、设备集合和组织单位

设备组、设备集合和组织单位使安全团队能够高效地管理和分配安全策略。 下表介绍了其中每个组以及如何配置它们。 您的组织可能不会使用所有这三种集合类型。

| 集合类型 | 需执行的操作 |
|--|--|
|[设备组](/microsoft-365/security/defender-endpoint/machine-groups) (以前称为计算机) 组，使安全运营团队可以配置安全性功能，例如自动调查和修正。<br/> 设备组还可用于分配对这些设备的访问权限，以便安全运营团队可根据需要采取修正操作。 <br/>设备组在设备Microsoft Defender 安全中心。 |1. 转到 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender 安全中心 () 。<p>2. 在左侧导航窗格中，选择"设置  >  **权限设备**  >  **组"。**  <p>3. 选择 **" + 添加设备组"。**<p>4. 指定设备组的名称和说明。<p>5. 在 **"自动化级别"** 列表中，选择一个选项。  (建议完全 **- 自动** 修正威胁 。) 若要了解有关各种自动化级别的完整信息，请参阅如何 [修正威胁](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)。<p>6. 指定匹配规则的条件以确定属于设备组的设备。 例如，可以选择域、操作系统版本，甚至可以使用 [设备标记](/microsoft-365/security/defender-endpoint/machine-tags)。<p>7. 在" **用户访问** "选项卡上，指定应有权访问设备组中包含的设备的角色。 <p>8. 选择"完成 **"。** |
|[设备集合](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) 使安全运营团队能够管理应用程序、部署合规性设置或在组织的设备上安装软件更新。 <br/>设备集合是使用 [Configuration Manager 创建的](/mem/configmgr/)。 |按照创建集合 [中的步骤操作](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create)。 |
|[组织](/azure/active-directory-domain-services/create-ou) 单位使您能够对用户帐户、服务帐户或计算机帐户等对象进行逻辑分组。 然后，可以将管理员分配给特定的组织单位，并应用组策略以强制执行目标配置设置。<br/> 组织单位在域服务[中Azure Active Directory定义](/azure/active-directory-domain-services)。 | 按照在域服务托管域中创建组织Azure Active Directory[中的步骤操作](/azure/active-directory-domain-services/create-ou)。 |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>配置反恶意软件策略和实时保护

使用 Configuration Manager 和设备集合 (，) 反恶意软件策略。

- 请参阅[在 Configuration Manager 中为Endpoint Protection和部署反恶意软件策略](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)。

- 创建和配置反恶意软件策略时，请确保查看实时保护设置并启用"[](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)[首次看到时阻止"。](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> 你可以先部署策略，然后再载入组织的设备。

## <a name="next-step"></a>后续步骤

**恭喜！** 你已完成从 [Symantec 迁移到 Defender for Endpoint 的安装阶段](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)！
- [继续执行阶段 3：载入到适用于终结点的 Defender](symantec-to-microsoft-defender-atp-onboard.md)
