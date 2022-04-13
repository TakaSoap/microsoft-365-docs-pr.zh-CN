---
title: 将Windows服务器载入到Microsoft Defender for Endpoint服务
description: 载入Windows服务器，以便将传感器数据发送到Microsoft Defender for Endpoint传感器。
keywords: 载入服务器，服务器，2012r2，2016，2019，服务器载入，设备管理，配置Microsoft Defender for Endpoint服务器，载入Microsoft Defender for Endpoint服务器，载入Microsoft Defender for Endpoint服务器
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
ms.openlocfilehash: f06ed934f1ba1a24ba16fe3919d37e10526a3a2f
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823841"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a>将Windows服务器载入到Microsoft Defender for Endpoint服务

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- Windows Server 2012 R2
- Windows Server 2016
- Windows服务器Semi-Annual Enterprise通道
- Windows服务器 2019 及更高版本
- Windows Server 2019 核心版
- Windows Server 2022
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configserver-abovefoldlink)。

Defender for Endpoint 支持范围也包括 Windows 服务器操作系统。 此支持通过Microsoft 365 Defender控制台无缝提供高级攻击检测和调查功能。 支持Windows服务器可以更深入地了解服务器活动、内核和内存攻击检测的覆盖范围，并启用响应操作。

本主题介绍如何载入特定Windows服务器以Microsoft Defender for Endpoint。

有关如何为Windows服务器下载和使用Windows 安全中心基线的指南，请[参阅Windows 安全中心基线](/windows/device-security/windows-security-baselines)。

## <a name="windows-server-onboarding-overview"></a>Windows服务器载入概述

需要完成以下常规步骤才能成功载入服务器。

:::image type="content" source="images/server-onboarding-tools-methods.png" alt-text="Windows服务器和Windows 10设备的载入流图示" lightbox="images/server-onboarding-tools-methods.png":::

**Windows Server 2012 R2 和 Windows Server 2016**

- 下载安装和载入包
- 应用安装包
- 按照相应工具的载入步骤操作

**Windows服务器Semi-Annual Enterprise通道和 Windows Server 2019**

- 下载载入包
- 按照相应工具的载入步骤操作

