---
title: 在 Microsoft Defender for Endpoint Windows上载入早期版本的客户端
description: 载入受支持的早期版本的 Windows 设备，以便它们可以将传感器数据发送到 Microsoft Defender for Endpoint 传感器
keywords: onboard， windows， 7， 81， oms， sp1， enterprise， pro， down level
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 39e01e614ebe2467899f179bc1ef3905ac0ca388
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61164906"
---
# <a name="onboard-previous-versions-of-windows"></a>载入以前版本的 Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**平台**

- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 专业版
- Windows 8.1 企业版
- Windows Server 2008 R2 SP1

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevel-abovefoldlink)。

Defender for Endpoint 扩展支持以包括低级别操作系统，在受支持的版本上提供高级攻击检测和Windows功能。

若要将低级别Windows客户端终结点载入到 Defender for Endpoint，你将需要：

- [配置和更新System Center Endpoint Protection客户端](#configure-and-update-system-center-endpoint-protection-clients)
- [安装和配置Microsoft Monitoring Agent (MMA) 报告传感器数据](#install-and-configure-microsoft-monitoring-agent-mma)

对于 Windows Server 2008 R2 SP1，可以选择通过[Microsoft Defender for Cloud 载入](#onboard-windows-servers-through-microsoft-defender-for-cloud)。

> [!NOTE]
> 每个节点都需要 Defender for Endpoint 独立服务器许可证，才能通过选项 1 Windows载入 Microsoft Monitoring Agent (服务器) 。 或者，每个节点都需要 Microsoft Defender 服务器许可证，才能通过 Microsoft Defender for Cloud (选项 2) 载入 Windows 服务器，请参阅[Microsoft Defender 云](/azure/security-center/security-center-services)中可用的支持功能。

> [!TIP]
> 载入设备后，你可以选择运行检测测试，以验证它是否正确载入到服务。 有关详细信息，请参阅对新载入的 Defender 终结点终结点运行检测 [测试](run-detection-test.md)。

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>配置和更新System Center Endpoint Protection客户端

> [!IMPORTANT]
> 只有当组织使用 SCEP System Center Endpoint Protection (时，才需要) 。

Defender for Endpoint 与 System Center Endpoint Protection集成，通过禁止潜在恶意文件或可疑恶意软件，提供恶意软件检测可见性并阻止攻击在组织中传播。

若要启用此集成，需要执行以下步骤：

- 为客户端[安装 2017](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)年 1 月Endpoint Protection更新
- 将 SCEP 客户端云保护服务成员身份配置为 **高级** 设置
- 配置网络以允许连接到Microsoft Defender 防病毒云。 有关详细信息，请参阅配置[和验证Microsoft Defender 防病毒网络连接](/microsoft-365/security/defender-endpoint/configure-network-connections-microsoft-defender-antivirus)

## <a name="install-and-configure-microsoft-monitoring-agent-mma"></a>安装和配置Microsoft Monitoring Agent (MMA) 

### <a name="before-you-begin"></a>准备工作

查看以下详细信息以验证最低系统要求：

- 安装 [2018 年 2 月每月更新汇总](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

  > [!NOTE]
  > 仅适用于 Windows Server 2008 R2、Windows 7 SP1 Enterprise 和 Windows 7 SP1 Pro。

- 安装 [客户体验和诊断遥测更新](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- 安装 [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > 仅适用于 Windows Server 2008 R2、Windows 7 SP1 Enterprise 和 Windows 7 SP1 Pro。
    >
    > 不要安装 .NET Framework 4.0.x，因为它将否定上述安装。
    >
    > 安装 .NET 4.5 可能需要在安装后重新启动计算机。

- 满足 Azure Log Analytics 代理的最低系统要求。 有关详细信息，请参阅使用[Log Analytics](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)从环境中的计算机收集数据

### <a name="installation-steps"></a>安装步骤

1. 下载代理安装文件[：Windows 64](https://go.microsoft.com/fwlink/?LinkId=828603)位代理Windows [32 位代理](https://go.microsoft.com/fwlink/?LinkId=828604)。

2. 获取工作区 ID：
   - 在 Defender for Endpoint 导航窗格中，选择"设置 >**设备>载入"**
   - 选择操作系统
   - 复制工作区 ID 和工作区密钥

3. 使用 Workspace ID 和 Workspace 密钥选择以下任一安装方法以安装代理：
    - [使用安装程序 手动安装代理](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。

      在"**代理设置选项**"页上 **，连接代理设置为 Azure Log Analytics (OMS)**

    - [使用命令行 安装代理](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。
    - [使用脚本 配置代理](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。

   > [!NOTE]
   > 如果你是美国政府客户，[](gov.md)在"Azure 云"下，如果使用安装向导，或者使用命令行或脚本，则需要选择"Azure 美国政府"，将"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE"参数设置为 1。

4. 如果使用代理连接到 Internet，请参阅配置代理和 Internet 连接设置部分。

完成后，你应该在一小时内在门户中看到已载入的终结点。

## <a name="configure-proxy-and-internet-connectivity-settings"></a>配置代理和 Internet 连接设置
如果你的服务器需要使用代理与 Defender for Endpoint 通信，请使用以下方法之一将 MMA 配置为使用代理服务器：

- [配置 MMA 以使用代理服务器](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [配置Windows以将代理服务器用于所有连接](configure-proxy-internet.md)

如果代理或防火墙已在使用中，请确保服务器可以直接访问所有 Microsoft Defender for Endpoint 服务 URL，且无需 SSL 拦截。 有关详细信息，请参阅启用对 [Defender for Endpoint 服务 URL 的访问](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。 使用 SSL 拦截将阻止系统与 Defender for Endpoint 服务通信。

完成后，应在一小时内Windows门户中的已载入服务器。

## <a name="onboard-windows-servers-through-microsoft-defender-for-cloud"></a>通过Windows云的 Microsoft Defender 载入服务器

1. 在"Microsoft Defender 安全中心"导航窗格中，选择 **"设置**  >  **设备管理**  >  **载入"。**

2. 选择 **Windows Server 2008 R2 SP1** 作为操作系统。

3. 单击 **载入 Microsoft Defender 云中的服务器**。

4. 按照 Microsoft Defender [for Endpoint with Microsoft Defender for Cloud](/azure/security-center/security-center-wdatp) 中的载入说明操作，如果你使用的是 Azure ARC，请按照启用适用于终结点集成的 Microsoft Defender [中的载入说明操作](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)。

完成载入步骤后，你需要配置和更新System Center Endpoint Protection[客户端](#configure-and-update-system-center-endpoint-protection-clients)。

> [!NOTE]
>
> - 若要通过 Microsoft Defender 载入服务器以如预期方式工作，服务器必须在 MMA Microsoft Monitoring Agent (配置适当的工作区) 密钥。
> - 配置后，相应的云管理包将部署在计算机中，并且传感器过程 (MsSenseS.exe) 将部署并启动。
> - 如果服务器配置为使用 OMS 网关服务器作为代理，则也要求这样做。



## <a name="verify-onboarding"></a>验证载入

验证 Microsoft Defender AV 和 Microsoft Defender for Endpoint 是否正在运行。 

> [!NOTE]
> 虽然不需要运行 Microsoft Defender AV，但建议使用它。 如果另一个防病毒供应商产品是主要终结点保护解决方案，可以在被动模式下运行 Defender 防病毒。 在验证 Microsoft Defender for Endpoint 传感器是否处于运行状态后，你 (被动) 处于打开状态。 

1. 运行以下命令以验证是否安装了 Microsoft Defender AV：

   ```sc.exe query Windefend```

    如果结果是"指定服务作为已安装服务不存在"，则需要安装 Microsoft Defender AV。 有关详细信息，请参阅 Microsoft Defender 防病毒[中的Windows 10。](microsoft-defender-antivirus-windows.md)

    有关如何使用组策略配置和管理 Microsoft Defender 防病毒 服务器Windows的信息，[请参阅使用组](use-group-policy-microsoft-defender-antivirus.md)策略设置配置和管理Microsoft Defender 防病毒。


2. 运行以下命令以验证 Microsoft Defender for Endpoint 是否正在运行：

    ```sc.exe query sense```
    
    结果应显示它正在运行。 如果你遇到载入问题，请参阅 [载入疑难解答](troubleshoot-onboarding.md)。

## <a name="run-a-detection-test"></a>运行检测测试
按照对新载入 [的设备运行检测](run-detection-test.md) 测试中的步骤验证服务器是否向终结点服务的 Defender 报告。





## <a name="onboarding-endpoints-with-no-management-solution"></a>载入终结点，无管理解决方案 

### <a name="using-group-policy"></a>使用组策略

**步骤 1：为终结点下载相应的 udpate。**

1. 导航到 c：\windows\sysvol\domain\scripts (其中一个域控制器上需要更改控件。) 
1. 创建一个名为 MMA 的文件夹。
1. 下载以下内容，然后将它们放在 MMA 文件夹中：
   
    - 客户体验和诊断遥测的更新：
      - [对于 Windows Server 2008 R2 x64](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)
     
    对于 Windows Server 2008 R2 SP1，还需要以下更新：

    2018 年 2 月汇总 - KB4074598 (Windows Server 2008 R2) 

    [Microsoft 更新目录](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4074598)<br>
    下载 Windows Server 2008 R2 x64 的更新
    
    .NET Framework 3.5.1 (KB315418) <br>
    [对于 Windows Server 2008 R2 x64](https://download.microsoft.com/download/6/8/0/680ee424-358c-4fdf-a0de-b45dee07b711/windows6.1-kb3154518-x64.msu)
    
    >[!NOTE]
    > 本文假定你正在使用基于 x64 的服务器 (MMA 代理.exe x64 新 SHA-2 兼容) 。


**步骤 2：使用记事本工具创建 (DeployMMA.cmd)** 将以下行添加到 cmd 文件。 请注意，你将需要工作区 ID 和密钥。

以下命令是一个示例。 替换以下值：
- KB - 使用与要载入的终结点相关的适用 KB
- 工作区 ID 和密钥 - 使用 ID 和密钥


```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (

wusa.exe C:\Windows\MMA\Windows6.1-KB3080149-x64.msu /quiet /norestart
wusa.exe C:\Windows\MMA\Windows6.1-KB4074598-x64.msu /quiet /norestart
wusa.exe C:\Windows\MMA\Windows6.1-KB3154518-x64.msu /quiet /norestart
wusa.exe C:\Windows\MMA\Windows8.1-KB3080149-x64.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /c /t: "C:\Windows\MMA"c:\windows\MMA\ setup.exe /qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID="<your workspace ID>"
OPINSIGHTS_WORKSPACE_KEY="<your workspace key>" AcceptEndUserLicenseAgreement=1
)

)
```





### <a name="group-policy-configuration"></a>组策略配置

创建专用于载入设备的新组策略，例如"适用于终结点载入的 Microsoft Defender"。

- 创建名为"c：\windows\MMA"的组策略文件夹

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="folders":::

    **这将在应用 GPO 的每台服务器上添加新文件夹（称为 MMA）并存储在 c：\windows 中。这将包含 MMA 的安装文件、必备组件和安装脚本。**

- 为存储在 Net 登录中的每个文件创建组策略文件首选项。

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="组策略图像 1":::

它将文件从 DOMAIN\NETLOGON\MMA\filename 复制到 C：\windows\MMA\filename ，因此安装文件是服务器 **的本地文件**：

:::image type="content" source="images/deploymma.png" alt-text="部署 mma cmd":::

重复此过程，但在"COMMON"选项卡上创建项目级别目标，因此文件仅复制到作用域中的相应平台/操作系统版本：

:::image type="content" source="images/targeteditor.png" alt-text="目标编辑器":::

对于 Windows Server 2008 R2，你将需要 (并且它将仅向下复制) 以下内容：
- Windows6.1-KB3080149-x64.msu
- Windows6.1-KB3154518-x64.msu
- Windows6.1-KB4075598-x64.msu


完成此操作后，你需要创建启动脚本策略：

:::image type="content" source="images/startupprops.png" alt-text="启动属性":::

要在此处运行的文件的名称为 c：\windows\MMA\DeployMMA.cmd。
在启动过程中重新启动服务器后，它将安装客户体验更新和诊断遥测 KB，然后安装 MMA 代理，同时设置工作区 ID 和密钥，并且将载入服务器。

如果不想重新启动所有 **服务器** ，您也可以使用即时任务运行 deployMMA.cmd。

这分两个阶段完成。 首先 **在** GPO 中创建文件和文件夹 - 为系统提供时间来确保已应用 GPO，并且所有服务器都有安装文件。 然后，添加即时任务。 这将获得相同的结果，而无需重新启动。

由于脚本具有退出方法，并且如果安装了 MMA，将不会重新运行，因此，您还可以使用每日计划任务来实现相同的结果。 与 Configuration Manager 合规性策略类似，它每天都会检查以确保 MMA 存在。

:::image type="content" source="images/schtask.png" alt-text="计划任务":::

:::image type="content" source="images/newtaskprops.png" alt-text="新任务属性":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="部署 mma 下载属性":::

:::image type="content" source="images/tasksch.png" alt-text="任务计划程序":::

如 Server 2008 R2 的载入文档所述，请参阅以下内容：对于 Windows Server 2008 R2 SP1，请确保满足以下要求：

- 安装 [2018 年 2 月每月更新汇总](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
- 安装 [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

请在载入 Windows Server 2008 R2 之前检查这些 KB 是否存在。 如果没有配置管理器管理服务器，此过程允许你载入所有服务器。


## <a name="offboard-endpoints"></a>载出终结点

有两个选项可以Windows从服务中离开终结点：

- 卸载 MMA 代理
- 删除 Defender for Endpoint 工作区配置

> [!NOTE]
> 载出会导致 Windows 终结点停止向门户发送传感器数据，但发送自终结点的数据，包括对已具有的任何警报的引用将保留最多 6 个月。

### <a name="uninstall-the-mma-agent"></a>卸载 MMA 代理

若要卸载 Windows 终结点，你可以卸载 MMA 代理或将其从报告分离到 Defender for Endpoint 工作区。 在离开代理后，终结点将不再将传感器数据发送到 Defender for Endpoint。
有关详细信息，请参阅禁用 [代理](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)。

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>删除 Defender for Endpoint 工作区配置

可以使用下列任一方法：

- 从 MMA 代理中删除 Defender for Endpoint 工作区配置
- 运行 PowerShell 命令以删除配置

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>从 MMA 代理中删除 Defender for Endpoint 工作区配置

1. 在 **"Microsoft Monitoring Agent属性**"中，选择 **"Azure Log Analytics (OMS) "** 选项卡。

2. 选择"适用于终结点的 Defender"工作区，然后单击"删除 **"。**

    ![属性Microsoft Monitoring Agent图像](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>运行 PowerShell 命令以删除配置

1. 获取工作区 ID：

   1. 在导航窗格中，选择 **"设置**  >  **载入"。**

   1. 选择相关操作系统并获取工作区 ID。

    
2. 打开提升的 PowerShell 并运行以下命令。 使用你获取的工作区 ID 并替换 `WorkspaceID` ：

    ```   
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```
