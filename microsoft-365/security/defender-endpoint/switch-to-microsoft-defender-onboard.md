---
title: 切换到 Microsoft Defender for Endpoint - 载入
description: 转换到 Microsoft Defender for Endpoint。 载入设备，然后卸载非 Microsoft 解决方案。
keywords: migration， Microsoft Defender for Endpoint， edr
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
ms.custom: migrationguides
ms.topic: article
ms.date: 10/07/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 3ce62eb9019b233bf2c52f9ce990813650ac4bbe
ms.sourcegitcommit: 166bf635c0905ae12c04b1865cb17aadef81e82a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2021
ms.locfileid: "60245701"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>切换到 Microsoft Defender for Endpoint - 阶段 3：载入

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![阶段 1：准备 3。](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[阶段 1：准备](switch-to-microsoft-defender-prepare.md) | [![阶段 2：设置](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[阶段 2：设置](switch-to-microsoft-defender-setup.md) | ![阶段 3：开始使用](images/phase-diagrams/onboard.png)<br/>阶段 3：开始使用 |
|--|--|--|
|| |*你在这里！* |

**欢迎使用切换到 Defender [for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)** 的第 3 阶段。 此迁移阶段包括以下步骤：

1. [将设备载入到 Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint)。
2. [运行检测测试](#run-a-detection-test)。
3. [确认Microsoft Defender 防病毒终结点处于被动模式](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints)。
4. [获取 Microsoft Defender 防病毒 的更新](#get-updates-for-microsoft-defender-antivirus)。
5. [卸载非 Microsoft 解决方案](#uninstall-your-non-microsoft-solution)。
6. [确保适用于终结点的 Defender 正常工作](#make-sure-defender-for-endpoint-is-working-correctly)。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>将设备载入到 Microsoft Defender for Endpoint

1. 转到"Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () 并登录。

2. 选择 **设置** \> **设备管理** \> **"下** (**终结点载入**) 。

3. 在 **"选择操作系统以开始载入过程"列表中** ，选择操作系统。

4. 在 **"部署方法**"下，选择一个选项。 按照链接和提示载入组织设备。 需要帮助？ 请参阅 [本文 (](#onboarding-methods) 载入方法) 。

> [!NOTE]
> 如果在载入时出错，请参阅排查 [Microsoft Defender 终结点载入问题](troubleshoot-onboarding.md)。 本文介绍如何解决终结点上的载入问题和常见错误。

### <a name="onboarding-methods"></a>载入方法

部署方法因操作系统和首选方法而异。 下表列出了可帮助你载入 Defender for Endpoint 的资源：

|操作系统  |方法  |
|---------|---------|
|Windows 10或更高版本<br/><br/>WindowsServer 2019 或更高版本<br/><br/>Windows服务器版本 1803 或更高版本<br/><br/>Windows Server 2012R2 和 2016 <sup> [[1](#fn1)]<sup>  |   [本地脚本 (最多 10 台设备) ](configure-endpoints-script.md)<br><br/>   [组策略](configure-endpoints-gp.md)<br/><br/>[Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)<br/><br/>[Microsoft Endpoint Manager/Intune (移动设备管理) ](configure-endpoints-mdm.md)<br>    [VDI 脚本](configure-endpoints-vdi.md) <br><br> **注意**：本地脚本适用于概念证明，但不应用于生产部署。 对于生产部署，我们建议使用组策略、Microsoft Endpoint Configuration Manager或 Intune。
|Windows Server 2008 R2 SP1 | [Microsoft Monitoring Agent (MMA) ](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma)或 Azure [Defender](/azure/security-center/security-center-wdatp) <br><br> **注意**：Microsoft Monitoring Agent现在为 Azure Log Analytics 代理。 若要了解更多信息，请参阅 [Log Analytics agent overview](/azure/azure-monitor/platform/log-analytics-agent)。  
|Windows 8.1 企业版<br/><br/>Windows 8.1 专业版<br/><br/>Windows 7 SP1 Pro<br/><br/>Windows 7 SP1| [Microsoft Monitoring Agent (MMA) ](onboard-downlevel.md) <br><br> **注意**：Microsoft Monitoring Agent现在为 Azure Log Analytics 代理。 若要了解更多信息，请参阅 [Log Analytics agent overview](/azure/azure-monitor/platform/log-analytics-agent)。  
| macOS：<br/>11.3.1 (大 Sur) <br/>10.15 (加泰罗尼亚语) <br/>10.14 (Mojave)  | [本地脚本](mac-install-manually.md)<br/><br/>[Microsoft Endpoint Manager](mac-install-with-intune.md)<br/><br/>[JAMF Pro](mac-install-with-jamf.md)<br/><br/>[移动设备管理](mac-install-with-other-mdm.md)   |
| Linux：<br/>RHEL 7.2+<br/>CentOS Linux 7.2+<br/>Ubuntu 16 LTS 或更高版本 LTS<br/>SLES 12+<br/>Debian 9+<br/>Oracle Linux 7.2 |  [本地脚本](linux-install-manually.md) <br><br/> [百分百](linux-install-with-puppet.md) <br><br/> [Ansible](linux-install-with-ansible.md)|  
| iOS | [Microsoft Endpoint Manager](ios-install.md)     |
|Android  | [Microsoft Endpoint Manager](android-intune.md)               | 




 (<a id="fn1">1</a>) Windows Server 2016 Windows Server 2012 R2 将需要按照载入服务器中的说明Windows[载入](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)。


## <a name="run-a-detection-test"></a>运行检测测试

若要验证载入的设备是否正确连接到 Defender for Endpoint，可以运行检测测试。

<br/><br/>

|操作系统|指南|
|---|---|
|Windows 10或更高版本<br/><br/>Windows Server 2022<br/><br/>Windows Server 2019<br/><br/>Windows服务器、版本 1803 或更高版本<br/><br/>Windows Server 2016<br/><br/>Windows Server 2012 R2|请参阅 [运行检测测试](run-detection-test.md)。<br/><br/>请访问 Defender for Endpoint 演示方案站点 <https://demo.wd.microsoft.com> () 并尝试一个或多个方案。 例如，尝试 **云提供的保护演示** 方案。|
|macOS：<br/> 11.3.1 (大 Sur) <br/>10.15 (加泰罗尼亚语) <br/>10.14 (Mojave) |从 下载并使用 DIY 应用 <https://aka.ms/mdatpmacosdiy> 。 <br/><br/> 有关详细信息，请参阅[macOS 上的 Defender for Endpoint。](microsoft-defender-endpoint-mac.md)|
|Linux：<br/> RHEL 7.2+<br/>CentOS Linux 7.2+<br/>Ubuntu 16 LTS 或更高版本 LTS<br/>SLES 12+<br/>Debian 9+<br/>Oracle Linux 7.2|1. 运行以下命令，并查找 **结果 1：。** `mdatp health --field real_time_protection_enabled`<br/><br/>2. 打开"终端"窗口，并运行以下命令 `curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt` ：。<br/><br/>3. 运行以下命令列出任何检测到的威胁 `mdatp threat list` ：。<br/><br/>有关详细信息，请参阅[Linux 上的 Defender for Endpoint。](microsoft-defender-endpoint-linux.md)|


## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>确认Microsoft Defender 防病毒终结点处于被动模式

现在终结点已载入到 Defender for Endpoint，下一步是确保Microsoft Defender 防病毒处于被动模式。 您可以使用多种方法之一，如下表所述：

<br/><br/>

|方法|需执行的操作|
|---|---|
|命令提示符|1. 在 Windows上，打开命令提示符。<br/><br/>2. 键入 `sc query windefend` ，然后按 Enter。<br/><br/>3. 查看结果以确认Microsoft Defender 防病毒处于被动模式。|
|PowerShell|1.在Windows上，以Windows PowerShell打开"登录"。<br/><br/>2. 运行以下 PowerShell cmdlet：。 `Get-MpComputerStatus|select AMRunningMode` <br/><br/>3. 查看结果。 你应该会看到被动 **模式**。|
|Windows 安全中心应用|1.在Windows上，打开Windows 安全中心应用。<br/><br/>2. 选择 **病毒&威胁防护。**<br/><br/>3. **Who保护我？选择** 管理 **提供程序**。<br/><br/>4. 在"**安全提供程序"** 页上的"**防病毒**"下 **，Microsoft Defender 防病毒"打开"。**|
|任务管理器|1. 在Windows上，打开"任务管理器"应用。<br/><br/>2. 选择" **详细信息"** 选项卡。在 **MsMpEng.exe** 查找列表。|

> [!NOTE]
> 在某些版本的 *Windows Defender 防病毒，Microsoft Defender 防病毒* 可能会看到Windows。
> 若要了解有关被动模式和主动模式的详细信息，请参阅有关被动Microsoft Defender 防病毒[的详细信息](microsoft-defender-antivirus-compatibility.md#more-details-about-microsoft-defender-antivirus-states)。

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>在 Microsoft Defender 防病毒 服务器上Windows手动设置为被动模式

若要在 Windows Microsoft Defender 防病毒 Server、版本 1803 或更高版本、Windows Server 2019 或 Windows Server 2022 上将 Windows 设置为被动模式，请按照以下步骤操作：

1. 打开注册表编辑器，然后导航到：

   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. 编辑 (或创建) **ForceDefenderPassiveMode** 的 DWORD 条目，并指定以下设置：
   - 将 DWORD 的值设置为 **1。**
   - 在 **"基本**"下，**选择"十六进制"。**

> [!NOTE]
> 可以使用其他方法来设置注册表项，如下所示：
>
> - [组策略首选项](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
> - [本地组策略对象工具](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
> - [Configuration Manager 中的程序包](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>从Microsoft Defender 防病毒开始Windows Server 2016

如果要使用Windows Server 2016，可能需要手动Microsoft Defender 防病毒启动。 可以在设备上使用 PowerShell cmdlet `mpcmdrun.exe -wdenable` 执行此任务。

## <a name="get-updates-for-microsoft-defender-antivirus"></a>获取更新Microsoft Defender 防病毒

确保Microsoft Defender 防病毒保持最新状态至关重要，可确保你的设备具有防止新的恶意软件和攻击技术所需的最新技术和功能，即使 Microsoft Defender 防病毒 处于被动模式。  (请参阅[Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md).) 

有两种类型的更新与使Microsoft Defender 防病毒保持最新有关：

- 安全智能更新
- 产品更新

若要获取更新，请按照管理更新和应用Microsoft Defender 防病毒[中的指南。](manage-updates-baselines-microsoft-defender-antivirus.md)

## <a name="uninstall-your-non-microsoft-solution"></a>卸载非 Microsoft 解决方案

如果此时你拥有：

- 将组织设备载入到 Defender for Endpoint，
- Microsoft Defender 防病毒并启用，

然后，下一步是卸载非 Microsoft 防病毒、反恶意软件和终结点保护解决方案。 卸载非 Microsoft 解决方案时，Microsoft Defender 防病毒被动模式切换到主动模式。 在大多数情况下，这会自动发生。

若要获取有关卸载非 Microsoft 解决方案的帮助，请联系他们的技术支持团队。

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>确保适用于终结点的 Defender 正常工作

现在，你已载入 Defender for Endpoint，并且已卸载以前的非 Microsoft 解决方案，下一步是确保 Defender for Endpoint 正常工作。 执行此任务的一个好方法就是访问 Defender for Endpoint 演示方案站点 [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) () 。 尝试该页面上的一个或多个演示方案，包括以下方案：

- 云端保护
- PUA (可能不需要) 
- 网络保护 (NP) 

## <a name="next-steps"></a>后续步骤

**恭喜！** 你已完成到 [Defender for Endpoint 的迁移](switch-to-microsoft-defender-migration.md#the-migration-process)！

- [访问安全操作仪表板，Microsoft 365 Defender](security-operations-dashboard.md)门户 [https://security.microsoft.com](https://security.microsoft.com) () 。
- [管理适用于终结点的 Defender，迁移后](manage-atp-post-migration.md)。