>[!IMPORTANT]
>若要有资格购买Microsoft Defender for Endpoint服务器 SKU，必须已购买以下任何一项（Windows E5/A5、Microsoft 365 E5/A5 或 Microsoft 365 E5 安全性 订阅许可证）的总和。  有关许可的详细信息，请参阅 [产品条款](https://www.microsoft.com/licensing/terms/productoffering/MicrosoftDefenderforEndpointServer/all)。  



### <a name="new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution"></a>新式统一解决方案中的新Windows Server 2012 R2 和 2016 功能

以前实现的载入Windows Server 2012 R2 和Windows Server 2016需要使用 Microsoft Monitoring Agent (MMA) 。

新的统一解决方案包通过删除依赖项和安装步骤，可以更轻松地载入服务器。 此外，此统一解决方案包还附带了以下主要改进：

- [Microsoft Defender 防病毒](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)Windows Server 2012 R2 的[下一代保护](/microsoft-365/security/defender-endpoint/next-generation-protection)
- [攻击面减少 (ASR) 规则](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules)
- [网络保护](/microsoft-365/security/defender-endpoint/network-protection)
- [受控文件夹访问](/microsoft-365/security/defender-endpoint/controlled-folders)
- [可能不需要的应用程序 (PUA) 阻止](/microsoft-365/security/defender-endpoint/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [改进了检测功能](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)
- 扩展了设备和[文件](/microsoft-365/security/defender-endpoint/respond-file-alerts)上的[响应功能](/microsoft-365/security/defender-endpoint/respond-machine-alerts)
- [在阻止模式下EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode)
- [实时响应](/microsoft-365/security/defender-endpoint/live-response)
- [AIR)  (自动调查和响应 ](/microsoft-365/security/defender-endpoint/automated-investigations)
- [篡改防护](/microsoft-365/security/defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection)

根据要载入的服务器，统一解决方案会安装Microsoft Defender 防病毒和/或EDR传感器。 下表指示默认安装的组件和内置的组件。

|服务器版本|AV|EDR|
|----|----|----|
|Windows Server 2012 R2 SP1|![是。](images/svg/check-yes.svg)|![是。](images/svg/check-yes.svg)|
|Windows Server 2016|内置|![是。](images/svg/check-yes.svg)|
|Windows服务器 2019 或更高版本|内置|内置|

如果以前已使用 MMA 载入服务器，请按照 [服务器迁移](server-migration.md) 中提供的指导迁移到新解决方案。

#### <a name="known-issues-and-limitations-in-the-new-unified-solution-package-for-windows-server-2012-r2-and-2016"></a>Windows Server 2012 R2 和 2016 的新统一解决方案包中的已知问题和限制

以下细节适用于适用于 Windows Server 2012 R2 和 2016 的新统一解决方案包：

- 确保满足在[启用对代理服务器中Microsoft Defender for Endpoint服务 URL 的访问权限中指定的](/microsoft-365/security/defender-endpoint/configure-proxy-internet?enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)连接要求。 它们等效于 Windows Server 2019。 
- 我们正在调查使用静态 TelemetryProxyServer 时Windows Server 2012 R2 连接到云的问题，并且无法从 SYSTEM 帐户上下文访问 CRL) URL (证书吊销列表。 即时缓解措施是使用提供此类连接的替代代理选项，或通过 SYSTEM 帐户上下文上的 WinInet 设置配置同一代理。
- 以前，允许 OMS/Log Analytics 网关在Windows Server 2016及更低版本上使用Microsoft Monitoring Agent (MMA) ，以提供与 Defender 云服务的连接。 新解决方案（如 Windows Server 2019、Windows Server 2022 和 Windows 10 上的Microsoft Defender for Endpoint）不支持此网关。
- 在Windows Server 2016，验证是否已安装Microsoft Defender 防病毒、处于活动状态和最新状态。 可以使用Windows 更新下载并安装最新的平台版本。 或者，从 [Microsoft 更新目录](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4052623) 或 [MMPC](https://go.microsoft.com/fwlink/?linkid=870379&arch=x64) 手动下载更新包。  
- Windows Server 2012 R2 上，没有用于Microsoft Defender 防病毒的用户界面。 此外，Windows Server 2016上的用户界面仅允许基本操作。 若要在本地设备上执行操作，请参阅[使用 PowerShell、WMI 和 MPCmdRun.exe管理Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/manage-mde-post-migration-other-tools)。 因此，专门依赖于用户交互的功能（例如提示用户做出决策或执行特定任务）可能无法按预期工作。 建议禁用或不启用用户界面，也不需要在任何托管服务器上进行用户交互，因为它可能会影响保护功能。
- 并非所有攻击面减少规则都可用于所有操作系统。 请参阅 [攻击面减少 (ASR) 规则](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules)。
- 若要启用 [网络保护](/microsoft-365/security/defender-endpoint/network-protection)，需要其他配置：
  - `Set-MpPreference -EnableNetworkProtection Enabled`
  - `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`
  - `Set-MpPreference -AllowNetworkProtectionDownLevel 1`
  - `Set-MpPreference -AllowDatagramProcessingOnWinServer 1`

  此外，在网络流量量很大的计算机上，强烈建议在广泛启用此功能之前在环境中进行性能测试。 可能需要考虑其他资源消耗。
- 在 Windows Server 2012 R2 上，网络事件可能不会在时间线中填充。 此问题需要在 [2021 年 10 月 12 日每月汇总 (KB5006714) ](https://support.microsoft.com/topic/october-12-2021-kb5006714-monthly-rollup-4dc4a2cd-677c-477b-8079-dcfef2bda09e)中发布的Windows 更新。
- 不支持操作系统升级。 在升级前卸载。然后卸载。
- Windows Server 2012 R2 不支持 *服务器角色* 的自动排除;但是，操作系统文件的内置排除项是。 有关添加排除项的详细信息，请参阅[Enterprise运行当前支持的Windows版本的计算机的病毒扫描建议](https://support.microsoft.com/topic/virus-scanning-recommendations-for-enterprise-computers-that-are-running-currently-supported-versions-of-windows-kb822158-c067a732-f24a-9079-d240-3733e39b40bc)。
- 在已从以前的基于 MMA 的解决方案和EDR传感器升级的计算机上， (预览) 版本早于 10.8047.22439.1056，卸载和还原到基于 MMA 的解决方案可能会导致崩溃。 
- 与 Microsoft Defender for Cloud/Microsoft Defender for servers 的集成以进行警报和自动部署或升级尚不可用。 虽然你可以在这些计算机上手动安装新解决方案，但不会在Microsoft Defender for Cloud中显示警报。

## <a name="integration-with-microsoft-defender-for-cloud"></a>与 Microsoft Defender for Cloud 集成

Microsoft Defender for Endpoint与Microsoft Defender for Cloud无缝集成。 可以自动载入服务器，将 Azure Defender 监视的服务器显示在 Defender for Endpoint 中，并以Microsoft Defender for Cloud客户的身份进行详细调查。

有关详细信息，请参阅[与Microsoft Defender for Cloud的集成](azure-server-integration.md)。

> [!NOTE]
> 对于运行新式统一解决方案的 Windows Server 2012 R2 和 2016，尚不可与用于警报和自动部署或升级的服务器Microsoft Defender for Cloud/Microsoft Defender 集成。 虽然你可以在这些计算机上手动安装新解决方案，但不会在Microsoft Defender for Cloud中显示警报。

> [!NOTE]
> - Microsoft Defender for server 和 Microsoft Defender for Endpoint 之间的集成已扩展，以支持 Windows Server 2022、[Windows Server 2019 和 Windows 虚拟桌面 (WVD) ](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)。
> - 已为Office 365 GCC客户禁用了利用此集成的服务器终结点监视。

## <a name="windows-server-2012-r2-and-windows-server-2016"></a>Windows Server 2012 R2 和 Windows Server 2016

### <a name="prerequisites"></a>先决条件

**Windows Server 2012 R2 的先决条件**

如果已使用最新的 [每月汇总](https://support.microsoft.com/topic/october-12-2021-kb5006714-monthly-rollup-4dc4a2cd-677c-477b-8079-dcfef2bda09e) 包完全更新计算机， **则没有** 其他先决条件。

安装程序包将检查是否已通过更新安装以下组件：

- [更新客户体验和诊断遥测](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)
- [更新Windows中的通用 C 运行时](https://support.microsoft.com/topic/update-for-universal-c-runtime-in-windows-c0514201-7fe6-95a3-b0a5-287930f3560c)

**Windows Server 2016的先决条件** 

必须安装 2021 年 9 月 14 日或更高版本的 SSU (服务堆栈更新) 。  必须安装 2018 年 9 月 20 日或更高版本 (LCU) 的最新累积更新。  建议在服务器上安装最新的可用 SSU 和 LCU。  

必须安装并运行版本 4.18.2109.6 或更高版本的Microsoft Defender 防病毒功能。  可以使用Windows 更新下载并安装最新的平台版本。 或者，从 [Microsoft 更新目录](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4052623) 或 [MMPC](https://go.microsoft.com/fwlink/?linkid=870379&arch=x64) 手动下载更新包。

**使用第三方安全解决方案运行的先决条件**

如果打算使用第三方反恶意软件解决方案，则需要在被动模式下运行Microsoft Defender 防病毒。 在安装和载入过程中，必须记住设置为被动模式。


**Windows Server 2012 R2 和 2016 上Microsoft Defender for Endpoint更新包**
> [!NOTE]
> 如果使用 McAfee Endpoint Security (ENS) 或 VirusScan Enterprise (VSE) 在服务器上安装Microsoft Defender for Endpoint，则可能需要更新 McAfee 平台的版本，以确保不会删除或禁用Microsoft Defender 防病毒。 有关详细信息，包括所需的特定版本号，请参阅 [McAfee 知识中心文章](https://kc.mcafee.com/corporate/index?page=content&id=KB88214)。



若要接收针对EDR传感器组件的常规产品改进和修复，请确保应用或批准 [Windows 更新 KB5005292](https://go.microsoft.com/fwlink/?linkid=2168277)。 此外，若要保持保护组件的更新，请参阅[“管理Microsoft Defender 防病毒更新并应用基线](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。

### <a name="onboarding-steps-summary"></a>载入步骤摘要

- 步骤 1： [下载安装和载入包](#step-1-download-installation-and-onboarding-packages)
- 步骤 2： [应用安装和载入包](#step-2-apply-the-installation-and-onboarding-package)
- 步骤 3： [完成载入步骤](#step-3-complete-the-onboarding-steps) 


### <a name="step-1-download-installation-and-onboarding-packages"></a>步骤 1：下载安装和载入包

需要从门户下载 **安装** 和 **载入** 包。

> [!div class="mx-imgBorder"]
> ![载入仪表板的图像](images/install-agent-onboard.png)


   > [!NOTE]
   > 在 Windows Server 2012R2 上，安装包将安装Microsoft Defender 防病毒并处于活动状态，除非将其设置为被动模式。 Windows Server 2016，Microsoft Defender 防病毒必须安装为功能 (请先查看[切换到 MDE](/microsoft-365/security/defender-endpoint/switch-to-mde-phase-2#re-enable-microsoft-defender-antivirus-on-windows-server-2016)) 并完全更新，然后再继续安装。
   > 
   > 如果运行的是非 Microsoft 反恶意软件解决方案，请确保在安装之前，在“[Defender Process”选项卡上将此 Microsoft Defender Process 列表中的](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)Microsoft Defender 防病毒 (排除项添加到非 Microsoft 解决方案) 。  还建议将非 Microsoft 安全解决方案添加到 Defender 防病毒排除列表。


**安装包** 包含安装Microsoft Defender for Endpoint代理的 MSI 文件。

载 **入包** 包含以下文件：

- `OptionalParamsPolicy` - 包含启用示例集合的设置
- `WindowsDefenderATPOnboardingScript.cmd` - 包含载入脚本

使用以下步骤下载包： 

1. 在Microsoft 365 Defender中，转到 **设置 > 设备管理 >载入**。

2. 选择 **Windows Server 2012 R2 和 2016**。

3. 选择 **“下载安装包** ”并保存.msi文件。 
 
4. 选择 **“下载载入”包** 并保存.zip文件。

5. 使用安装Microsoft Defender 防病毒的任何选项安装安装包。 安装需要管理权限。



### <a name="step-2-apply-the-installation-and-onboarding-package"></a>步骤 2：应用安装和载入包
在此步骤中，你将安装在将设备载入Microsoft Defender for Endpoint云环境之前所需的防护和检测组件，以便为计算机准备载入。 确保满足所有 [先决条件](#prerequisites) 。 

   > [!NOTE]
   > Microsoft Defender 防病毒将安装并处于活动状态，除非将其设置为被动模式。 

#### <a name="options-to-install-the-microsoft-defender-for-endpoint-packages"></a>用于安装Microsoft Defender for Endpoint包的选项

在上一部分中，你下载了安装包。 安装包包含所有Microsoft Defender for Endpoint组件的安装程序。 

可以使用以下任一选项来安装代理：
- [使用命令行进行安装](#install-microsoft-defender-for-endpoint-using-the-command-line)
- [使用脚本进行安装](#install-microsoft-defender-for-endpoint-using-a-script)
- [使用组策略应用安装和载入包](#apply-the-microsoft-defender-for-endpoint-installation-and-onboarding-packages-using-group-policy)

##### <a name="install-microsoft-defender-for-endpoint-using-the-command-line"></a>使用命令行安装 Microsoft Defender For Endpoint
使用上一步骤中的安装包安装Microsoft Defender for Endpoint。 


运行以下命令安装Microsoft Defender for Endpoint：

```console
Msiexec /i md4ws.msi /quiet
```

若要卸载，请确保先使用相应的离载脚本将计算机卸载。 然后，使用控制面板\>程序\>程序和功能执行卸载。

或者，运行以下卸载命令卸载Microsoft Defender for Endpoint：

```console
Msiexec /x md4ws.msi /quiet
```

必须使用用于安装的同一包，上述命令才能成功。

该 `/quiet` 开关将禁止所有通知。

> [!NOTE]
> Microsoft Defender 防病毒不会自动进入被动模式。 如果运行的是非 Microsoft 防病毒/反恶意软件解决方案，可以选择将Microsoft Defender 防病毒设置为在被动模式下运行。 对于命令行安装，可选项`FORCEPASSIVEMODE=1`会立即将Microsoft Defender 防病毒组件设置为被动模式，以避免干扰。 然后，若要确保 Defender 防病毒在载入后保持被动模式，以支持 EDR Block 等功能，请设置“ForceDefenderPassiveMode”注册表项。

支持Windows服务器可以更深入地了解服务器活动、内核和内存攻击检测的覆盖范围，并启用响应操作。

##### <a name="install-microsoft-defender-for-endpoint-using-a-script"></a>使用脚本安装Microsoft Defender for Endpoint

可以使用 [安装程序脚本](server-migration.md#installer-script) 来帮助自动安装、卸载和载入。 有关详细信息，请参阅以下部分中的说明，将脚本与组策略配合使用。

##### <a name="apply-the-microsoft-defender-for-endpoint-installation-and-onboarding-packages-using-group-policy"></a>使用组策略应用Microsoft Defender for Endpoint安装和载入包

1. 创建组策略： <br> 打开 [组策略管理控制台](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) ，右键单击 **要配置的组策略对象**，然后单击 **“新建**”。 在显示的对话框中输入新 GPO 的名称，然后单击 **“确定**”。

2. 打开 [GPMC)  (组策略管理控制台](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)，右键单击要配置的 组策略 对象 (GPO) ，然后单击 **“编辑**”。

3. 在 **组策略管理编辑器** 中，转到 **“计算机配置**”，然后转到 **“首选项”**，然后 **转到“控制面板”设置**。

4. 右键单击 **“计划”任务**，指向 **“新建**”，然后单击“**即时任务” (至少Windows 7)**。

5. 在打开 **的任务** 窗口中，转到“ **常规** ”选项卡。在 **“安全选项** ”下，单击 **“更改用户或组** ”并键入“系统”，然后单击 **“检查名称** ”，然后 **“确定**”。 NT AUTHORITY\SYSTEM 显示为任务将作为运行方式运行的用户帐户。

6. 选择 **“运行是否登录用户** ”，然后选中“ **使用最高权限运行** ”复选框。

7. 在“名称”字段中，键入计划任务 (的相应名称，例如 Defender for Endpoint Deployment) 。

8. 转到 **“操作”** 选项卡，然后选择 **“新建...** 确保在 **“操作**”字段中选择了 **“启动程序**”。 [安装程序脚本](server-migration.md#installer-script)处理安装，安装完成后立即执行载入步骤。 选择 *C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe* 然后提供参数：

    ```console
     -ExecutionPolicy RemoteSigned \\servername-or-dfs-space\share-name\install.ps1 -OnboardingScript \\servername-or-dfs-space\share-name\windowsdefenderatponboardingscript.cmd
    ```  

     >[!NOTE]
    >如果需要排查代理安装问题，请将“-etl -log”添加到install.ps1脚本参数。
    >
    >建议的执行策略设置为 `Allsigned`。 如果脚本在终结点上以 SYSTEM 身份运行，则需要将脚本的签名证书导入本地计算机受信任发布服务器存储。

    使用共享install.ps1文件的文件服务器的完全限定域名 (FQDN) ，将 servername-or-dfs-space\share-name 替换\\*为* UNC 路径。 安装程序包md4ws.msi必须放置在同一目录中。  另请确保 UNC 路径的权限允许对安装平台的计算机帐户进行读取访问。

   

    对于希望Microsoft Defender 防病毒与非 Microsoft 反恶意软件解决方案共存的情况，请添加$Passive参数以在安装期间设置被动模式。

9. 选择 **“确定”** 并关闭任何打开的 GPMC 窗口。

10. 若要将 GPO 链接到组织单位 (OU) ，请右键单击并选择 **“链接现有 GPO**”。 在显示的对话框中，选择要链接的组策略对象。 单击“确定”。

有关其他配置设置，请参阅[配置示例集合设置](configure-endpoints-gp.md#configure-sample-collection-settings)[和其他建议的配置设置](configure-endpoints-gp.md#other-recommended-configuration-settings)。

### <a name="step-3-complete-the-onboarding-steps"></a>步骤 3：完成载入步骤

仅当使用第三方反恶意软件解决方案时，以下步骤才适用。 需要应用以下Microsoft Defender 防病毒被动模式设置。 验证是否已正确配置：

1. 设置以下注册表项：
    - 路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
    - 名称：`ForceDefenderPassiveMode`
    - 类型： `REG_DWORD`
    - 值：`1`

       :::image type="content" source="images/atp-verify-passive-mode.png" alt-text="被动模式验证结果" lightbox="images/atp-verify-passive-mode.png":::
> [!IMPORTANT]
>
> - 使用Microsoft Defender for Cloud监视服务器时，会在美国为美国用户自动创建 Defender for Endpoint 租户 (，在欧盟为欧洲用户创建，在英国为英国用户) 创建 Defender for Endpoint 租户。
Defender for Endpoint 收集的数据存储在预配过程中标识的租户的地理位置中。
> - 如果在使用 Microsoft Defender for Cloud 之前使用 Defender for Endpoint，则即使稍后与Microsoft Defender for Cloud集成，数据也会存储在创建租户时指定的位置。
> - 配置后，无法更改数据的存储位置。 如果需要将数据移动到另一个位置，则需要联系Microsoft 支持部门重置租户。
> - Windows Server 2019 和 Windows Server 2022 到 Microsoft Endpoint Manager 的载入包当前提供脚本。 有关如何在Configuration Manager中部署脚本的详细信息，请参阅[Configuration Manager中的包和程序](/configmgr/apps/deploy-use/packages-and-programs)。
> - 本地脚本适用于概念证明，但不应用于生产部署。 对于生产部署，建议使用组策略或Microsoft Endpoint Configuration Manager。



## <a name="windows-server-semi-annual-enterprise-channel-and-windows-server-2019-and-windows-server-2022"></a>Windows服务器Semi-Annual Enterprise通道和 Windows Server 2019 和 Windows Server 2022

Windows Server 2019 和 Windows Server 2022 到 Microsoft Endpoint Manager 的载入包当前提供脚本。 有关如何在Configuration Manager中部署脚本的详细信息，请参阅[Configuration Manager中的包和程序](/configmgr/apps/deploy-use/packages-and-programs)。

### <a name="download-package"></a>下载包

1. 在Microsoft 365 Defender中，转到 **设置 > 设备管理 >载入**。

2. 选择 **Windows服务器 1803 和 2019**。

3. 选择 **“下载”包**。 将其另存为WindowsDefenderATPOnboardingPackage.zip。

4. 按照“ [完成载入步骤](#step-3-complete-the-onboarding-steps) ”部分中提供的步骤操作。


## <a name="verify-the-onboarding-and-installation"></a>验证载入和安装

验证Microsoft Defender 防病毒和Microsoft Defender for Endpoint是否正在运行。

## <a name="run-a-detection-test-to-verify-onboarding"></a>运行检测测试以验证载入

载入设备后，可以选择运行检测测试来验证设备是否已正确加入服务。 有关详细信息，请参阅[在新加入的Microsoft Defender for Endpoint设备上运行检测测试](run-detection-test.md)。

> [!NOTE]
> 运行Microsoft Defender 防病毒不是必需的，但建议运行。 如果另一个防病毒供应商产品是主要的终结点保护解决方案，则可以在被动模式下运行 Defender 防病毒。 只有在验证Microsoft Defender for Endpoint传感器 (SENSE) 是否正在运行后，才能确认被动模式是否处于打开状态。

1. 运行以下命令以验证是否已安装Microsoft Defender 防病毒：

    >[!NOTE]
    >仅当将Microsoft Defender 防病毒用作活动反恶意软件解决方案时，才需要执行此审核步骤。

    `sc.exe query Windefend`


    如果结果为“指定的服务不存在作为已安装的服务”，则需要安装Microsoft Defender 防病毒。 


    有关如何使用组策略在Windows服务器上配置和管理Microsoft Defender 防病毒的信息，请参阅[使用组策略设置来配置和管理Microsoft Defender 防病毒](use-group-policy-microsoft-defender-antivirus.md)。

2. 运行以下命令以验证Microsoft Defender for Endpoint是否正在运行：

    `sc.exe query sense`

    结果应显示它正在运行。 如果在载入方面遇到问题，请参阅 [载入疑难解答](troubleshoot-onboarding.md)。

## <a name="run-a-detection-test"></a>运行检测测试

按照 [在新载入的设备上运行检测测试](run-detection-test.md) 中的步骤，验证服务器是否向 Defender for Endpoint 服务报告。

## <a name="next-steps"></a>后续步骤

将设备成功载入服务后，需要配置Microsoft Defender for Endpoint的各个组件。 按照 [采用顺序](prepare-deployment.md#adoption-order) 指导启用各种组件。

## <a name="offboard-windows-servers"></a>载入Windows服务器

可以使用适用于Windows 10客户端设备的同一方法Windows Server 2012 R2、Windows Server 2016、Windows Server (SAC) 、Windows Server 2019 和 Windows Server 2019 Core 版本。

- [使用 组策略 载入设备](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [使用Configuration Manager载入设备](configure-endpoints-sccm.md#offboard-devices-using-configuration-manager)
- [使用移动设备管理工具载入和监视设备](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)
- [使用本地脚本载入设备](configure-endpoints-script.md#offboard-devices-using-a-local-script)

卸载后，可以在 Windows Server 2012 R2 和 Windows Server 2016 上继续卸载统一解决方案包。

对于其他Windows服务器版本，可以使用两个选项从服务中Windows服务器：

- 卸载 MMA 代理
- 删除 Defender for Endpoint 工作区配置

> [!NOTE]
> 如果为需要 MMA 的 Windows Server 2016 和 Windows Server 2012 R2 运行以前的Microsoft Defender for Endpoint，则其他Windows服务器版本的这些离载说明也适用。 Microsoft Defender for Endpoint[中的服务器迁移方案中](/microsoft-365/security/defender-endpoint/server-migration)介绍了迁移到新的统一解决方案的说明。

## <a name="related-topics"></a>相关主题

- [载入以前版本的 Windows](onboard-downlevel.md)
- [载入 Windows 10 设备](configure-endpoints.md)
- [载入非 Windows 设备](configure-endpoints-non-windows.md)
- [配置代理和 Internet 连接设置](configure-proxy-internet.md)
- [在新加入的 Defender for Endpoint 设备上运行检测测试](run-detection-test.md)
- [排查Microsoft Defender for Endpoint载入问题](troubleshoot-onboarding.md)
