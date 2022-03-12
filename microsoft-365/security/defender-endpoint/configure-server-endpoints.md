---
title: 将Windows载入 Microsoft Defender for Endpoint 服务
description: 载入Windows服务器，以便它们可以将传感器数据发送到 Microsoft Defender for Endpoint 传感器。
keywords: 载入服务器， 服务器， 2012r2， 2016， 2019， 服务器载入， 设备管理， 配置适用于终结点服务器的 Microsoft Defender， 载入适用于终结点服务器的 Microsoft Defender， 载入适用于终结点服务器的 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5f0b846fdbfaa76250ae64ae281afc9592a24eb4
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2022
ms.locfileid: "63450306"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a>将Windows载入 Microsoft Defender for Endpoint 服务

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- Windows Server 2012 R2
- Windows Server 2016
- Windows Server Semi-Annual Enterprise Channel
- Windows Server 2019 及更高版本
- Windows Server 2019 核心版本
- Windows Server 2022
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configserver-abovefoldlink)。

Defender for Endpoint 扩展支持，还包括 Windows Server 操作系统。 此支持通过 Microsoft 365 Defender 控制台无缝提供高级攻击检测和Microsoft 365 Defender功能。 对 Windows Server 的支持可更深入地了解服务器活动、内核和内存攻击检测的范围，并启用响应操作。

本主题介绍如何将特定服务器Windows Microsoft Defender for Endpoint。

有关如何下载和使用 Windows 安全中心 基线的Windows，请参阅 Windows 安全中心 [Baselines](/windows/device-security/windows-security-baselines)。

## <a name="windows-server-onboarding-overview"></a>Windows服务器载入概述

需要完成以下常规步骤，以成功载入服务器。

![插图：Windows 和 Windows 10 设备的载入流程](images/server-onboarding-tools-methods.png)

**Windows Server 2012 R2 和 Windows Server 2016 (Preview)**

