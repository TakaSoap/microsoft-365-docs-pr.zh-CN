---
title: 在无法访问 Internet 的情况下载入设备以访问 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 在没有 Internet 访问的情况下载入设备，以便它们可以将传感器数据发送到 Microsoft Defender for Endpoint 传感器
keywords: onboard， 服务器， vm， 本地， oms 网关， 日志分析， azure log analytics， mma
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
ms.openlocfilehash: ee06f927579445825a2b2813e483c24357d2ed78
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934917"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="577ed-104">在无法访问 Internet 的情况下载入设备以访问 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="577ed-104">Onboard devices without Internet access to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="577ed-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="577ed-105">**Applies to:**</span></span>
- [<span data-ttu-id="577ed-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="577ed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="577ed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="577ed-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="577ed-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="577ed-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="577ed-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="577ed-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="577ed-110">若要在没有 Internet 访问的情况下载入设备，需要执行以下常规步骤：</span><span class="sxs-lookup"><span data-stu-id="577ed-110">To onboard devices without Internet access, you'll need to take the following general steps:</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="577ed-111">以下步骤仅适用于运行以前版本的 Windows 的设备，例如 Windows Server 2016 及更早版本或 Windows 8.1 及更早版本。</span><span class="sxs-lookup"><span data-stu-id="577ed-111">The steps below are applicable only to devices running previous versions of Windows such as: Windows Server 2016 and earlier or Windows 8.1 and earlier.</span></span>

> [!NOTE]
> - <span data-ttu-id="577ed-112">如果通过"TelemetryProxyServer"注册表或 GPO 进行配置，则 OMS 网关服务器不能用作断开连接的 Windows 10 或 Windows Server 2019 设备的代理。</span><span class="sxs-lookup"><span data-stu-id="577ed-112">An OMS gateway server cannot be used as proxy for disconnected Windows 10 or Windows Server 2019 devices when configured via 'TelemetryProxyServer' registry or GPO.</span></span>
> - <span data-ttu-id="577ed-113">对于 Windows 10 或 Windows Server 2019 - 尽管可以使用 TelemetryProxyServer，但它必须指向标准代理设备或设备。</span><span class="sxs-lookup"><span data-stu-id="577ed-113">For Windows 10 or Windows Server 2019 - while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.</span></span>
> - <span data-ttu-id="577ed-114">此外，断开连接的环境中的 Windows 10 或 Windows Server 2019 必须能够通过内部文件或 Web 服务器脱机更新证书信任列表。</span><span class="sxs-lookup"><span data-stu-id="577ed-114">In addition, Windows 10 or Windows Server 2019 in disconnected environments must be able to update Certificate Trust Lists offline via an internal file or web server.</span></span>
> - <span data-ttu-id="577ed-115">有关脱机更新 CTLS 的信息，请参阅配置文件或 [Web 服务器以下载 CTL 文件](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)。</span><span class="sxs-lookup"><span data-stu-id="577ed-115">For more information about updating CTLs offline, see [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span></span>

<span data-ttu-id="577ed-116">有关载入方法详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="577ed-116">For more information about onboarding methods, see the following articles:</span></span>
- [<span data-ttu-id="577ed-117">载入以前版本的 Windows</span><span class="sxs-lookup"><span data-stu-id="577ed-117">Onboard previous versions of Windows</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [<span data-ttu-id="577ed-118">将服务器载入 Microsoft Defender for Endpoint 服务</span><span class="sxs-lookup"><span data-stu-id="577ed-118">Onboard servers to the Microsoft Defender for Endpoint service</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [<span data-ttu-id="577ed-119">配置设备代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="577ed-119">Configure device proxy and Internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a><span data-ttu-id="577ed-120">本地设备</span><span class="sxs-lookup"><span data-stu-id="577ed-120">On-premise devices</span></span>

- <span data-ttu-id="577ed-121">设置 Azure Log Analytics (以前称为 OMS Gateway) 充当代理或集线器：</span><span class="sxs-lookup"><span data-stu-id="577ed-121">Setup Azure Log Analytics (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
  - [<span data-ttu-id="577ed-122">Azure Log Analytics 代理</span><span class="sxs-lookup"><span data-stu-id="577ed-122">Azure Log Analytics Agent</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - <span data-ttu-id="577ed-123">[安装和配置 Microsoft Monitoring Agent (MMA ](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)) 指向 Defender for Endpoint Workspace key & ID</span><span class="sxs-lookup"><span data-stu-id="577ed-123">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>

- <span data-ttu-id="577ed-124">同一 Azure Log Analytics 网络中的脱机设备</span><span class="sxs-lookup"><span data-stu-id="577ed-124">Offline devices in the same network of Azure Log Analytics</span></span>
  -  <span data-ttu-id="577ed-125">将 MMA 配置为指向：</span><span class="sxs-lookup"><span data-stu-id="577ed-125">Configure MMA to point to:</span></span>
     - <span data-ttu-id="577ed-126">作为代理的 Azure Log Analytics IP</span><span class="sxs-lookup"><span data-stu-id="577ed-126">Azure Log Analytics IP as a proxy</span></span>
     - <span data-ttu-id="577ed-127">Defender for Endpoint 工作区密钥& ID</span><span class="sxs-lookup"><span data-stu-id="577ed-127">Defender for Endpoint workspace key & ID</span></span>

## <a name="azure-virtual-machines"></a><span data-ttu-id="577ed-128">Azure 虚拟机</span><span class="sxs-lookup"><span data-stu-id="577ed-128">Azure virtual machines</span></span>
- <span data-ttu-id="577ed-129">配置和启用 [Azure Log Analytics 工作区](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span><span class="sxs-lookup"><span data-stu-id="577ed-129">Configure and enable [Azure Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span></span>

    - <span data-ttu-id="577ed-130">设置 Azure Log Analytics Gateway (以前称为 OMS 网关) 充当代理或集线器：</span><span class="sxs-lookup"><span data-stu-id="577ed-130">Setup Azure Log Analytics Gateway (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
      - [<span data-ttu-id="577ed-131">Azure Log Analytics 网关</span><span class="sxs-lookup"><span data-stu-id="577ed-131">Azure Log Analytics Gateway</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - <span data-ttu-id="577ed-132">[安装和配置 Microsoft Monitoring Agent (MMA ](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)) 指向 Defender for Endpoint Workspace key & ID</span><span class="sxs-lookup"><span data-stu-id="577ed-132">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>
    - <span data-ttu-id="577ed-133">同一网络 OMS 网关中的脱机 Azure VM</span><span class="sxs-lookup"><span data-stu-id="577ed-133">Offline Azure VMs in the same network of OMS Gateway</span></span>
      - <span data-ttu-id="577ed-134">将 Azure Log Analytics IP 配置为代理</span><span class="sxs-lookup"><span data-stu-id="577ed-134">Configure Azure Log Analytics IP as a proxy</span></span>
      - <span data-ttu-id="577ed-135">Azure Log Analytics 工作区密钥& ID</span><span class="sxs-lookup"><span data-stu-id="577ed-135">Azure Log Analytics Workspace Key & ID</span></span>

    - <span data-ttu-id="577ed-136">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="577ed-136">Azure Defender</span></span>
      - [<span data-ttu-id="577ed-137">安全策略 \> 日志分析工作区</span><span class="sxs-lookup"><span data-stu-id="577ed-137">Security Policy \> Log Analytics Workspace</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [<span data-ttu-id="577ed-138">威胁 \> 检测允许终结点的 Defender 访问我的数据</span><span class="sxs-lookup"><span data-stu-id="577ed-138">Threat Detection \> Allow Defender for Endpoint to access my data</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        <span data-ttu-id="577ed-139">有关详细信息，请参阅 [使用安全策略](https://docs.microsoft.com/azure/security-center/tutorial-security-policy)。</span><span class="sxs-lookup"><span data-stu-id="577ed-139">For more information, see [Working with security policies](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).</span></span>
