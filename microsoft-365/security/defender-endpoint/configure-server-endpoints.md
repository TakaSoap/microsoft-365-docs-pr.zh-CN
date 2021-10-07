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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 13356a3276fd6a95f18591e92f459bbb2d28f9f7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213141"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a>将Windows载入 Microsoft Defender for Endpoint 服务

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- Windows Server 2008 R2 SP1
- Windows Server 2012 R2
- Windows Server 2016
- Windows服务器 (SAC) 版本 1803 及更高版本
- WindowsServer 2019 及更高版本
- WindowsServer 2019 核心版本

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configserver-abovefoldlink)。

Defender for Endpoint 扩展支持，还包括 Windows Server 操作系统。 此支持通过安全中心控制台无缝提供高级攻击检测和Microsoft 365 Defender功能。

有关许可和基础结构需要满足的实际指导，请参阅使用 Defender for Endpoint [Windows服务器](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)。

有关如何下载和使用 Windows 安全中心 基线的Windows，请参阅 Windows 安全中心[Baselines](/windows/device-security/windows-security-baselines)。

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a>WindowsServer 2008 R2 SP1、Windows Server 2012 R2 和 Windows Server 2016

可以使用以下任Windows将 Windows Server 2008 R2 SP1、Windows Server 2012 R2 和 Windows Server 2016 载入 Defender for Endpoint：

