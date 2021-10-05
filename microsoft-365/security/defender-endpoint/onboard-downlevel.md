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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 11771bc8a5eab4a514ef70db43946cead0b16214
ms.sourcegitcommit: d78553deeba23d2f8238f10e64c2e27f235dc37f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2021
ms.locfileid: "60124333"
---
# <a name="onboard-previous-versions-of-windows"></a>载入以前版本的 Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**平台**
- Windows 7 SP1 Enterprise
- Windows 7 SP1 Pro
- Windows 8.1 专业版
- Windows 8.1 企业版

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevel-abovefoldlink)。

Defender for Endpoint 扩展支持以包括低级别操作系统，在受支持的版本上提供高级攻击检测和Windows功能。

若要将低级别Windows客户端终结点载入到 Defender for Endpoint，你将需要：

- 配置和更新System Center Endpoint Protection客户端。
- 安装并配置Microsoft Monitoring Agent (MMA) 向 Defender for Endpoint 报告传感器数据，如下所述。

> [!TIP]
> 载入设备后，你可以选择运行检测测试，以验证它是否正确载入到服务。 有关详细信息，请参阅对新载入的 Defender 终结点终结点运行检测 [测试](run-detection-test.md)。

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a>配置和更新System Center Endpoint Protection客户端

> [!IMPORTANT]
> 只有当组织使用 SCEP System Center Endpoint Protection (时，才需要) 。

Defender for Endpoint 与 System Center Endpoint Protection集成，通过禁止潜在恶意文件或可疑恶意软件，提供恶意软件检测的可见性，并阻止攻击在组织中传播。

若要启用此集成，需要执行以下步骤：

- 为客户端[安装 2017](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)年 1 月Endpoint Protection更新
- 将 SCEP 客户端云保护服务成员身份配置为 **高级** 设置
- 配置网络以允许连接到 Microsoft Defender 防病毒 云。 有关详细信息，请参阅允许[连接到云Microsoft Defender 防病毒云](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a>安装和配置 Microsoft Monitoring Agent (MMA) 以将传感器数据报告给 Microsoft Defender for Endpoint

### <a name="before-you-begin"></a>准备工作

查看以下详细信息以验证最低系统要求：

- 安装 [2018 年 2 月每月更新汇总](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

  > [!NOTE]
  > 仅适用于 Windows 7 SP1 Enterprise Windows 7 SP1 Pro。

- 安装 [客户体验和诊断遥测更新](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

- 安装 [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本) [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)

    > [!NOTE]
    > 仅适用于 Windows 7 SP1 Enterprise Windows 7 SP1 Pro。
    > 不要安装 .NET Framework 4.0.x，因为它将否定上述安装。

- 满足 Azure Log Analytics 代理的最低系统要求。 有关详细信息，请参阅使用 Log [Analytics](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)从环境中的计算机收集数据。

1. 下载代理设置文件[：Windows 64](https://go.microsoft.com/fwlink/?LinkId=828603)位代理或 Windows [32 位代理](https://go.microsoft.com/fwlink/?LinkId=828604)。

2. 获取工作区 ID：
   - 在 Defender for Endpoint 导航窗格中，选择"设置 >**终结点>">载入"**
   - 选择 **Windows 7 SP1 和 8.1** 作为操作系统
   - 复制工作区 ID 和工作区密钥

3. 使用 Workspace ID 和 Workspace 密钥选择以下任一安装方法以安装代理：
    - [使用安装程序 手动安装代理](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)。

      在"**代理设置选项**"页上 **，连接代理登录到 Azure Log Analytics (OMS)**

    - [使用命令行 安装代理](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)。
    - [使用脚本 配置代理](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)。

   > [!NOTE]
   > 如果你是美国政府客户，[](gov.md)在"Azure 云"下，如果使用安装向导，或者使用命令行或脚本，则需要选择"Azure 美国政府"，将"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE"参数设置为 1。

4. 如果使用代理连接到 Internet，请参阅配置代理设置部分。

完成后，你应该在一小时内在门户中看到已载入的终结点。

### <a name="configure-proxy-and-internet-connectivity-settings"></a>配置代理和 Internet 连接设置

- 每个Windows终结点必须能够使用 HTTPS 连接到 Internet。 此连接可以是直接的、使用代理的，也可以通过 [OMS 网关进行](/azure/log-analytics/log-analytics-oms-gateway)。
- 如果代理或防火墙默认阻止所有流量，并且仅允许特定域通过或 HTTPS 扫描 (SSL 检查) 已启用，请确保启用对 Defender [for Endpoint 服务 URL 的访问](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)。

## <a name="run-a-detection-test-to-verify-onboarding"></a>运行检测测试以验证载入

载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。 有关详细信息，请参阅对新载入的 [Microsoft Defender for Endpoint](run-detection-test.md)设备运行检测测试。

## <a name="offboard-client-endpoints"></a>载出客户端终结点

若要卸载，你可以从终结点卸载 MMA 代理或将其从报告分离到 Defender for Endpoint 工作区。 在离开代理后，终结点将不再将传感器数据发送到 Defender for Endpoint。

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-downlevele-belowfoldlink)。
