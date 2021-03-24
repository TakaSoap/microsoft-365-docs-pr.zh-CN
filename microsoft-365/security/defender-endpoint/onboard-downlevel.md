---
title: 在 Microsoft Defender ATP 上载入以前版本的 Windows
description: 载入受支持的以前版本的 Windows 设备，以便它们可以将传感器数据发送到 Microsoft Defender ATP 传感器
keywords: onboard， windows， 7， 81， oms， sp1， enterprise， pro， down level
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a70826ee6e245f6744d8fc64eaf06e8cd1bdb265
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054676"
---
# <a name="onboard-previous-versions-of-windows"></a>载入以前版本的 Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**平台**
- Windows 7 SP1 企业版
- Windows 7 SP1 专业版
- Windows 8.1 专业版
- Windows 8.1 企业版


>想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)。

Defender for Endpoint 扩展支持以包括低级别操作系统，在受支持的 Windows 版本上提供高级攻击检测和调查功能。

若要将下层 Windows 客户端终结点载入到 Defender for Endpoint，你需要：
- 配置和更新 System Center Endpoint Protection 客户端。
- 安装和配置 Microsoft 监视代理 (MMA) 向 Defender for Endpoint 报告传感器数据，如下所述。

> [!TIP]
> 载入设备后，你可以选择运行检测测试，以验证它是否正确载入到服务。 有关详细信息，请参阅对新载入的 Defender 终结点终结点运行检测 [测试](run-detection-test.md)。

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>配置和更新 System Center Endpoint Protection 客户端
> [!IMPORTANT]
> 只有当组织使用 System Center Endpoint Protection 或 SCEP (时，才需要) 。

Defender for Endpoint 与 System Center Endpoint Protection 集成，以通过禁止潜在恶意文件或可疑恶意软件来查看恶意软件检测，并阻止攻击在组织中传播。 

若要启用此集成，需要执行以下步骤： 
- 安装 [Endpoint Protection 客户端的 2017 年 1 月反恶意软件平台更新](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) 
- 将 SCEP 客户端云保护服务成员身份配置为 **高级** 设置
- 配置网络以允许连接到 Microsoft Defender 防病毒云。 有关详细信息，请参阅允许 [连接到 Microsoft Defender 防病毒云](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>安装和配置 Microsoft 监视代理 (MMA) 向 Microsoft Defender for Endpoint 报告传感器数据

### <a name="before-you-begin"></a>准备工作
查看以下详细信息以验证最低系统要求：
- 安装 [2018 年 2 月每月更新汇总](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)
  
  > [!NOTE]
  > 仅适用于 Windows 7 SP1 企业版和 Windows 7 SP1 专业版。 

- 安装 [客户体验和诊断遥测更新](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- 安装 [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > 仅适用于 Windows 7 SP1 企业版和 Windows 7 SP1 专业版。
    > 不要安装 4.0.x .NET Framework 4.0.x，因为它将否定上述安装。

- 满足 Azure Log Analytics 代理的最低系统要求。 有关详细信息，请参阅使用[Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)从环境中的计算机收集数据



1. 下载代理设置文件 [：Windows 64 位代理](https://go.microsoft.com/fwlink/?LinkId=828603) 或 [Windows 32 位代理](https://go.microsoft.com/fwlink/?LinkId=828604)。

2. 获取工作区 ID：
   - In the Defender for Endpoint navigation pane， select **Settings > Device management > Onboarding**
   - 选择 **Windows 7 SP1 和 8.1** 作为操作系统
   - 复制工作区 ID 和工作区密钥

3. 使用 Workspace ID 和 Workspace 密钥选择以下任一安装方法以安装代理：
    - [使用安装程序 手动安装代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。 <br>
      在" **代理设置选项** "页上，选择"将代理 **连接到 Azure Log Analytics (OMS)**
    - [使用命令行 安装代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。
    - [使用脚本 配置代理](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。

   > [!NOTE]
   > 如果你是美国政府客户，[](gov.md)在"Azure 云"下，如果使用安装向导，或者使用命令行或脚本，则需要选择"Azure 美国政府"，将"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE"参数设置为 1。

4. 如果使用代理连接到 Internet，请参阅配置代理设置部分。

完成后，你应该在一小时内在门户中看到已载入的终结点。

### <a name="configure-proxy-and-internet-connectivity-settings"></a>配置代理和 Internet 连接设置
 
- 每个 Windows 终结点必须能够使用 HTTPS 连接到 Internet。 此连接可以是直接的、使用代理的，也可以通过 [OMS 网关进行](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)。
- 如果代理或防火墙默认阻止所有流量，并仅允许特定域通过或 HTTPS 扫描 (SSL 检查) 已启用，请确保启用对 Defender [for Endpoint 服务 URL 的访问](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。

## <a name="offboard-client-endpoints"></a>载出客户端终结点
若要卸载，你可以从终结点卸载 MMA 代理或将其从报告分离到 Defender for Endpoint 工作区。 离开代理后，终结点将不再将传感器数据发送到 Defender for Endpoint。 

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)。