- **选项 1：**[通过安装和配置 MMA Microsoft Monitoring Agent (](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)载入) 
- **选项 2：**[通过 Azure 安全中心载入](#option-2-onboard-windows-servers-through-azure-security-center)
- **选项 3：**[在 Microsoft Endpoint Manager版本 2002 及更高版本中载入](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)

使用提供的任一选项完成载入步骤后，你需要配置和更新System Center Endpoint Protection[客户端](#configure-and-update-system-center-endpoint-protection-clients)。

> [!NOTE]
> 每个节点都需要 Defender for Endpoint 独立服务器许可证，才能通过 Microsoft Monitoring Agent (选项 1) 或 Microsoft Endpoint Manager (选项 3) 载入 Windows 服务器。 或者，每个节点都需要 Azure Defender for Servers 许可证，才能通过 Azure 安全中心 (选项 2) 载入 Windows 服务器。 有关详细信息，请参阅 Azure [Defender 中支持的功能](/azure/security-center/security-center-services)。 与用户许可证不同，这些许可证不分配给任何用户或对象。 它们必须符合要求，才能在租户中。

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a>选项 1：通过安装和配置 MMA Microsoft Monitoring Agent (载入) 

你需要为服务器安装和配置 MMA Windows向 Defender for Endpoint 报告传感器数据。 有关详细信息，请参阅使用 [Azure Log Analytics 代理收集日志数据](/azure/azure-monitor/platform/log-analytics-agent)。

如果你已在使用 System Center Operations Manager (SCOM) 或 Azure Monitor (以前称为 Operations Management Suite (OMS) ) ，请附加 Microsoft Monitoring Agent (MMA) 以通过多托管支持向 Defender for Endpoint 工作区报告。

通常，您需要执行以下步骤：

  1. 满足开始之前部分 **中列出的载入** 要求。
  2. 从服务器启用Microsoft 365 Defender。
  3. 安装和配置服务器的 MMA，以将传感器数据报告给 Defender for Endpoint。
  4. 配置和更新System Center Endpoint Protection客户端。


#### <a name="before-you-begin"></a>准备工作

执行以下步骤以满足载入要求：

对于 Windows Server 2008 R2 SP1 或 Windows Server 2012 R2，请确保安装以下修补程序：

- [客户体验和诊断遥测更新](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

对于 Windows Server 2008 R2 SP1，请确保满足以下要求：

- 安装 [2 月每月更新汇总](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
- 安装 [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > 如果使用 SCCM 管理 Windows Server 2008 R2 SP1，SCCM 客户端代理将安装 .Net Framework 4.5.2。 因此，无需安装 .NET framework 4.5 (更高版本) 。

For Windows Server 2008 R2 SP1 and Windows Server 2012 R2： [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).

> [!NOTE]
> 只有当您的组织使用 SCEP System Center Endpoint Protection (SCEP) 并且要载入 Windows Server 2008 R2 SP1 和 Windows Server 2012 R2 时，才需要此步骤。

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>安装和配置 Microsoft Monitoring Agent (MMA) 以将传感器数据报告给 Microsoft Defender for Endpoint

1. 下载代理安装文件[：Windows 64 位代理](https://go.microsoft.com/fwlink/?LinkId=828603)。

2. 使用在上一过程中获取的 Workspace ID 和 Workspace 密钥，选择以下任一安装方法将代理安装在Windows服务器上：
    - [使用安装程序 手动安装代理](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。
    在"**代理设置选项**"页上 **，连接代理设置为 Azure Log Analytics (OMS) 。**
    - [使用命令行 安装代理](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。
    - [使用脚本 配置代理](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。

> [!NOTE]
> 如果你是美国政府客户，[](gov.md)在"Azure 云"下，如果使用安装向导，或者使用命令行或脚本，则需要选择"Azure 美国政府"，将"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE"参数设置为 1。

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a>根据需要Windows服务器代理和 Internet 连接设置

如果你的服务器需要使用代理与 Defender for Endpoint 通信，请使用以下方法之一将 MMA 配置为使用代理服务器：

- [配置 MMA 以使用代理服务器](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)
- [配置Windows以将代理服务器用于所有连接](configure-proxy-internet.md)

如果代理或防火墙已在使用中，请确保服务器可以直接访问所有 Microsoft Defender for Endpoint 服务 URL，且无需 SSL 拦截。 有关详细信息，请参阅启用对 [Defender for Endpoint 服务 URL 的访问](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。 使用 SSL 拦截将阻止系统与 Defender for Endpoint 服务通信。

完成后，应在一小时内Windows门户中的已载入服务器。

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a>选项 2：Windows Azure 安全中心载入服务器

在"Microsoft 365 Defender导航窗格中，选择 **"设置** \> **终结点** \> **设备管理** \> **载入"。**

1. 选择 **Windows Server 2008 R2 SP1、2012 R2 和 2016** 作为操作系统。

2. 单击 **Azure 安全中心中的载入服务器**。

3. 按照使用 Azure Defender 的 [Microsoft Defender for Endpoint](/azure/security-center/security-center-wdatp) 中的载入说明操作，如果你使用的是 Azure ARC，请按照启用适用于终结点集成的 Microsoft Defender [中的载入说明操作](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)。

完成载入步骤后，你需要配置和更新System Center Endpoint Protection[客户端](#configure-and-update-system-center-endpoint-protection-clients)。

> [!NOTE]
>
> - 若要通过 Azure Defender for Servers 载入以如预期方式工作，服务器必须在 Microsoft Monitoring Agent (MMA) 配置相应的工作区和密钥。
> - 配置后，相应的云管理包将部署在计算机中，并且传感器 (MsSenseS.exe) 将部署和启动。
> - 如果服务器配置为使用 OMS 网关服务器作为代理，则也要求这样做。

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a>选项 3：Windows 2002 Microsoft Endpoint Manager更高版本载入服务器

可以使用 2002 Windows Server 2012更高版本Windows Server 2016 R2 和 Microsoft Endpoint Manager R2 和更高版本。 有关详细信息，请参阅[Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)。

完成载入步骤后，你需要配置和更新System Center Endpoint Protection[客户端](#configure-and-update-system-center-endpoint-protection-clients)。

## <a name="windows-server-sac-version-1803-windows-server-2019-windows-server-2022-and-windows-server-2019-core-edition"></a>WindowsServer (SAC) 1803、Windows Server 2019、Windows Server 2022 和 Windows Server 2019 Core 版本

可以使用以下部署方法载入 Windows Server (SAC) 版本 1803、Windows Server 2019、Windows Server 2022 或 Windows Server 2019 Core 版本：

- [本地脚本](configure-endpoints-script.md)
- [组策略](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [System Center Configuration Manager 2012 / 2012 R2 1511 / 1602](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [用于非永久性设备的 VDI 载入脚本](configure-endpoints-vdi.md)

> [!NOTE]
>
> - Windows Server 2019 和 Windows Server 2022 的载入Microsoft Endpoint Manager目前附带了脚本。 若要详细了解如何在 Configuration Manager 中部署脚本，请参阅 Configuration [Manager 中的程序包和程序](/configmgr/apps/deploy-use/packages-and-programs)。
> - 本地脚本适用于概念证明，但不应用于生产部署。 对于生产部署，我们建议使用组策略或Microsoft Endpoint Configuration Manager。

对 Windows Server 的支持可更深入地了解服务器活动、内核和内存攻击检测的范围，并启用响应操作。

1. 使用适用于所有设备Windows相同工具和方法在 Windows 10 服务器上配置 Defender 终结点载入设置。 有关详细信息，请参阅载入[Windows 10设备](configure-endpoints.md)。

2. 如果你运行的是第三方反恶意软件解决方案，则需要应用以下 Microsoft Defender AV 被动模式设置。 验证是否正确配置了它：

    1. 设置以下注册表项：
       - 路径： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
       - 名称：ForceDefenderPassiveMode
       - 类型：REG_DWORD
       - Value: 1

    1. 运行以下 PowerShell 命令以验证被动模式是否配置：

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. 确认找到包含被动模式事件的最近事件：

       ![被动模式验证结果的图像。](images/atp-verify-passive-mode.png)

3. 运行以下命令检查是否安装了 Microsoft Defender AV：

   ```dos
   sc.exe query Windefend
   ```

    如果结果是"指定服务作为已安装服务不存在"，则需要安装 Microsoft Defender AV。 有关详细信息，请参阅 Microsoft Defender 防病毒[中的Windows 10。](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

    有关如何使用组策略在 Windows 服务器上配置和管理 Microsoft Defender 防病毒 的信息，[请参阅使用组](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)策略设置配置和管理Microsoft Defender 防病毒。

## <a name="integration-with-azure-defender"></a>与 Azure Defender 集成

Defender for Endpoint 可以与 Azure Defender 集成，以提供全面的Windows服务器保护解决方案。 通过此集成，Azure Defender 可以使用 Defender for Endpoint 功能为 Windows 服务器提供改进的威胁检测。

此集成中包含以下功能：

- 自动载入 - 在载入到 Azure Defender 的 Windows 自动启用 Defender for Endpoint 传感器。 有关 Azure Defender 载入详细信息，请参阅使用集成的 [Microsoft Defender for Endpoint 许可证](/azure/security-center/security-center-wdatp)。

    > [!NOTE]
    > Azure Defender for Servers 和 Microsoft Defender for Endpoint 之间的集成已扩展为支持 Windows Server 2022、Windows [Server 2019 和 Windows Virtual Desktop (WVD) 。 ](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)

- Windows受 Azure Defender 监视的服务器也将在 Defender for Endpoint 中可用 - Azure Defender 无缝连接到 Defender for Endpoint 租户，跨客户端和服务器提供单个视图。 此外，适用于终结点的 Defender 警报将在 Azure Defender 控制台中提供。

- 服务器调查 - Azure Defender 客户可以访问Microsoft 365 Defender执行详细调查，以发现潜在泄露的范围。

> [!IMPORTANT]
>
> - 当你使用 Azure Defender 监视服务器时，会自动在美国为美国用户 (，在欧盟为欧洲和英国用户创建 Defender) 。
Defender for Endpoint 收集的数据存储在预配期间标识的租户地理位置中。
> - 如果在使用 Azure Defender 之前使用 Defender for Endpoint，数据将存储在创建租户时指定的位置，即使以后与 Azure Defender 集成。
> - 配置后，你无法更改数据存储的位置。 如果需要将数据移动到其他位置，需要联系 Microsoft 支持部门来重置租户。
>
已针对客户禁用利用此集成的服务器终结点Office 365 GCC监视。

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>配置和更新System Center Endpoint Protection客户端

Defender for Endpoint 与 System Center Endpoint Protection 集成。 集成提供了恶意软件检测的可见性，并禁止潜在恶意文件或可疑恶意软件，从而停止攻击在组织中传播。

若要启用此集成，需要执行以下步骤：

- 为客户端[安装 2017 年 1](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)月Endpoint Protection更新。

- [将 SCEP 客户端云保护服务成员身份配置为](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus)**高级** 设置。

## <a name="run-a-detection-test-to-verify-onboarding"></a>运行检测测试以验证载入

载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。 有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint](run-detection-test.md)设备运行检测测试。

## <a name="offboard-windows-servers"></a>载出Windows服务器

可以使用适用于 Windows 10 客户端设备的相同方法从 Windows Server (SAC) 、Windows Server 2019、Windows Server 2022 和 Windows Server 2019 Core 版本上离开。

- [使用组策略的载出](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [使用 Configuration Manager 的载出设备](configure-endpoints-sccm.md#offboard-devices-using-configuration-manager)
- [使用移动设备管理工具离开并监视设备](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)
- [使用本地脚本的载出设备](configure-endpoints-script.md#offboard-devices-using-a-local-script)

对于其他Windows版本，有两个选项Windows从服务中离开服务器：

- 卸载 MMA 代理
- 删除 Defender for Endpoint 工作区配置

> [!NOTE]
> 载出会导致 Windows 服务器停止向门户发送传感器数据，但来自 Windows 服务器的数据（包括引用已具有的任何警报）最多保留 6 个月。

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a>通过Windows MMA 代理卸载服务器

若要卸载Windows，可以从服务器卸载 MMA Windows或将其从报告分离到 Defender for Endpoint 工作区。 在离开代理后，Windows服务器将不再将传感器数据发送到 Defender for Endpoint。
有关详细信息，请参阅禁用 [代理](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)。

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>删除 Defender for Endpoint 工作区配置

若要将Windows服务器，可以使用下列方法之一：

- 从 MMA 代理中删除 Defender for Endpoint 工作区配置
- 运行 PowerShell 命令以删除配置

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>从 MMA 代理中删除 Defender for Endpoint 工作区配置

1. 在 **"Microsoft Monitoring Agent属性**"中，选择 **"Azure Log Analytics (OMS) "** 选项卡。

2. 选择"适用于终结点的 Defender"工作区，然后单击"删除 **"。**

    ![属性Microsoft Monitoring Agent的图像。](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>运行 PowerShell 命令以删除配置

1. 获取工作区 ID：

   1. 在"Microsoft 365 Defender导航窗格中，选择 **"设置** \> **终结点** \> **设备管理** \> **载入"。**

   1. 选择 **Windows Server 2008 R2 SP1、2012 R2 和 2016** 作为操作系统并获取工作区 ID：

      ![服务器Windows映像。](images/atp-server-offboarding-workspaceid.png)

2. 打开提升的 PowerShell 并运行以下命令。 使用你获取的工作区 ID 并替换 `WorkspaceID` ：

    ```powershell
    $ErrorActionPreference = "SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()
    ```

## <a name="onboarding-servers-with-no-management-solution"></a>载入服务器，无管理解决方案

### <a name="using-group-policy"></a>使用组策略

**步骤 1：创建复制到服务器所需的文件。**

1. 导航到 c：\windows\sysvol\domain\scripts (其中一个域控制器上需要更改控件。) 
1. 创建一个名为 MMA 的文件夹。
1. 下载以下内容，并放置到 MMA 文件夹中：

    **(Windows Server 2008 R2 和 Windows Server 2012 R2)**

    [For Windows 2008 R2 x64](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [For Windows 2012 R2 x64](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > 本文假定你正在使用基于 x64 的服务器 (MMA 代理.exe x64 [新 SHA-2](https://go.microsoft.com/fwlink/?LinkId=828603) 兼容版本) 

**步骤 2：使用记事本工具创建 (DeployMMA.cmd)** 将以下行添加到 cmd 文件。 请注意，你将需要工作区 ID 和密钥。

```dos
@echo off
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" (
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a>组策略配置

创建专用于载入设备的新组策略，例如"适用于终结点载入的 Microsoft Defender"。

- 创建名为"c：\windows\MMA"的组策略文件夹

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="文件夹。":::

    **这将在应用 GPO 的每台服务器上添加新文件夹（称为 MMA）并存储在 c：\windows 中。这将包含 MMA 的安装文件、必备组件和安装脚本。**

- 为存储在 Net 登录中的每个文件创建组策略文件首选项。

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="组策略图像 1。":::

它将文件从 DOMAIN\NETLOGON\MMA\filename 复制到 C：\windows\MMA\filename ，因此安装文件是服务器 **的本地文件**：

:::image type="content" source="images/deploymma.png" alt-text="部署 mma cmd。":::

对于两个 KB (一个针对 Windows Server 2008R2/Windows 7，另一个针对 Windows Server 2012 R2) 重复此过程，但在"COMMON"选项卡上创建项目级别目标，因此文件仅复制到作用域中的相应平台/操作系统版本：

:::image type="content" source="images/targeteditor.png" alt-text="目标编辑器。":::

- 对于 Windows Server 2008 R2，你需要 (并且它将仅向下复制) Windows6.1-BJ3080149-x64.msu
- For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu

完成此操作后，你需要创建启动脚本策略：

:::image type="content" source="images/startupprops.png" alt-text="启动属性。":::

要在此处运行的文件的名称为 c：\windows\MMA\DeployMMA.cmd。
在启动过程中重新启动服务器后，它将安装客户体验更新和诊断遥测 KB，然后安装 MMA 代理，同时设置工作区 ID 和密钥，并且将载入服务器。

如果不想重新启动所有 **服务器** ，您也可以使用即时任务运行 deployMMA.cmd。
这分两个阶段完成。 首先在 GPO **中创建文件和** 文件夹。 为系统提供时间来确保已应用 GPO，并且所有服务器都有安装文件。 然后，添加即时任务。 这将获得相同的结果，而无需重新启动。

由于脚本具有退出方法，并且如果安装了 MMA，将不会重新运行，因此，您还可以使用每日计划任务来实现相同的结果。 与 Configuration Manager 合规性策略类似，它每天都会检查以确保 MMA 存在。

:::image type="content" source="images/schtask.png" alt-text="计划任务。":::

:::image type="content" source="images/newtaskprops.png" alt-text="新任务属性。":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="部署 mma 下载属性。":::

:::image type="content" source="images/tasksch.png" alt-text="任务计划程序。":::

如 Server 的载入文档中提及，特别是围绕 Server 2008 R2，请参阅以下内容：

对于 Windows Server 2008 R2 PS1，请确保满足以下要求：

- 安装 [2018 年 2 月每月更新汇总](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

- 安装 [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

在载入 Windows Server 2008 R2 之前，请检查这些 KB。如果没有配置管理器管理服务器，此过程允许你载入所有服务器。

## <a name="related-topics"></a>相关主题

- [载入 Windows 10 设备](configure-endpoints.md)
- [载入非 Windows 设备](configure-endpoints-non-windows.md)
- [配置代理和 Internet 连接设置](configure-proxy-internet.md)
- [在新载入的适用于终结点的 Defender 设备上运行检测测试](run-detection-test.md)
- [Microsoft Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)
