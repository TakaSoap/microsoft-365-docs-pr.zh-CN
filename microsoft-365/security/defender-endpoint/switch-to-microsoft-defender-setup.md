---
title: 切换到 Microsoft Defender for Endpoint - 安装程序
description: 转换到 Defender for Endpoint。 查看安装过程，其中包括安装Microsoft Defender 防病毒。
keywords: 迁移， Microsoft Defender for Endpoint， 防病毒， 被动模式， 设置过程
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
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: article
ms.custom: migrationguides
ms.date: 11/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 8ff011277df4e4bfba16eef169f5f64ba5751b32
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60786706"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>切换到 Microsoft Defender for Endpoint - 阶段 2：设置

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![阶段 1：准备。](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[阶段 1：准备](switch-to-microsoft-defender-prepare.md)|![阶段 2：设置。](images/phase-diagrams/setup.png)<br/>阶段 2：设置|[![阶段 3：Onboard3。](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[阶段 3：开始使用](switch-to-microsoft-defender-onboard.md)|
|---|---|---|
||*你在这里！*||

**欢迎使用切换到 Defender [for Endpoint 的安装阶段](switch-to-microsoft-defender-migration.md#the-migration-process)**。 此阶段包括以下步骤：

1. [在终结点上Microsoft Defender 防病毒/启用安全配置](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)。
2. [为终结点配置 Defender。](#configure-defender-for-endpoint)
3. [将 Defender for Endpoint 添加到现有解决方案的排除列表](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution)。
4. [将现有解决方案添加到列表的排除Microsoft Defender 防病毒。](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus)
5. [设置设备组、设备集合和组织单位](#set-up-your-device-groups-device-collections-and-organizational-units)。

## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>在终结点Microsoft Defender 防病毒/启用配置

在某些版本的 Windows，Microsoft Defender 防病毒安装非 Microsoft 防病毒/反恶意软件解决方案时，可能会卸载或禁用这些应用程序。 当运行 Windows终结点载入 Defender for Endpoint 时，Microsoft Defender 防病毒非 Microsoft 防病毒解决方案一起在被动模式下运行。 若要了解更多信息，请参阅使用 [Defender for Endpoint 进行防病毒保护](microsoft-defender-antivirus-compatibility.md#antivirus-protection-without-defender-for-endpoint)。

在切换到 Defender for Endpoint 时，可能需要采取某些步骤来重新安装或启用Microsoft Defender 防病毒。 下表介绍了在客户端和服务器上Windows操作。
<br/> <br/>

|终结点类型|需执行的操作|
|---|---|
|Windows客户端 (，例如运行 Windows 10 和 Windows 11) |一般情况下，无需对客户端Windows执行任何 (，Microsoft Defender 防病毒客户端) 。 以下是原因： <br/><br/> Microsoft Defender 防病毒仍应安装，但在迁移过程的此时很可能已禁用。 <br/><br/> 安装非 Microsoft 防病毒/反恶意软件解决方案，并且客户端尚未载入 Defender for Endpoint 时，Microsoft Defender 防病毒自动禁用。 <br/><br/> 稍后，当客户端终结点载入 Defender for Endpoint 时，如果这些终结点运行的是非 Microsoft 防病毒解决方案，Microsoft Defender 防病毒进入被动模式。 <br/><br/> 如果卸载非 Microsoft 防病毒解决方案，Microsoft Defender 防病毒自动进入活动模式。|
|Windows服务器|在 Windows 服务器上，你需要重新安装Microsoft Defender 防病毒，并手动设置为被动模式。 在Windows服务器上，安装非 Microsoft 防病毒/反恶意软件Microsoft Defender 防病毒无法与非 Microsoft 防病毒解决方案一起运行。 在这种情况下，Microsoft Defender 防病毒禁用或卸载。 <br/><br/> 若要在 Microsoft Defender 防病毒 服务器上重新安装或Windows，请执行以下任务： <br/>- 仅在必要时，才将 Windows Server ([DisableAntiSpyware](#set-disableantispyware-to-false-on-windows-server)设置为 false) <br/>- [在 Microsoft Defender 防病毒 服务器上重新安装Windows](#reinstall-microsoft-defender-antivirus-on-windows-server)<br/>- [将Microsoft Defender 防病毒服务器设置为被动Windows模式](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)|

> [!TIP]
> 若要了解有关使用Microsoft Defender 防病毒 Microsoft 防病毒保护状态的详细信息，请参阅Microsoft Defender 防病毒[兼容性。](microsoft-defender-antivirus-compatibility.md)

### <a name="set-disableantispyware-to-false-on-windows-server"></a>在 Windows Server 上将 DisableAntiSpyware 设置为 false

过去使用[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)注册表项禁用 Microsoft Defender 防病毒，并部署其他防病毒产品，如 McAfee、Symantec 或其他产品。 **通常，不应在设备上和终结点上Windows注册表项**;但是，*如果已* `DisableAntiSpyware` 配置，下面将说明如何将它的值设置为 false：

1. 在 Windows Server 设备上，打开注册表编辑器。

2. 导航到 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`。

3. 在文件夹中，查找名为 **DisableAntiSpyware** 的 DWORD 条目。
   - 如果看不到该条目，则已全部设置。
   - 如果看到 **DisableAntiSpyware，** 请继续执行步骤 4。

4. 右键单击 DisableAntiSpyware DWORD，然后选择"修改 **"。**

5. 将值设置为 `0` 。  (此操作将注册表项的值设置为 *false*.) 

> [!TIP]
> 若要了解有关此注册表项的信息，请参阅 [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)。

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>在 Microsoft Defender 防病毒 服务器上重新安装Windows

> [!IMPORTANT]
> 以下过程仅适用于运行以下版本的 Windows：
>
> - Windows Server 2019
> - Windows Server 2022
> - Windows服务器版本 1803 (仅核心模式) 
> - Windows Server 2016 (请参阅以下部分：[是否正在使用Windows Server 2016？](#are-you-using-windows-server-2012-r2-or-windows-server-2016)

1. 作为终结点或设备的本地管理员，打开Windows PowerShell。

2. 运行以下 PowerShell cmdlet：

   ```powershell
   # For Windows Server 2016
   Dism /online /Enable-Feature /FeatureName:Windows-Defender-Features
   Dism /online /Enable-Feature /FeatureName:Windows-Defender
   Dism /online /Enable-Feature /FeatureName:Windows-Defender-Gui
   # For Windows Server 2019 and Windows Server 2022
   Dism /online /Enable-Feature /FeatureName:Windows-Defender
   ```

   然后重新启动设备。

   在运行 PowerShell 的任务序列内使用 DISM 命令时，必须cmd.exe路径。
   示例：

   ```powershell
   c:\windows\sysnative\cmd.exe /c Dism /online /Enable-Feature /FeatureName:Windows-Defender-Features
   c:\windows\sysnative\cmd.exe /c Dism /online /Enable-Feature /FeatureName:Windows-Defender
   ```

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>将Microsoft Defender 防病毒服务器设置为被动Windows模式

1. 打开注册表编辑器，然后导航到

   ```text
   Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
   ```

2. 编辑 (或) 名为 **ForceDefenderPassiveMode** 的 DWORD 条目，并指定以下设置：

   - 将 DWORD 的值设置为 **1。**
   - 在 **"基本**"下，**选择"十六进制"。**

> [!NOTE]
> 载入 Defender for Endpoint 后，你可能必须Microsoft Defender 防病毒服务器中的被动Windows模式。 若要验证被动模式是否按预期设置，请搜索位于) 的 **Microsoft-Windows-Windows Defender** 操作日志 (中的事件 *5007，* 并确认 `C:\Windows\System32\winevt\Logs` **ForceDefenderPassiveMode** 或 **PassiveMode** 注册表项已设置为 **0x1。**

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>是使用 Windows Server 2012 R2 还是 Windows Server 2016？

现在，可以使用上述Microsoft Defender 防病毒在 Windows Server 2012 R2 和 2016 上以被动模式运行。 有关详细信息，请参阅安装 [Microsoft Defender for Endpoint 的选项](configure-server-endpoints.md#options-to-install-microsoft-defender-for-endpoint)。

## <a name="configure-defender-for-endpoint"></a>配置 Defender for Endpoint

迁移过程的这一步涉及为Microsoft Defender 防病毒配置策略。 我们建议使用 Intune;但是，您可以采用下表中列出的任何方法：
<br/><br/>

|方法|需执行的操作|
|---|---|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/> **注意**：Intune 现在是该Microsoft Endpoint Manager。|1. 转到Microsoft Endpoint Manager[中心并](https://go.microsoft.com/fwlink/?linkid=2109431)登录。<br/><br/>2. **选择"设备** \> **配置文件"，** 然后选择要配置的配置文件类型。 如果你尚未创建设备限制配置文件类型，或者如果你想要创建新的配置文件类型，请参阅配置设备限制设置[Microsoft Intune。](/intune/device-restrictions-configure)<br/><br/>3. 选择 **"属性"，** 然后选择" **配置设置：编辑"**<br/><br/>4. 展开 **Microsoft Defender 防病毒**。<br/><br/>5. 启用 **云保护**。<br/><br/>6. 在"**在示例提交前提示用户"** 下拉列表中，选择"自动 **发送所有示例"。**<br/><br/>7. 在"**检测可能不需要的应用程序"** 下拉列表中，选择"**启用"** 或"审核 **"。**<br/><br/>8. 选择 **"审阅 + 保存"，** 然后选择"保存 **"。** <br/><br/> **提示**：有关 Intune 设备配置文件（包括如何创建和配置其设置）的信息，请参阅什么是Microsoft Intune [配置文件？。](/intune/device-profiles)|
|Microsoft Endpoint Configuration Manager|请参阅[在 Configuration Manager 中为Endpoint Protection和部署反恶意软件策略](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)。 <br/><br/> 创建和配置反恶意软件策略时，请确保查看实时保护设置并启用"[](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)[首次看到时阻止"。](configure-block-at-first-sight-microsoft-defender-antivirus.md)
|控制面板Windows|请按照以下指南：[打开"Microsoft Defender 防病毒"。](/mem/intune/user-help/turn-on-defender-windows)  (在 Windows Defender 防病毒.Microsoft Defender 防病毒.Windows.)  |
|[高级组策略管理](/microsoft-desktop-optimization-pack/agpm/) <br/><br/> 或者 <br/><br/> [组策略管理控制台](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)|1. 转到计算机 **配置** \> **管理模板** \> **Windows组件** \> **Microsoft Defender 防病毒**。<br/><br/>2. 查找名为"关闭策略 **"Microsoft Defender 防病毒。**<br/><br/>3. 选择 **"编辑策略设置**"，并确保策略已禁用。 此操作将启用Microsoft Defender 防病毒。 <br/> (在 Windows Defender 防病毒.Microsoft Defender 防病毒.Windows.)  |

> [!TIP]
> 可以在载入组织设备之前部署策略。

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>将 Microsoft Defender for Endpoint 添加到现有解决方案的排除列表

设置过程的这一步是将 Defender for Endpoint 添加到现有终结点保护解决方案以及组织使用的其他安全产品的排除列表中。

> [!TIP]
> 若要获取有关配置排除项的帮助，请参阅解决方案提供商的文档。

要配置的特定排除项将取决于终结点或Windows运行的版本，下表中列出了这些排除项。
<br/><br/>

|操作系统 |排除 |
|--|--|
|Windows 11 <br/><br/>Windows 10[版本 1803](/windows/release-health/status-windows-10-1803)或更高版本 (请参阅Windows 10[版本) ](/windows/release-health/release-information)<br/><br/>Windows 10，版本 1703 或 1709（已安装[KB4493441）](https://support.microsoft.com/help/4493441) <br/><br/> Windows Server 2022<br/><br/>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019) <br/><br/>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows服务器版本 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCM.exe`<br/>
<br/>此外，在运行新式Windows Server 2012统一解决方案的 Windows Server 2012 R2 和 2016 上，使用[KB5005292](https://support.microsoft.com/en-us/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac)更新 Sense EDR 组件后，需要以下排除项：<br/> |<br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\MsSense.exe`<br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseCnCProxy.exe`<br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseIR.exe`<br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseCE.exe`<br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseSampleUploader.exe`<br/>`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Platform\*\SenseCM.exe`<br/>
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>[WindowsServer 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/>**注意**：监视主机临时文件 6\45 可以是不同的编号子文件夹。 <br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>将现有解决方案添加到列表的排除Microsoft Defender 防病毒

在设置过程的这一步中，将现有解决方案添加到Microsoft Defender 防病毒列表中。 可以从多种方法中选择将排除项添加到Microsoft Defender 防病毒，如下表所列：
<br/><br/>

|方法|需执行的操作|
|---|---|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/><br/> **注意**：Intune 现在是 Microsoft Endpoint Manager 的一Microsoft Endpoint Manager。|1. 转到Microsoft Endpoint Manager[中心并](https://go.microsoft.com/fwlink/?linkid=2109431)登录。<br/><br/>2. **选择"设备** \> **配置文件"，** 然后选择要配置的配置文件。<br/><br/>3. 在"**管理"下**，选择"**属性"。**<br/><br/>4. 选择 **配置设置：编辑**。<br/><br/>5. 展开 **Microsoft Defender 防病毒，** 然后展开 **"Microsoft Defender 防病毒排除项"。**<br/><br/>6. 指定要从扫描中排除的文件和文件夹、扩展Microsoft Defender 防病毒进程。 有关参考，请参阅[Microsoft Defender 防病毒排除项](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)。<br/><br/>7. 选择 **"审阅 + 保存"，** 然后选择"保存 **"。**|
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/)|1. 使用[Configuration Manager](/mem/configmgr/core/servers/manage/admin-console)控制台，转到"资产和Endpoint Protection反恶意软件策略"，然后选择 \>  \> 要修改的策略。<br/><br/>2. 为要从扫描中排除的文件和文件夹、扩展和进程指定Microsoft Defender 防病毒设置。|
|[组策略对象](/previous-versions/windows/desktop/Policy/group-policy-objects)|1. 在组策略管理计算机上，打开组 [](https://technet.microsoft.com/library/cc731212.aspx)策略管理控制台，右键单击要配置的组策略对象，**然后选择编辑**。<br/><br/>2. 在组 **策略管理编辑器** 中，转到"**计算机配置"，** 然后选择"**管理模板"。**<br/><br/>3. 展开树以Windows **排除 \> Microsoft Defender 防病毒 \> 组件**。  (在 Windows Defender 防病毒.Microsoft Defender 防病毒.Windows.)  <br/><br/>4. 双击" **路径排除项"** 设置并添加排除项。<br/><br/>5. 将选项设置为 **已启用**。<br/><br/>6. 在"选项 **"部分** 下，选择"显示 **..."。**<br/><br/>7. 在"值名称"列下的其自己的行 **中指定每个** 文件夹。 如果指定文件，请确保输入该文件的完全限定路径，包括驱动器号、文件夹路径、文件名和扩展名。 在 **"值"****列中输入** 0。<br/><br/>8. 选择"**确定"。**<br/><br/>9. 双击扩展 **排除** 项设置并添加排除项。<br/><br/>10. 将选项设置为 **已启用**。<br/><br/>11. 在"选项 **"部分** 下，选择"显示 **..."。**<br/><br/>12. 在"值名称"列下，在其自己的行中 **输入每个文件** 扩展名。 在 **"值"****列中输入** 0。<br/><br/>13. 选择"**确定"。**|
|本地组策略对象|1. 在终结点或设备上，打开"本地组策略编辑器"。<br/><br/>2. 转到计算机 **配置** 管理模板 \>  \> **Windows组件** \> **Microsoft Defender 防病毒** \> **排除项**。  (在 Windows Defender 防病毒.Microsoft Defender 防病毒.Windows.)  <br/><br/>3. 指定路径和进程排除项。|
|注册表项|1. 导出以下注册表项 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` ：。<br/><br/>2. 导入注册表项。 下面是两个示例：<br/>- 本地路径： `regedit.exe /s c:\temp\ MDAV_Exclusion.reg`<br/>- 网络共享： `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg`|

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>请记住以下有关排除项的要点

向扫描[中添加排除项Microsoft Defender 防病毒，](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)应添加路径和进程排除项。

请记住以下几点：

- *路径排除* 项排除特定文件以及这些文件访问的任何内容。
- *进程排除* 排除排除进程涉及的任何内容，但不排除进程本身。
- 使用进程排除项的完整路径而不是仅按名称列出进程排除项。  (仅名称方法安全性较低。) 
- 如果列出了每个可执行 (.exe) 作为路径排除和进程排除，则进程及其涉及的任何内容都将被排除。

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>设置设备组、设备集合和组织单位

设备组、设备集合和组织单位使安全团队能够高效地管理和分配安全策略。 下表介绍了其中每个组以及如何配置它们。 您的组织可能不会使用所有这三种集合类型。
<br/><br/>

|集合类型|需执行的操作|
|---|---|
|[设备组](/microsoft-365/security/defender-endpoint/machine-groups) (*以前称为)* 组，可使安全运营团队配置安全性功能，例如自动调查和修正。 <br/><br/> 设备组还可用于分配对这些设备的访问权限，以便你的安全运营团队可以执行修正操作（如果需要）。 <br/><br/> 设备组是在 Microsoft 365 Defender[门户中创建的](microsoft-defender-security-center.md)。|1. 转到Microsoft 365 Defender门户 <https://security.microsoft.com> () 。<br/><br/>2. 在左侧导航窗格中，选择"设置 \> **终结点** \> **权限** \> **设备组"。**<br/><br/>3. 选择 **" + 添加设备组"。**<br/><br/>4. 指定设备组的名称和说明。<br/><br/>5. 在 **"自动化级别"** 列表中，选择一个选项。  (建议完全 **- 自动** 修正威胁 。) 若要了解有关各种自动化级别的完整信息，请参阅如何 [修正威胁](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)。<br/><br/>6. 指定匹配规则的条件以确定属于设备组的设备。 例如，可以选择域、操作系统版本，甚至可以使用 [设备标记](/microsoft-365/security/defender-endpoint/machine-tags)。<br/><br/>7. 在" **用户访问** "选项卡上，指定应有权访问设备组中包含的设备的角色。<br/><br/>8. 选择"完成 **"。**|
|[设备集合](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) 使安全运营团队能够管理应用程序、部署合规性设置或在组织的设备上安装软件更新。 <br/><br/> 设备集合是使用 [Configuration Manager 创建的](/mem/configmgr/)。|按照创建集合 [中的步骤操作](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create)。|
|[组织](/azure/active-directory-domain-services/create-ou) 单位使您能够对用户帐户、服务帐户或计算机帐户等对象进行逻辑分组。 <br/><br/> 然后，可以将管理员分配给特定的组织单位，并应用组策略以强制执行目标配置设置。 <br/><br/> 组织单位在域服务[中Azure Active Directory定义](/azure/active-directory-domain-services)。|按照在域服务托管域中创建组织Azure Active Directory[中的步骤操作](/azure/active-directory-domain-services/create-ou)。|

## <a name="next-step"></a>后续步骤

**恭喜！** 你已完成切换到 Defender for [Endpoint 的安装阶段](switch-to-microsoft-defender-migration.md#the-migration-process)！

- [继续执行阶段 3：载入到适用于终结点的 Defender](switch-to-microsoft-defender-onboard.md)
