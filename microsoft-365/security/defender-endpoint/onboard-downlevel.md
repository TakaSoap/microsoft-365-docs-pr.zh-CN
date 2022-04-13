---
title: 在 Microsoft Defender for Endpoint 上载入以前版本的 Windows
description: 载入支持以前版本的Windows设备，以便它们可以将传感器数据发送到Microsoft Defender for Endpoint传感器
keywords: 载入， windows， 7， 81， oms， sp1， 企业， 专业， 下级
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
ms.openlocfilehash: 0cd1e0aa999200814639f24401bf019774ca1d43
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64825203"
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

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevel-abovefoldlink)。

Defender for Endpoint 支持包括下层操作系统，为受支持的Windows版本提供高级攻击检测和调查功能。

若要将下层Windows客户端终结点载入 Defender for Endpoint，需要：

- [配置和更新System Center Endpoint Protection客户端](#configure-and-update-system-center-endpoint-protection-clients)
- [安装和配置 Microsoft Monitoring Agent (MMA) 以报告传感器数据](#install-and-configure-microsoft-monitoring-agent-mma)

对于Windows服务器 2008 R2 SP1，可以选择[通过Microsoft Defender for Cloud载入](#onboard-windows-servers-through-microsoft-defender-for-cloud)。

> [!NOTE]
> 每个节点都需要 Defender for Endpoint 独立服务器许可证才能通过Microsoft Monitoring Agent (选项 1) 载入Windows服务器。 或者，每个节点都需要 Microsoft Defender for servers 许可证才能通过Microsoft Defender for Cloud (选项 2) 载入Windows服务器，请参阅[Microsoft Defender for Cloud中提供的受支持功能](/azure/security-center/security-center-services)。

> [!TIP]
> 载入设备后，可以选择运行检测测试以验证设备是否已正确加入服务。 有关详细信息，请参阅 [在新加入的 Defender for Endpoint 终结点上运行检测测试](run-detection-test.md)。

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>配置和更新System Center Endpoint Protection客户端

> [!IMPORTANT]
> 仅当组织使用System Center Endpoint Protection (SCEP) 时，才需要此步骤。

Defender for Endpoint 与System Center Endpoint Protection集成，通过禁止潜在的恶意文件或可疑恶意软件来提供恶意软件检测的可见性，并停止在组织中传播攻击。

若要启用此集成，需要执行以下步骤：

- [为Endpoint Protection客户端安装 2017 年 1 月反恶意软件平台更新](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)
- 将 SCEP 客户端云保护服务成员身份配置为 **高级** 设置
- 将网络配置为允许连接到Microsoft Defender 防病毒云。 有关详细信息，请参阅[配置和验证Microsoft Defender 防病毒网络连接](/microsoft-365/security/defender-endpoint/configure-network-connections-microsoft-defender-antivirus)

## <a name="install-and-configure-microsoft-monitoring-agent-mma"></a>安装和配置 Microsoft Monitoring Agent (MMA) 

### <a name="before-you-begin"></a>准备工作

查看以下详细信息以验证最低系统要求：

- 安装 [2018 年 2 月每月更新汇总](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

  > [!NOTE]
  > 仅适用于 Windows Server 2008 R2、Windows 7 SP1 Enterprise 和 Windows 7 SP1 Pro。

- 安装 [更新以获得客户体验和诊断遥测](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- 安装 [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) 或 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > 仅适用于 Windows Server 2008 R2、Windows 7 SP1 Enterprise 和 Windows 7 SP1 Pro。
    >
    > 请勿安装.NET Framework 4.0.x，因为它将否定上述安装。
    >
    > 安装 .NET 4.5 可能需要在安装后重启计算机。

- 满足 Azure Log Analytics 代理最低系统要求。 有关详细信息，请参阅 [使用 Log Analytics 从环境中的计算机收集数据](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)

### <a name="installation-steps"></a>安装步骤

1. 下载代理安装文件：[Windows 64 位代理](https://go.microsoft.com/fwlink/?LinkId=828603)或 [Windows 32 位代理](https://go.microsoft.com/fwlink/?LinkId=828604)。

    >[!NOTE]
    >由于 [MMA 代理弃用了 SHA-1 支持](/azure/azure-monitor/agents/agent-windows#sha-2-code-signing-support-requirement)，MMA 代理需要版本 10.20.18029 或更高版本。
    

2. 获取工作区 ID：
   - 在“Defender for Endpoint”导航窗格中，选择 **设置 >设备管理>载入**
   - 选择操作系统
   - 复制工作区 ID 和工作区密钥

3. 使用工作区 ID 和工作区密钥选择以下任何安装方法来安装代理：
    - [使用安装程序手动安装代理](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。

      在 **“代理设置选项**”页上，选择 **代理连接到 Azure Log Analytics (OMS)**

    - [使用命令行安装代理](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。
    - [使用脚本配置代理](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。

   > [!NOTE]
   > 如果你是 [美国政府客户](gov.md)，则在“Azure 云”下，如果使用安装向导，或者使用命令行或脚本，则需要选择“Azure 美国政府”，将“OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE”参数设置为 1。

4. 如果使用代理连接到 Internet，请参阅“配置代理和 Internet 连接设置”部分。

完成后，应在一小时内在门户中看到载入终结点。

## <a name="configure-proxy-and-internet-connectivity-settings"></a>配置代理和 Internet 连接设置
如果服务器需要使用代理与 Defender for Endpoint 通信，请使用以下方法之一将 MMA 配置为使用代理服务器：

- [将 MMA 配置为使用代理服务器](/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [将Windows配置为对所有连接使用代理服务器](configure-proxy-internet.md)

如果使用代理或防火墙，请确保服务器可以直接访问所有Microsoft Defender for Endpoint服务 URL，而无需 SSL 拦截。 有关详细信息，请参阅 [启用对 Defender for Endpoint 服务 URL 的访问](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。 使用 SSL 拦截将阻止系统与 Defender for Endpoint 服务通信。

完成后，应会在一小时内在门户中看到载入的Windows服务器。

## <a name="onboard-windows-servers-through-microsoft-defender-for-cloud"></a>通过Microsoft Defender for Cloud载入Windows服务器

1. 在Microsoft 365 Defender导航窗格中，选择 **设置** > **Device** **managementOnboarding** > 。

2. 选择 **Windows服务器 2008 R2 SP1** 作为操作系统。

3. 在Microsoft Defender for Cloud中单击“**载入服务器**”。

4. 使用[Microsoft Defender for Cloud按照Microsoft Defender for Endpoint](/azure/security-center/security-center-wdatp)中的载入说明操作，如果使用的是 Azure ARC，请按照[“启用Microsoft Defender for Endpoint”中的载入说明操作集成](/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)。

完成载入步骤后，需要[配置和更新System Center Endpoint Protection客户端](#configure-and-update-system-center-endpoint-protection-clients)。

> [!NOTE]
>
> - 若要通过 Microsoft Defender 载入服务器才能按预期工作，服务器必须在 Microsoft Monitoring Agent (MMA) 设置中配置适当的工作区和密钥。
> - 配置后，会在计算机上部署相应的云管理包，并部署和启动传感器进程 (MsSenseS.exe) 。
> - 如果服务器配置为使用 OMS 网关服务器作为代理，则还需要这样做。



## <a name="verify-onboarding"></a>验证载入

验证 Microsoft Defender AV 和Microsoft Defender for Endpoint是否正在运行。 

> [!NOTE]
> 运行 Microsoft Defender AV 不是必需的，但建议运行。 如果另一个防病毒供应商产品是主要的终结点保护解决方案，则可以在被动模式下运行 Defender 防病毒。 只有在验证Microsoft Defender for Endpoint传感器 (SENSE) 是否正在运行后，才能确认被动模式是否处于打开状态。 

1. 运行以下命令以验证是否安装了 Microsoft Defender AV：

   ```sc.exe query Windefend```

    如果结果为“指定的服务不存在作为已安装的服务”，则需要安装 Microsoft Defender AV。 有关详细信息，请参阅[Windows 10中的Microsoft Defender 防病毒](microsoft-defender-antivirus-windows.md)。

    有关如何使用组策略在Windows服务器上配置和管理Microsoft Defender 防病毒的信息，请参阅[使用组策略设置来配置和管理Microsoft Defender 防病毒](use-group-policy-microsoft-defender-antivirus.md)。


2. 运行以下命令以验证Microsoft Defender for Endpoint是否正在运行：

    ```sc.exe query sense```
    
    结果应显示它正在运行。 如果在载入方面遇到问题，请参阅 [载入疑难解答](troubleshoot-onboarding.md)。

## <a name="run-a-detection-test"></a>运行检测测试
按照 [在新载入的设备上运行检测测试](run-detection-test.md) 中的步骤，验证服务器是否向 Defender for Endpoint 服务报告。





## <a name="onboarding-endpoints-with-no-management-solution"></a>载入没有管理解决方案的终结点 

### <a name="using-group-policy"></a>使用组策略

**步骤 1：下载终结点的相应 udpate。**

1. 导航到 c：\windows\sysvol\domain\scripts (可能需要在其中一个域控制器上进行更改控制。) 
1. 创建名为 MMA 的文件夹。
1. 下载以下内容并将其放在 MMA 文件夹中：
   
    - 更新客户体验和诊断遥测：
      - [对于Windows服务器 2008 R2 x64](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)
     
    对于Windows服务器 2008 R2 SP1，还需要以下更新：

    2018 年 2 月月汇总 - KB4074598 (Windows Server 2008 R2) 

    [Microsoft 更新目录](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4074598)<br>
    下载 Windows Server 2008 R2 x64 的更新
    
    .NET Framework 3.5.1 (KB315418) <br>
    [对于Windows服务器 2008 R2 x64](https://download.microsoft.com/download/6/8/0/680ee424-358c-4fdf-a0de-b45dee07b711/windows6.1-kb3154518-x64.msu)
    
    >[!NOTE]
    > 本文假设使用基于 x64 的服务器 (MMA 代理.exe x64 新 SHA-2 兼容版本) 。


**步骤 2：使用记事本) 创建文件名 DeployMMA.cmd (** 将以下行添加到 cmd 文件。 请注意，需要工作区 ID 和密钥。

下面的命令是一个示例。 替换以下值：
- KB - 使用与载入终结点相关的适用 KB
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

创建一个新的组策略，专门用于载入设备，例如“Microsoft Defender for Endpoint载入”。

- 创建名为“c：\windows\MMA”的组策略文件夹

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="文件夹位置" lightbox="images/grppolicyconfig1.png":::

    **这会在每个服务器上添加一个新文件夹，该文件夹将应用 GPO，称为 MMA，并将存储在 c：\windows 中。这将包含 MMA 的安装文件、先决条件和安装脚本。**

- 为 Net 登录中存储的每个文件创建组策略文件首选项。

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="组策略 - 1" lightbox="images/grppolicyconfig2.png":::

它将文件从 DOMAIN\NETLOGON\MMA\filename 复制到 C：\windows\MMA\filename - **因此安装文件是服务器的本地** 文件：

:::image type="content" source="images/deploymma.png" alt-text="部署 mma cmd 属性" lightbox="images/deploymma.png":::

重复此过程，但在 COMMON 选项卡上创建项目级别目标，因此文件仅在范围内复制到相应的平台/操作系统版本：

:::image type="content" source="images/targeteditor.png" alt-text="目标编辑器" lightbox="images/targeteditor.png":::

对于Windows服务器 2008 R2，你将需要 (，它只会) 以下内容复制：
- Windows6.1-KB3080149-x64.msu
- Windows6.1-KB3154518-x64.msu
- Windows6.1-KB4075598-x64.msu


完成此操作后，需要创建启动脚本策略：

:::image type="content" source="images/startupprops.png" alt-text="启动属性" lightbox="images/startupprops.png":::

要在此处运行的文件的名称是 c：\windows\MMA\DeployMMA.cmd。
在启动过程中重启服务器后，它将安装更新以获得客户体验和诊断遥测 KB，然后安装 MMA 代理，同时设置工作区 ID 和密钥，并载入服务器。

如果不想重启所有服务器，也可以使用 **即时任务** 运行 deployMMA.cmd。

这可以分两个阶段完成。 首先在 GPO **中创建文件和文件夹** - 给系统时间以确保已应用 GPO，并且所有服务器都有安装文件。 然后，添加即时任务。 这将实现相同的结果，而无需重新启动。

由于脚本具有退出方法，并且在安装了 MMA 时不会重新运行，因此还可以使用每日计划任务来实现相同的结果。 与Configuration Manager合规性策略类似，它将每天检查以确保 MMA 存在。

:::image type="content" source="images/schtask.png" alt-text="计划任务" lightbox="images/schtask.png":::

:::image type="content" source="images/newtaskprops.png" alt-text="新的任务属性" lightbox="images/newtaskprops.png":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="部署 mma 下载属性" lightbox="images/deploymmadowmload.png":::

:::image type="content" source="images/tasksch.png" alt-text="任务计划程序" lightbox="images/tasksch.png":::

如服务器 2008 R2 的载入文档中所述，请参阅以下内容：对于 Windows Server 2008 R2 SP1，请确保满足以下要求：

- 安装 [2018 年 2 月每月更新汇总](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
- 安装 [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) 或 [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

在加入服务器 2008 R2 Windows之前，请检查 KB 是否存在。 如果没有管理服务器Configuration Manager，则此过程允许你载入所有服务器。


## <a name="offboard-endpoints"></a>脱机终结点

有两个选项可以从服务中Windows终结点：

- 卸载 MMA 代理
- 删除 Defender for Endpoint 工作区配置

> [!NOTE]
> 卸载会导致Windows终结点停止将传感器数据发送到门户，但终结点中的数据（包括对其已保留的任何警报的引用）将保留长达 6 个月。

### <a name="uninstall-the-mma-agent"></a>卸载 MMA 代理

若要卸载Windows终结点，可以卸载 MMA 代理或将其从报告分离到 Defender for Endpoint 工作区。 卸载代理后，终结点将不再将传感器数据发送到 Defender for Endpoint。
有关详细信息，请参阅 [“禁用代理](/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)”。

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a>删除 Defender for Endpoint 工作区配置

可以使用以下任一方法：

- 从 MMA 代理中删除 Defender for Endpoint 工作区配置
- 运行 PowerShell 命令以删除配置

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a>从 MMA 代理中删除 Defender for Endpoint 工作区配置

1. 在 **Microsoft Monitoring Agent属性** 中，选择 **“Azure Log Analytics (OMS)**”选项卡。

2. 选择 Defender for Endpoint 工作区，然后单击 **“删除**”。

    :::image type="content" source="images/atp-mma.png" alt-text="“工作区”窗格" lightbox="images/atp-mma.png":::

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a>运行 PowerShell 命令以删除配置

1. 获取工作区 ID：

   1. 在导航窗格中，选择 **设置** > **Onboarding**。

   1. 选择相关的操作系统并获取工作区 ID。

    
2. 打开提升的 PowerShell 并运行以下命令。 使用获取并替换 `WorkspaceID`的工作区 ID：

    ```   
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```
