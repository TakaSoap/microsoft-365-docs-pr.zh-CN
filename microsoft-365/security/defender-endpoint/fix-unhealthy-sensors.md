---
title: 修复 Microsoft Defender for Endpoint 中的不正常传感器
description: 修复报告为错误配置或不活动的设备传感器，以便服务从设备接收数据。
keywords: 错误配置， 非活动， 修复传感器， 传感器运行状况， 无传感器数据， 传感器数据， 通信受损， 通信
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: a24dc4ef23d32b19de9d2871b7d87aae90d05828
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055817"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="ffa47-104">修复 Microsoft Defender for Endpoint 中的不正常传感器</span><span class="sxs-lookup"><span data-stu-id="ffa47-104">Fix unhealthy sensors in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ffa47-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ffa47-105">**Applies to:**</span></span>
- [<span data-ttu-id="ffa47-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ffa47-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ffa47-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ffa47-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="ffa47-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ffa47-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ffa47-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ffa47-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

<span data-ttu-id="ffa47-110">分类为错误配置或非活动的设备可能由于各种原因被标记。</span><span class="sxs-lookup"><span data-stu-id="ffa47-110">Devices that are categorized as misconfigured or inactive can be flagged due to varying causes.</span></span> <span data-ttu-id="ffa47-111">本节提供了一些说明，说明可能导致设备被分类为非活动或错误配置的原因。</span><span class="sxs-lookup"><span data-stu-id="ffa47-111">This section provides some explanations as to what might have caused a device to be categorized as inactive or misconfigured.</span></span>

## <a name="inactive-devices"></a><span data-ttu-id="ffa47-112">非活动设备</span><span class="sxs-lookup"><span data-stu-id="ffa47-112">Inactive devices</span></span>

<span data-ttu-id="ffa47-113">非活动设备不一定由于问题而标记。</span><span class="sxs-lookup"><span data-stu-id="ffa47-113">An inactive device is not necessarily flagged due to an issue.</span></span> <span data-ttu-id="ffa47-114">在设备上采取的以下操作可能导致设备被分类为非活动状态：</span><span class="sxs-lookup"><span data-stu-id="ffa47-114">The following actions taken on a device can cause a device to be categorized as inactive:</span></span>

### <a name="device-is-not-in-use"></a><span data-ttu-id="ffa47-115">设备未在使用中</span><span class="sxs-lookup"><span data-stu-id="ffa47-115">Device is not in use</span></span>

<span data-ttu-id="ffa47-116">如果设备出于任何原因未使用七天以上，它将在门户中保持"非活动"状态。</span><span class="sxs-lookup"><span data-stu-id="ffa47-116">If the device has not been in use for more than seven days for any reason, it will remain in an ‘Inactive’ status in the portal.</span></span>

### <a name="device-was-reinstalled-or-renamed"></a><span data-ttu-id="ffa47-117">已重新安装或重命名设备</span><span class="sxs-lookup"><span data-stu-id="ffa47-117">Device was reinstalled or renamed</span></span>
<span data-ttu-id="ffa47-118">重新安装或重命名的设备将在 Microsoft Defender 安全中心中生成一个新的设备实体。</span><span class="sxs-lookup"><span data-stu-id="ffa47-118">A reinstalled or renamed device will generate a new device entity in Microsoft Defender Security Center.</span></span> <span data-ttu-id="ffa47-119">以前的设备实体在门户中将保持"非活动"状态。</span><span class="sxs-lookup"><span data-stu-id="ffa47-119">The previous device entity will remain with an ‘Inactive’ status in the portal.</span></span> <span data-ttu-id="ffa47-120">如果重新安装了设备并部署了 Defender for Endpoint 程序包，请搜索新设备名称以验证设备是否正常报告。</span><span class="sxs-lookup"><span data-stu-id="ffa47-120">If you reinstalled a device and deployed the Defender for Endpoint package, search for the new device name to verify that the device is reporting normally.</span></span>

### <a name="device-was-offboarded"></a><span data-ttu-id="ffa47-121">设备已载出</span><span class="sxs-lookup"><span data-stu-id="ffa47-121">Device was offboarded</span></span>
<span data-ttu-id="ffa47-122">如果设备已载出，它仍将显示在设备列表中。</span><span class="sxs-lookup"><span data-stu-id="ffa47-122">If the device was offboarded, it will still appear in devices list.</span></span> <span data-ttu-id="ffa47-123">七天后，设备运行状况应更改为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="ffa47-123">After seven days, the device health state should change to inactive.</span></span>

### <a name="device-is-not-sending-signals"></a><span data-ttu-id="ffa47-124">设备未发送信号</span><span class="sxs-lookup"><span data-stu-id="ffa47-124">Device is not sending signals</span></span>
<span data-ttu-id="ffa47-125">如果设备出于任何原因（包括属于错误配置设备分类的条件）未向任何 Microsoft Defender 终结点通道发送超过 7 天的信号，则设备可视为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="ffa47-125">If the device is not sending any signals for more than seven days to any of the Microsoft Defender for Endpoint channels for any reason including conditions that fall under misconfigured devices classification, a device can be considered inactive.</span></span> 

<span data-ttu-id="ffa47-126">你是否希望设备的状态为"活动"？</span><span class="sxs-lookup"><span data-stu-id="ffa47-126">Do you expect a device to be in ‘Active’ status?</span></span> <span data-ttu-id="ffa47-127">[打开支持票证](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)。</span><span class="sxs-lookup"><span data-stu-id="ffa47-127">[Open a support ticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span></span>

## <a name="misconfigured-devices"></a><span data-ttu-id="ffa47-128">错误配置的设备</span><span class="sxs-lookup"><span data-stu-id="ffa47-128">Misconfigured devices</span></span>
<span data-ttu-id="ffa47-129">可以将错误配置的设备进一步分类为：</span><span class="sxs-lookup"><span data-stu-id="ffa47-129">Misconfigured devices can further be classified to:</span></span>
- <span data-ttu-id="ffa47-130">通信受损</span><span class="sxs-lookup"><span data-stu-id="ffa47-130">Impaired communications</span></span>
- <span data-ttu-id="ffa47-131">无传感器数据</span><span class="sxs-lookup"><span data-stu-id="ffa47-131">No sensor data</span></span>

### <a name="impaired-communications"></a><span data-ttu-id="ffa47-132">通信受损</span><span class="sxs-lookup"><span data-stu-id="ffa47-132">Impaired communications</span></span>
<span data-ttu-id="ffa47-133">此状态表示设备和服务之间的通信有限。</span><span class="sxs-lookup"><span data-stu-id="ffa47-133">This status indicates that there's limited communication between the device and the service.</span></span>

<span data-ttu-id="ffa47-134">以下建议操作可帮助修复与通信受损的错误配置设备相关的问题：</span><span class="sxs-lookup"><span data-stu-id="ffa47-134">The following suggested actions can help fix issues related to a misconfigured device with impaired communications:</span></span>

- [<span data-ttu-id="ffa47-135">确保设备具有 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="ffa47-135">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="ffa47-136">Window Defender ATP 传感器需要 Microsoft Windows HTTP (WinHTTP) 报告传感器数据并与 Microsoft Defender for Endpoint 服务通信。</span><span class="sxs-lookup"><span data-stu-id="ffa47-136">The Window Defender ATP sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="ffa47-137">验证与 Microsoft Defender for Endpoint 服务 URL 的客户端连接</span><span class="sxs-lookup"><span data-stu-id="ffa47-137">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)</br>
  <span data-ttu-id="ffa47-138">验证代理配置是否成功完成，WinHTTP 能否发现并通过您环境中代理服务器进行通信，以及代理服务器是否允许流量到 Microsoft Defender for Endpoint 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="ffa47-138">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

<span data-ttu-id="ffa47-139">如果采取更正操作，但设备状态仍配置错误， [请打开支持票证](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="ffa47-139">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

### <a name="no-sensor-data"></a><span data-ttu-id="ffa47-140">无传感器数据</span><span class="sxs-lookup"><span data-stu-id="ffa47-140">No sensor data</span></span>
<span data-ttu-id="ffa47-141">状态为"无传感器数据"的错误配置设备与服务通信，但只能报告部分传感器数据。</span><span class="sxs-lookup"><span data-stu-id="ffa47-141">A misconfigured device with status ‘No sensor data’ has communication with the service but can only report partial sensor data.</span></span>
<span data-ttu-id="ffa47-142">按照以下操作更正与状态为"无传感器数据"的错误配置设备相关的已知问题：</span><span class="sxs-lookup"><span data-stu-id="ffa47-142">Follow theses actions to correct known issues related to a misconfigured device with status ‘No sensor data’:</span></span>

- [<span data-ttu-id="ffa47-143">确保设备具有 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="ffa47-143">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="ffa47-144">Window Defender ATP 传感器需要 Microsoft Windows HTTP (WinHTTP) 报告传感器数据并与 Microsoft Defender for Endpoint 服务通信。</span><span class="sxs-lookup"><span data-stu-id="ffa47-144">The Window Defender ATP sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="ffa47-145">验证与 Microsoft Defender for Endpoint 服务 URL 的客户端连接</span><span class="sxs-lookup"><span data-stu-id="ffa47-145">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)</br>
  <span data-ttu-id="ffa47-146">验证代理配置是否成功完成，WinHTTP 能否发现并通过您环境中代理服务器进行通信，以及代理服务器是否允许流量到 Microsoft Defender for Endpoint 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="ffa47-146">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

- [<span data-ttu-id="ffa47-147">确保诊断数据服务已启用</span><span class="sxs-lookup"><span data-stu-id="ffa47-147">Ensure the diagnostic data service is enabled</span></span>](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
<span data-ttu-id="ffa47-148">如果设备未正确报告，你可能需要检查 Windows 10 诊断数据服务是否设置为自动启动并且正在终结点上运行。</span><span class="sxs-lookup"><span data-stu-id="ffa47-148">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the endpoint.</span></span>

- [<span data-ttu-id="ffa47-149">确保策略未禁用 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="ffa47-149">Ensure that Microsoft Defender Antivirus is not disabled by policy</span></span>](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
<span data-ttu-id="ffa47-150">如果你的设备运行的是第三方反恶意软件客户端，则 Defender for Endpoint 代理需要启用 Microsoft Defender 防病毒提前启动反恶意软件 (ELAM) 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="ffa47-150">If your devices are running a third-party antimalware client, the Defender for Endpoint agent needs the Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver to be enabled.</span></span>

<span data-ttu-id="ffa47-151">如果采取更正操作，但设备状态仍配置错误， [请打开支持票证](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="ffa47-151">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

## <a name="see-also"></a><span data-ttu-id="ffa47-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffa47-152">See also</span></span>
- [<span data-ttu-id="ffa47-153">检查 Microsoft Defender for Endpoint 中的传感器运行状况</span><span class="sxs-lookup"><span data-stu-id="ffa47-153">Check sensor health state in Microsoft Defender for Endpoint</span></span>](check-sensor-status.md)
