---
title: 在无法访问 Internet 的情况下载入设备以访问 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 在没有 Internet 访问的情况下载入设备，以便它们可以将传感器数据发送到 Microsoft Defender for Endpoint 传感器
keywords: onboard， 服务器， vm， 本地， oms 网关， 日志分析， azure log analytics， mma
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
ms.openlocfilehash: 83f0f53e2d2376975f853d826531e749732416b7
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754322"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>在无法访问 Internet 的情况下载入设备以访问 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。


若要在没有 Internet 访问的情况下载入设备，需要执行以下常规步骤：

> [!IMPORTANT] 
> 以下步骤仅适用于使用基于 MMA 的解决方案运行早期版本Windows的设备。 有关详细信息，请参阅[将Windows载入到 Microsoft Defender for Endpoint 服务](/microsoft-365/security/defender-endpoint/configure-server-endpoints)。

> [!NOTE]
> - 如果通过"TelemetryProxyServer"注册表或 GPO 配置，则 OMS 网关服务器不能用作断开连接的 Windows 或 Windows Server 设备的代理。
> - 对于 Windows 或 Windows Server - 尽管可以使用 TelemetryProxyServer，但它必须指向标准代理设备或设备。
> - 此外，Windows环境中Windows服务器或服务器必须能够通过内部文件或 Web 服务器脱机更新证书信任列表。
> - 有关脱机更新 CTLS 的信息，请参阅 [配置文件或 Web 服务器以下载 CTL 文件](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)。

有关载入方法详细信息，请参阅以下文章：
- [载入以前版本的 Windows](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [将服务器载入 Microsoft Defender for Endpoint 服务](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [配置设备代理和 Internet 连接设置](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="devices-running-the-previous-mma-based-solution"></a>运行之前基于 MMA 的解决方案的设备

- 设置 Azure Log Analytics (以前称为 OMS Gateway) 充当代理或集线器：
  - [Azure Log Analytics 代理](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [安装和配置Microsoft Monitoring Agent (MMA) ](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma)指向 Defender for Endpoint Workspace 密钥& ID

[载入以前版本的 Windows](onboard-downlevel.md)

- 同一 Azure Log Analytics 网络中的脱机设备
  - 将 MMA 配置为指向：
    - 作为代理的 Azure Log Analytics IP
    - Defender for Endpoint 工作区密钥& ID

### <a name="azure-virtual-machines"></a>Azure 虚拟机

- 对于运行之前基于 MMA 的解决方案的设备，将 Azure Log Analytics Gateway (以前称为 OMS Gateway) 设置为充当代理或中心：
    - [Azure Log Analytics 网关](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
    - [安装和配置Microsoft Monitoring Agent (MMA) ](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma)指向 Defender for Endpoint Workspace 密钥& ID
- 同一网络 OMS 网关中的脱机 Azure VM
    - 将 Azure Log Analytics IP 配置为代理
    - Azure Log Analytics 工作区密钥& ID
- Microsoft Defender for Cloud
    - [\>安全策略日志分析工作区](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
    - [威胁检测 \> 允许终结点的 Defender 访问我的数据](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

    有关详细信息，请参阅 [使用安全策略](/azure/security-center/tutorial-security-policy)。