>[!IMPORTANT]
> 若要使用此功能，你需要在"终结点"部分Microsoft 365 Defender预览功能。 导航到[Microsoft 365 Defender > 设置 >终结点>高级功能，](https://security.microsoft.com/preferences2/integration)然后打开预览功能。

- 下载安装和载入程序包
- 应用安装包
- 按照相应工具的载入步骤操作

**Windows Server Semi-Annual Enterprise Channel and Windows Server 2019**

- 下载载入程序包
- 按照相应工具的载入步骤操作

>[!IMPORTANT]
>若要有资格购买适用于 Endpoint Server SKU 的 Microsoft Defender，必须已购买以下任一许可证的组合最低要求：Windows E5/A5、Microsoft 365 E5/A5 或 Microsoft 365 E5 安全性 订阅许可证。  有关许可详细信息，请参阅产品 [条款](https://www.microsoft.com/licensing/terms/productoffering/MicrosoftDefenderforEndpointServer/all)。  



### <a name="new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution-preview"></a>新式Windows Server 2012预览版中的新 R2 和 2016 (2016) 

上一次实现 Windows Server 2012 R2 和 Windows Server 2016要求使用 Microsoft Monitoring Agent (MMA) 。

新的统一解决方案包通过删除依赖项和安装步骤更轻松地载入服务器。 此外，此统一解决方案包还进行了以下重大改进：

- [Microsoft Defender 防病毒](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows) R2 [的下一](/microsoft-365/security/defender-endpoint/next-generation-protection)代Windows Server 2012保护
- [攻击面减少 (ASR) 规则](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules)
- [网络保护](/microsoft-365/security/defender-endpoint/network-protection)
- [受控文件夹访问权限](/microsoft-365/security/defender-endpoint/controlled-folders)
- [PUA 阻止 (可能不需要) 的应用程序](/microsoft-365/security/defender-endpoint/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [改进的检测功能](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)
- [设备和文件](/microsoft-365/security/defender-endpoint/respond-machine-alerts) 上的扩展响应 [功能](/microsoft-365/security/defender-endpoint/respond-file-alerts)
- [EDR阻止模式](/microsoft-365/security/defender-endpoint/edr-in-block-mode)
- [实时响应](/microsoft-365/security/defender-endpoint/live-response)
- [AIR (自动调查和) ](/microsoft-365/security/defender-endpoint/automated-investigations)
- [防篡改保护](/microsoft-365/security/defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection)

根据要载入的服务器，统一解决方案会安装 Microsoft Defender 防病毒 和/或 EDR 传感器。 下表指示已安装的组件以及默认内置组件。

|服务器版本|AV|EDR|
|----|----|----|
|Windows Server 2012 R2 SP1|![是。](images/svg/check-yes.svg)|![是。](images/svg/check-yes.svg)|
|Windows Server 2016|内置|![是。](images/svg/check-yes.svg)|
|Windows Server 2019 或更高版本|内置|内置|

如果之前已使用 MMA 载入服务器，请按照服务器迁移中提供的指南迁移到新[](server-migration.md)解决方案。

>[!NOTE]
>虽然此 R2 Windows Server 2012和 Windows Server 2016 的载入方法为预览版，但可以选择继续使用之前使用 Microsoft Monitoring Agent (MMA) 。 有关详细信息，请参阅使用 [MMA 安装和配置终结点](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma)。

#### <a name="known-issues-and-limitations-on-the-new-unified-solution-package-for-windows-server-2012-r2-and-2016"></a>R2 和 2016 的新统一解决方案包的已知Windows Server 2012限制

以下具体信息适用于 R2 和 Windows Server 2012 2016 的新统一解决方案包：

- 确保满足允许访问代理服务器中的 [Microsoft Defender for Endpoint 服务 URL 中](/microsoft-365/security/defender-endpoint/configure-proxy-internet?enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) 指定的连接要求。 它们等效于 Windows Server 2019。 
- 我们将调查在使用静态 TelemetryProxyServer 且无法从系统帐户上下文访问证书吊销列表 (CRL) URL 时与云的 Windows Server 2012 R2 连接问题。 立即缓解措施是使用提供此类连接的备用代理选项，或通过系统帐户上下文上的 WinInet 设置配置同一代理。
- 以前，OMS/Log Analytics 网关Microsoft Monitoring Agent (MMA) 或Windows Server 2016，以便 OMS/Log Analytics 网关能够连接到 Defender 云服务。 新解决方案（如 Windows Server 2019、Windows Server 2022 和 Windows 10 上的 Microsoft Defender for Endpoint）不支持此网关。

- On Windows Server 2016， verify that Microsoft Defender 防病毒 is installed， is active and up to date. 可以使用"更新"下载并安装Windows版本。 或者，从 [Microsoft](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4052623) 更新目录或 [MMPC 手动下载更新包](https://go.microsoft.com/fwlink/?linkid=870379&arch=x64)。  
- 在 Windows Server 2012 R2 上，没有用于Microsoft Defender 防病毒。 此外，Windows Server 2016用户界面只允许基本操作。 若要在本地设备上执行操作，请参阅使用 [PowerShell、WMI 和 MPCmdRun.exe管理 Microsoft Defender for Endpoint ](/microsoft-365/security/defender-endpoint/manage-mde-post-migration-other-tools)。 因此，专门依赖用户交互的功能（如提示用户做出决定或执行特定任务）可能无法如期工作。 建议禁用或不启用用户界面，也建议在任何托管服务器上进行用户交互，因为它可能会影响保护功能。
- 并非所有攻击面减少规则都适用于所有操作系统。 请参阅 [攻击面减少 (ASR) 规则](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules)。
- 若要启用 [网络保护](/microsoft-365/security/defender-endpoint/network-protection)，需要其他配置：
  - `Set-MpPreference -EnableNetworkProtection Enabled`
  - `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`
  - `Set-MpPreference -AllowNetworkProtectionDownLevel 1`
  - `Set-MpPreference -AllowDatagramProcessingOnWinServer 1`

  此外，在网络通信量较高的计算机上，强烈建议在广泛启用此功能之前，先在环境中执行性能测试。 您可能需要考虑额外的资源消耗。
- 在 Windows Server 2012 R2 上，网络事件可能不会在时间线中填充。 This issue requires a Windows Update released as part of the [October 12， 2021 monthly rollup (KB5006714) ](https://support.microsoft.com/topic/october-12-2021-kb5006714-monthly-rollup-4dc4a2cd-677c-477b-8079-dcfef2bda09e).
- 不支持操作系统升级。 卸载，然后在升级之前卸载。
- 服务器角色的自动排除 *在* Windows Server 2012 R2 上不受支持;但是，操作系统文件的内置排除项是。 有关添加排除项详细信息，请参阅病毒扫描建议[Enterprise运行](https://support.microsoft.com/topic/virus-scanning-recommendations-for-enterprise-computers-that-are-running-currently-supported-versions-of-windows-kb822158-c067a732-f24a-9079-d240-3733e39b40bc)当前受支持版本的病毒扫描Windows。
- 目前，如果您选择卸载和卸载新式统一解决方案，并重新载入以前的基于 MMA 的 EDR 传感器，则可能会遇到重复`MsSenseS.exe`崩溃。 

作为解决方法，请删除以下注册表项（如果存在）：
- `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\WMI\Security\fdedb2b8-61e4-4a7e-8b15-abf214a08fcc`
- `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\WMI\Security\c60418cc-7e07-400f-ae3b-d521c5dbd96f`

可以使用以下命令：

```cmd
reg delete HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\WMI\Security /v fdedb2b8-61e4-4a7e-8b15-abf214a08fcc /f
reg delete HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\WMI\Security /v c60418cc-7e07-400f-ae3b-d521c5dbd96f /f
```
无需重新启动。


<a name="integration-with-azure-defender"></a>

## <a name="integration-with-microsoft-defender-for-cloud"></a>与 Microsoft Defender for Cloud 集成

Microsoft Defender for Endpoint 与 Microsoft Defender for Cloud 无缝集成。 你可以自动载入服务器，使 Azure Defender 监视的服务器显示在 Defender for Endpoint 中，并作为 Microsoft Defender 云客户进行详细调查。

有关详细信息，请参阅与 [Microsoft Defender for Cloud 集成](azure-server-integration.md)。

> [!NOTE]
> 对于Windows Server 2012新式统一解决方案预览的 R2 和 2016，尚未提供与 Microsoft Defender for Cloud/Microsoft Defender 服务器集成以用于警报和自动部署。 尽管你可以手动在这些计算机上安装新解决方案，但 Microsoft Defender for Cloud 中不会显示任何警报。

> [!NOTE]
> - Microsoft Defender for servers 和 Microsoft Defender for Endpoint 之间的集成已扩展为支持 Windows Server 2022、[Windows Server 2019 和 Windows Virtual Desktop (WVD) ](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)。
> - 已针对客户禁用利用此集成的服务器终结点Office 365 GCC监视。

## <a name="windows-server-2012-r2-and-windows-server-2016"></a>Windows Server 2012 R2 和 Windows Server 2016

> [!NOTE]
> 虽然此 R2 Windows Server 2012和 Windows Server 2016 的载入方法为预览版，但可以选择继续使用之前使用 Microsoft Monitoring Agent (MMA) 。 有关详细信息，请参阅使用 [MMA 安装和配置终结点](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma)。

### <a name="prerequisites"></a>先决条件

**R2 Windows Server 2012的先决条件**

如果你已使用最新的每月汇总程序包完全更新计算机 [](https://support.microsoft.com/topic/october-12-2021-kb5006714-monthly-rollup-4dc4a2cd-677c-477b-8079-dcfef2bda09e)，则没有 **其他** 先决条件。

安装程序程序包将检查是否通过更新安装了以下组件：

- [客户体验和诊断遥测更新](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)
- [更新中通用 C 运行时Windows](https://support.microsoft.com/topic/update-for-universal-c-runtime-in-windows-c0514201-7fe6-95a3-b0a5-287930f3560c)

**部署Windows Server 2016** 

除了使用 LCU (最新累积更新) ，Microsoft Defender 防病毒计算机是否处于活动状态且保持最新。 可以使用"更新"下载并安装Windows版本。 或者，从 [Microsoft](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4052623) 更新目录或 [MMPC 手动下载更新包](https://go.microsoft.com/fwlink/?linkid=870379&arch=x64)。 

> [!NOTE]
> 若要将 Windows Defender 的内置版本（版本号从 4.10 开始）成功更新到最新可用平台，必须已应用服务堆栈更新以及等于或晚于 2018 年 9 月 20 日的最新累积更新 (LCU) KB4457127 (OS 内部版本 14393.2515) 。

**使用第三方安全解决方案运行的先决条件**

如果你打算使用第三方反恶意软件解决方案，你需要在被动Microsoft Defender 防病毒运行该解决方案。 在安装和载入过程中，必须记住设置为被动模式。

**Windows Server 2012 R2 和 2016 上的 Microsoft Defender for Endpoint 的新更新程序包**

若要接收适用于传感器组件的常规产品改进和EDR，请确保已应用Windows[更新 KB5005292](https://go.microsoft.com/fwlink/?linkid=2168277) 或获得批准。 此外，若要使保护组件保持更新，请参阅管理Microsoft Defender 防病毒[更新和应用基线](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。

### <a name="onboarding-steps-summary"></a>载入步骤摘要

- 步骤 1 [：下载安装和载入程序包](#step-1-download-installation-and-onboarding-packages)
- 步骤 2 [：应用安装和载入程序包](#step-2-apply-the-installation-and-onboarding-package)
- 步骤 3 [：完成载入步骤](#step-3-complete-the-onboarding-steps) 


### <a name="step-1-download-installation-and-onboarding-packages"></a>步骤 1：下载安装和载入程序包

你将需要从 **门户下载安装和****载入** 程序包。

> [!div class="mx-imgBorder"]
> ![载入仪表板的图像](images/install-agent-onboard.png)


   > [!NOTE]
   > 在 Windows Server 2012R2 上，Microsoft Defender 防病毒安装程序包进行安装，并且将处于活动状态，除非你将安装包设置为被动模式。 在Windows Server 2016，Microsoft Defender 防病毒必须作为一项功能进行安装 (请参阅在继续安装之前) 切换到 [MDE](/microsoft-365/security/defender-endpoint/switch-to-mde-phase-2#re-enable-microsoft-defender-antivirus-on-windows-server-2016)) 完全更新。
   > 
   > 如果运行的是非 Microsoft 反恶意软件解决方案，请确保在安装之前将 Microsoft Defender 防病毒 (排除项从"Defender 进程"选项卡) 上的 [Microsoft Defender](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 进程列表中添加到非 Microsoft 解决方案。  还建议将非 Microsoft 安全解决方案添加到 Defender 防病毒排除列表。


安装 **程序包包含** 安装 Microsoft Defender for Endpoint 代理的 MSI 文件。

**载入包包含** 以下文件：

- `OptionalParamsPolicy` - 包含启用示例集合的设置
- `WindowsDefenderATPOnboardingScript.cmd` - 包含载入脚本

使用以下步骤下载程序包： 

1. In Microsoft 365 Defender， go to **设置 > Device Management > Onboarding**.

2. 选择 **Windows Server 2012 R2 和 2016**。

3. 选择 **下载安装程序包** 并保存.msi文件。 
 
4. 选择 **下载载入程序包并** 保存.zip文件。

5. 使用任一选项安装安装程序包Microsoft Defender 防病毒。 安装需要管理权限。



### <a name="step-2-apply-the-installation-and-onboarding-package"></a>步骤 2：应用安装和载入程序包
在此步骤中，你将在将设备载入到 Microsoft Defender for Endpoint 云环境之前安装所需的防护和检测组件，以准备载入计算机。 确保 [满足所有](#prerequisites) 先决条件。 

   > [!NOTE]
   > Microsoft Defender 防病毒将安装并处于活动状态，除非你将它设置为被动模式。 

#### <a name="options-to-install-the-microsoft-defender-for-endpoint-packages"></a>安装适用于终结点的 Microsoft Defender 程序包的选项

在上一部分中，你下载了安装程序包。 安装程序包包含所有 Microsoft Defender for Endpoint 组件的安装程序。 

可以使用以下任一选项安装代理：
- [使用命令行安装](#install-microsoft-defender-for-endpoint-using-the-command-line)
- [使用脚本安装](#install-microsoft-defender-for-endpoint-using-a-script)
- [使用组策略应用安装和载入程序包](#apply-the-microsoft-defender-for-endpoint-installation-and-onboarding-packages-using-group-policy)

##### <a name="install-microsoft-defender-for-endpoint-using-the-command-line"></a>使用命令行安装 Microsoft Defender For Endpoint
使用上一步中的安装程序包安装 Microsoft Defender for Endpoint。 


运行以下命令以安装 Microsoft Defender for Endpoint：

```console
Msiexec /i md4ws.msi /quiet
```

若要卸载，请确保首先使用相应的卸载脚本将计算机卸载。 然后，使用控制面板 \> 程序 \> 程序和功能执行卸载。

或者，运行以下卸载命令以卸载 Microsoft Defender for Endpoint：

```console
Msiexec /x md4ws.msi /quiet
```

必须使用相同的程序包进行安装，上述命令才能成功。

该 `/quiet` 开关禁止显示所有通知。

> [!NOTE]
> Microsoft Defender 防病毒不会自动进入被动模式。 如果运行的是非 Microsoft Microsoft Defender 防病毒/反恶意软件解决方案，你可以选择将设置在被动模式下运行。 对于命令行安装，`FORCEPASSIVEMODE=1`可选组件会立即Microsoft Defender 防病毒被动模式，以避免干扰。 然后，为了确保 Defender 防病毒在载入后保持被动模式以支持 EDR 阻止等功能，请设置"ForceDefenderPassiveMode"注册表项。

对 Windows Server 的支持可更深入地了解服务器活动、内核和内存攻击检测的范围，并启用响应操作。

##### <a name="install-microsoft-defender-for-endpoint-using-a-script"></a>使用脚本安装 Microsoft Defender for Endpoint

可以使用安装程序 [脚本来帮助](server-migration.md#installer-script) 自动执行安装、卸载和载入。 有关详细信息，请参阅以下部分中的说明，以将脚本与组策略一同使用。

##### <a name="apply-the-microsoft-defender-for-endpoint-installation-and-onboarding-packages-using-group-policy"></a>使用组策略应用 Microsoft Defender for Endpoint 安装和载入程序包

1. 创建组策略： <br> 打开 GPMC [ (](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)组策略管理) ，右键单击要配置的组策略对象，**然后单击新建。** 在显示的对话框中输入新 GPO 的名称，然后单击"确定 **"**。

2. 打开 GPMC (组策略管理) ，右键单击要配置的组策略对象 (GPO) 然后单击"编辑 **"**。[](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)

3. 在组 **策略管理编辑器中**，转到" **计算机配置**"，然后转到" **首选项**"，然后转到" **控制面板设置"**。

4. 右键单击 **计划任务**，指向新建，然后单击立即任务 (**任务Windows 7)**。

5. 在打开 **的任务** 窗口中，转到常规 **选项卡** 。在 **"安全选项"** 下，单击 **"更改用户或组** "并键入"系统"，然后单击" **检查名称"** ，然后单击"确定 **"**。 NT AUTHORITY\SYSTEM 显示为任务将运行的用户帐户。

6. Select **Run whether user is logged on or not and** check the **Run with highest privileges** check box.

7. 在"名称"字段中，键入计划任务策略的适当名称 (例如，Defender for Endpoint Deployment) 。

8. 转到操作 **选项卡，** 然后选择新建 **...** 确保在 **"操作"** 字段中选择了"启动 **程序** "。 安装程序 [脚本](server-migration.md#installer-script) 处理安装，在安装完成后立即执行载入步骤。 选择 *C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe* ，然后提供参数：

    ```console
     -ExecutionPolicy RemoteSigned \\servername-or-dfs-space\share-name\install.ps1 -OnboardingScript \\servername-or-dfs-space\share-name\windowsdefenderatponboardingscript.cmd
    ```  

     >[!NOTE]
    >推荐的执行策略设置为 `Allsigned`。 如果脚本作为 SYSTEM 在终结点上运行，则需要将脚本的签名证书导入到本地计算机受信任发布者存储中。

    \\使用共享文件的文件服务器的完全限定域名 (FQDN) ，将 servername-or-dfs-space\share-name 替换为 UNC *install.ps1* 路径。 安装程序包md4ws.msi必须放在同一目录中。  还要确保 UNC 路径的权限允许对正在安装平台的计算机帐户进行读取访问。

   

    对于您希望Microsoft Defender 防病毒 Microsoft 反恶意软件解决方案共存的方案，请添加 $Passive 参数以在安装过程中设置被动模式。

9. 选择 **"确定** "并关闭任何打开的 GPMC 窗口。

10. 若要将 GPO 链接到组织单位 (OU) ，请右键单击并选择" **链接现有 GPO"**。 在显示的对话框中，选择要链接的组策略对象。 单击“**确定**”。

有关其他配置设置，请参阅[配置示例集合设置和其他](configure-endpoints-gp.md#configure-sample-collection-settings)[建议的配置设置](configure-endpoints-gp.md#other-recommended-configuration-settings)。

### <a name="step-3-complete-the-onboarding-steps"></a>步骤 3：完成载入步骤

以下步骤仅适用于使用第三方反恶意软件解决方案时。 你需要将以下设置应用于Microsoft Defender 防病毒模式设置。 验证是否正确配置了它：

1. 设置以下注册表项：
    - 路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
    - 名称：`ForceDefenderPassiveMode`
    - 类型： `REG_DWORD`
    - 值：`1`

2. 运行以下 PowerShell 命令以验证被动模式是否配置：

    ```powershell
    Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
    ```

3. 确认找到包含被动模式事件的最近事件：

    ![被动模式验证结果的图像](images/atp-verify-passive-mode.png)

> [!IMPORTANT]
>
> - 当你使用 Microsoft Defender for Cloud 监视服务器时，会自动在美国为美国用户创建 (，在欧盟为欧洲用户创建，而英国为英国用户自动创建) 。
Defender for Endpoint 收集的数据存储在预配期间标识的租户地理位置中。
> - 如果在使用 Microsoft Defender for Cloud 之前使用 Defender for Endpoint，则数据将存储在创建租户时指定的位置，即使以后与 Microsoft Defender for Cloud 集成。
> - 配置后，你无法更改数据存储的位置。 如果需要将数据移动到其他位置，需要联系 Microsoft 支持部门来重置租户。
> - Windows Server 2019 和 Windows Server 2022 的载入Microsoft Endpoint Manager目前附带了一个脚本。 若要详细了解如何在 Configuration Manager 中部署脚本，请参阅 Configuration [Manager 中的程序包和程序](/configmgr/apps/deploy-use/packages-and-programs)。
> - 本地脚本适用于概念证明，但不应用于生产部署。 对于生产部署，我们建议使用组策略，或Microsoft Endpoint Configuration Manager。



## <a name="windows-server-semi-annual-enterprise-channel-and-windows-server-2019-and-windows-server-2022"></a>Windows Server Semi-Annual Enterprise Channel and Windows Server 2019 and Windows Server 2022

Windows Server 2019 和 Windows Server 2022 到 Microsoft Endpoint Manager的载入包目前附带了一个脚本。 若要详细了解如何在 Configuration Manager 中部署脚本，请参阅 Configuration [Manager 中的程序包和程序](/configmgr/apps/deploy-use/packages-and-programs)。

### <a name="download-package"></a>下载包

1. In Microsoft 365 Defender， go to **设置 > Device Management > Onboarding**.

2. 选择 **Windows Server 1803 和 2019**。

3. 选择 **下载程序包**。 将其另存为WindowsDefenderATPOnboardingPackage.zip。

4. 按照完成载入步骤 [部分中提供的步骤](#step-3-complete-the-onboarding-steps) 操作。


## <a name="verify-the-onboarding-and-installation"></a>验证载入和安装

验证Microsoft Defender 防病毒和 Microsoft Defender for Endpoint 是否正在运行。

## <a name="run-a-detection-test-to-verify-onboarding"></a>运行检测测试以验证载入

载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。 有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint](run-detection-test.md) 设备运行检测测试。

> [!NOTE]
> 虽然Microsoft Defender 防病毒运行，但建议这样做。 如果另一个防病毒供应商产品是主要终结点保护解决方案，可以在被动模式下运行 Defender 防病毒。 在验证 Microsoft Defender for Endpoint 传感器是否处于运行状态后，你 (被动) 处于打开状态。

1. 运行以下命令以验证Microsoft Defender 防病毒安装：

    >[!NOTE]
    >只有在将 Microsoft Defender 防病毒用作活动的反恶意软件解决方案时，才需要执行此步骤。

    `sc.exe query Windefend`


    如果结果是"指定的服务作为已安装的服务不存在"，则需要安装Microsoft Defender 防病毒。 


    有关如何使用组策略在 Microsoft Defender 防病毒 服务器上配置和管理 Windows 的信息，请参阅使用组策略设置配置[和管理](use-group-policy-microsoft-defender-antivirus.md)Microsoft Defender 防病毒。

2. 运行以下命令以验证 Microsoft Defender for Endpoint 是否正在运行：

    `sc.exe query sense`

    结果应显示它正在运行。 如果你遇到载入问题，请参阅 [载入疑难解答](troubleshoot-onboarding.md)。

## <a name="run-a-detection-test"></a>运行检测测试

按照对新载入 [的设备运行检测](run-detection-test.md) 测试中的步骤验证服务器是否向终结点服务的 Defender 报告。

## <a name="next-steps"></a>后续步骤

成功将设备载入服务后，你需要配置适用于终结点的 Microsoft Defender 的单个组件。 按照 [采用顺序](prepare-deployment.md#adoption-order) 指导如何启用各种组件。

## <a name="offboard-windows-servers"></a>载出Windows服务器

可以使用适用于 Windows 10 客户端设备的相同方法从 Windows Server 2012 R2、Windows Server 2016、Windows Server (SAC) 、Windows Server 2019 和 Windows Server 2019 Core 版本上离开。

- [使用组策略的载出设备](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [使用 Configuration Manager 的载出设备](configure-endpoints-sccm.md#offboard-devices-using-configuration-manager)
- [使用移动设备管理工具离开并监视设备](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)
- [使用本地脚本的载出设备](configure-endpoints-script.md#offboard-devices-using-a-local-script)

对于其他Windows版本，有两个选项可以Windows服务器：

- 卸载 MMA 代理
- 删除 Defender for Endpoint 工作区配置

>[!NOTE]
> 如果你运行的是适用于需要 MMA 的 Windows Server 2016 Windows Server 2012 R2 的 Microsoft Defender for Endpoint，则适用于其他 Windows 服务器版本的这些载出说明也适用。 有关迁移到新的未关注解决方案的说明，请参阅 [Microsoft Defender for Endpoint 中的服务器迁移方案](/microsoft-365/security/defender-endpoint/server-migration)。

## <a name="related-topics"></a>相关主题

- [载入以前版本的 Windows](onboard-downlevel.md)
- [载入 Windows 10 设备](configure-endpoints.md)
- [载入非 Windows 设备](configure-endpoints-non-windows.md)
- [配置代理和 Internet 连接设置](configure-proxy-internet.md)
- [在新载入的适用于终结点的 Defender 设备上运行检测测试](run-detection-test.md)
- [Microsoft Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)
