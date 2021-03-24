---
title: 使用事件查看器查看事件和错误
description: 如果需要，请获取 (Microsoft Defender for Endpoint) 报告的所有事件的说明和进一步疑难解答步骤。
keywords: 疑难解答， 事件查看器， 日志摘要， 故障代码， 失败， Microsoft Defender for Endpoint 服务， 无法启动， 断开， 无法启动
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
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056538"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="5b59d-104">使用事件查看器查看事件和错误</span><span class="sxs-lookup"><span data-stu-id="5b59d-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5b59d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5b59d-105">**Applies to:**</span></span>
- <span data-ttu-id="5b59d-106">事件查看器</span><span class="sxs-lookup"><span data-stu-id="5b59d-106">Event Viewer</span></span>
- [<span data-ttu-id="5b59d-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5b59d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5b59d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b59d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5b59d-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5b59d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5b59d-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5b59d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="5b59d-111">可以在各个设备上的事件查看器 [中查看](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) 事件 ID。</span><span class="sxs-lookup"><span data-stu-id="5b59d-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="5b59d-112">例如，如果设备未显示在"设备"列表中，你可能需要在设备上查找事件 ID。</span><span class="sxs-lookup"><span data-stu-id="5b59d-112">For example, if devices are not appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="5b59d-113">然后，可以使用此表确定进一步的疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="5b59d-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="5b59d-114">**打开事件查看器并查找 Microsoft Defender for Endpoint 服务事件日志：**</span><span class="sxs-lookup"><span data-stu-id="5b59d-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="5b59d-115">单击 **Windows** 菜单上的"开始"，键入 **"事件查看器"，** 然后按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="5b59d-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="5b59d-116">在日志列表中的"日志 **摘要"下**，滚动到看到 **"Microsoft-Windows-SENSE/Operational"。**</span><span class="sxs-lookup"><span data-stu-id="5b59d-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="5b59d-117">双击该项以打开日志。</span><span class="sxs-lookup"><span data-stu-id="5b59d-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="5b59d-118">a.</span><span class="sxs-lookup"><span data-stu-id="5b59d-118">a.</span></span>  <span data-ttu-id="5b59d-119">您还可以通过展开"应用程序和服务日志  >  **""Microsoft**  >  **Windows**  >  **SENSE"** 并单击"操作"来访问 **日志**。</span><span class="sxs-lookup"><span data-stu-id="5b59d-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5b59d-120">SENSE 是内部名称，用于引用支持 Microsoft Defender for Endpoint 的行为传感器。</span><span class="sxs-lookup"><span data-stu-id="5b59d-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="5b59d-121">服务记录的事件将显示在日志中。</span><span class="sxs-lookup"><span data-stu-id="5b59d-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="5b59d-122">有关服务记录的事件的列表，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="5b59d-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="5b59d-123">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5b59d-123">Event ID</span></span></th>
<th><span data-ttu-id="5b59d-124">邮件</span><span class="sxs-lookup"><span data-stu-id="5b59d-124">Message</span></span></th>
<th><span data-ttu-id="5b59d-125">说明</span><span class="sxs-lookup"><span data-stu-id="5b59d-125">Description</span></span></th>
<th><span data-ttu-id="5b59d-126">操作</span><span class="sxs-lookup"><span data-stu-id="5b59d-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="5b59d-127">1</span><span class="sxs-lookup"><span data-stu-id="5b59d-127">1</span></span></td>
<td><span data-ttu-id="5b59d-128">Microsoft Defender for Endpoint 服务 (版本 <code>variable</code>) 。</span><span class="sxs-lookup"><span data-stu-id="5b59d-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="5b59d-129">在系统启动、关闭和板载期间发生。</span><span class="sxs-lookup"><span data-stu-id="5b59d-129">Occurs during system start up, shut down, and during onbboarding.</span></span></td>
<td><span data-ttu-id="5b59d-130">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-131">2</span><span class="sxs-lookup"><span data-stu-id="5b59d-131">2</span></span></td>
<td><span data-ttu-id="5b59d-132">Microsoft Defender for Endpoint 服务关闭。</span><span class="sxs-lookup"><span data-stu-id="5b59d-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="5b59d-133">在设备关闭或载出时发生。</span><span class="sxs-lookup"><span data-stu-id="5b59d-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="5b59d-134">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-135">3</span><span class="sxs-lookup"><span data-stu-id="5b59d-135">3</span></span></td>
<td><span data-ttu-id="5b59d-136">Microsoft Defender for Endpoint 服务启动失败。</span><span class="sxs-lookup"><span data-stu-id="5b59d-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="5b59d-137">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-138">服务未启动。</span><span class="sxs-lookup"><span data-stu-id="5b59d-138">Service did not start.</span></span></td>
<td><span data-ttu-id="5b59d-139">查看其他消息以确定可能的原因和疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="5b59d-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-140">4 </span><span class="sxs-lookup"><span data-stu-id="5b59d-140">4</span></span></td>
<td><span data-ttu-id="5b59d-141">Microsoft Defender for Endpoint 服务与 位于 的服务器联系 <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="5b59d-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-142">变量 = 适用于终结点处理服务器的 Defender 的 URL。</span><span class="sxs-lookup"><span data-stu-id="5b59d-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="5b59d-143">此 URL 将匹配防火墙或网络活动中显示的内容。</span><span class="sxs-lookup"><span data-stu-id="5b59d-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="5b59d-144">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-145">5 </span><span class="sxs-lookup"><span data-stu-id="5b59d-145">5</span></span></td>
<td><span data-ttu-id="5b59d-146">Microsoft Defender for Endpoint 服务无法连接到 位于 的服务器 <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="5b59d-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-147">变量 = 适用于终结点处理服务器的 Defender 的 URL。</span><span class="sxs-lookup"><span data-stu-id="5b59d-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="5b59d-148">该服务无法通过该 URL 与外部处理服务器联系。</span><span class="sxs-lookup"><span data-stu-id="5b59d-148">The service could not contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="5b59d-149">检查与 URL 的连接。</span><span class="sxs-lookup"><span data-stu-id="5b59d-149">Check the connection to the URL.</span></span> <span data-ttu-id="5b59d-150">请参阅 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">配置代理和 Internet 连接</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-151">6 </span><span class="sxs-lookup"><span data-stu-id="5b59d-151">6</span></span></td>
<td><span data-ttu-id="5b59d-152">Microsoft Defender for Endpoint 服务未载入，并且未找到任何载入参数。</span><span class="sxs-lookup"><span data-stu-id="5b59d-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="5b59d-153">设备未正确载入，并且不会向门户报告。</span><span class="sxs-lookup"><span data-stu-id="5b59d-153">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="5b59d-154">在启动该服务之前，必须运行载入。</span><span class="sxs-lookup"><span data-stu-id="5b59d-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="5b59d-155">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="5b59d-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5b59d-156">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="5b59d-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5b59d-157">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-158">7 </span><span class="sxs-lookup"><span data-stu-id="5b59d-158">7</span></span></td>
<td><span data-ttu-id="5b59d-159">Microsoft Defender for Endpoint 服务无法读取载入参数。</span><span class="sxs-lookup"><span data-stu-id="5b59d-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="5b59d-160">失败 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-161">变量 = 详细的错误描述。</span><span class="sxs-lookup"><span data-stu-id="5b59d-161">Variable = detailed error description.</span></span> <span data-ttu-id="5b59d-162">设备未正确载入，并且不会向门户报告。</span><span class="sxs-lookup"><span data-stu-id="5b59d-162">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="5b59d-163">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="5b59d-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5b59d-164">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="5b59d-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5b59d-165">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-166">8 </span><span class="sxs-lookup"><span data-stu-id="5b59d-166">8</span></span></td>
<td><span data-ttu-id="5b59d-167">Microsoft Defender for Endpoint 服务无法清理其配置。</span><span class="sxs-lookup"><span data-stu-id="5b59d-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="5b59d-168">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-169"><b>载入期间：</b> 服务在载入期间未能清理其配置。</span><span class="sxs-lookup"><span data-stu-id="5b59d-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="5b59d-170">载入过程继续进行。</span><span class="sxs-lookup"><span data-stu-id="5b59d-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="5b59d-171"><b>在载出期间：</b> 该服务在载出过程中未能清理其配置。</span><span class="sxs-lookup"><span data-stu-id="5b59d-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="5b59d-172">载出过程已完成，但服务继续运行。</span><span class="sxs-lookup"><span data-stu-id="5b59d-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="5b59d-173"><b>载入：</b> 无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="5b59d-174"><b>载出：</b> 重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="5b59d-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="5b59d-175">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-176">9 </span><span class="sxs-lookup"><span data-stu-id="5b59d-176">9</span></span></td>
<td><span data-ttu-id="5b59d-177">Microsoft Defender for Endpoint 服务未能更改其启动类型。</span><span class="sxs-lookup"><span data-stu-id="5b59d-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="5b59d-178">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-179"><b>载入期间：</b> 设备未正确载入，并且不会向门户报告。</span><span class="sxs-lookup"><span data-stu-id="5b59d-179"><b>During onboarding:</b> The device did not onboard correctly and will not be reporting to the portal.</span></span> <br><br><span data-ttu-id="5b59d-180"><b>在载出期间：</b> 未能更改服务启动类型。</span><span class="sxs-lookup"><span data-stu-id="5b59d-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="5b59d-181">载出过程继续进行。</span><span class="sxs-lookup"><span data-stu-id="5b59d-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="5b59d-182">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="5b59d-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5b59d-183">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="5b59d-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5b59d-184">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-185">10  </span><span class="sxs-lookup"><span data-stu-id="5b59d-185">10</span></span></td>
<td><span data-ttu-id="5b59d-186">Microsoft Defender for Endpoint 服务无法保留载入信息。</span><span class="sxs-lookup"><span data-stu-id="5b59d-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="5b59d-187">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-188">设备未正确载入，并且不会向门户报告。</span><span class="sxs-lookup"><span data-stu-id="5b59d-188">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="5b59d-189">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="5b59d-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5b59d-190">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="5b59d-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5b59d-191">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-192">11</span><span class="sxs-lookup"><span data-stu-id="5b59d-192">11</span></span></td>
<td><span data-ttu-id="5b59d-193">已完成 Defender for Endpoint 服务的载入或重新载入。</span><span class="sxs-lookup"><span data-stu-id="5b59d-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="5b59d-194">设备已正确载入。</span><span class="sxs-lookup"><span data-stu-id="5b59d-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="5b59d-195">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="5b59d-196">设备可能需要几个小时才能显示在门户中。</span><span class="sxs-lookup"><span data-stu-id="5b59d-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-197">12 </span><span class="sxs-lookup"><span data-stu-id="5b59d-197">12</span></span></td>
<td><span data-ttu-id="5b59d-198">Microsoft Defender for Endpoint 无法应用默认配置。</span><span class="sxs-lookup"><span data-stu-id="5b59d-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="5b59d-199">服务无法应用默认配置。</span><span class="sxs-lookup"><span data-stu-id="5b59d-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="5b59d-200">此错误应在短时间内解决。</span><span class="sxs-lookup"><span data-stu-id="5b59d-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-201">13</span><span class="sxs-lookup"><span data-stu-id="5b59d-201">13</span></span></td>
<td><span data-ttu-id="5b59d-202">计算得出的 Microsoft Defender for Endpoint 设备 <code>variable</code> ID：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-203">正常操作过程。</span><span class="sxs-lookup"><span data-stu-id="5b59d-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="5b59d-204">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-205">15 </span><span class="sxs-lookup"><span data-stu-id="5b59d-205">15</span></span></td>
<td><span data-ttu-id="5b59d-206">Microsoft Defender for Endpoint 无法使用 URL 启动命令通道 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-207">变量 = 适用于终结点处理服务器的 Defender 的 URL。</span><span class="sxs-lookup"><span data-stu-id="5b59d-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="5b59d-208">该服务无法通过该 URL 与外部处理服务器联系。</span><span class="sxs-lookup"><span data-stu-id="5b59d-208">The service could not contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="5b59d-209">检查与 URL 的连接。</span><span class="sxs-lookup"><span data-stu-id="5b59d-209">Check the connection to the URL.</span></span> <span data-ttu-id="5b59d-210">请参阅 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">配置代理和 Internet 连接</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-211">17 </span><span class="sxs-lookup"><span data-stu-id="5b59d-211">17</span></span></td>
<td><span data-ttu-id="5b59d-212">Microsoft Defender for Endpoint 服务未能更改连接用户体验和遥测服务位置。</span><span class="sxs-lookup"><span data-stu-id="5b59d-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="5b59d-213">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-214">Windows 遥测服务出错。</span><span class="sxs-lookup"><span data-stu-id="5b59d-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="5b59d-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">确保诊断数据服务已启用</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="5b59d-216">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="5b59d-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5b59d-217">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="5b59d-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5b59d-218">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-219">18 </span><span class="sxs-lookup"><span data-stu-id="5b59d-219">18</span></span></td>
<td><span data-ttu-id="5b59d-220">OOBE (Windows 欢迎) 已完成。</span><span class="sxs-lookup"><span data-stu-id="5b59d-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="5b59d-221">服务仅在任何 Windows 更新完成安装后启动。</span><span class="sxs-lookup"><span data-stu-id="5b59d-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="5b59d-222">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-223">19</span><span class="sxs-lookup"><span data-stu-id="5b59d-223">19</span></span></td>
<td><span data-ttu-id="5b59d-224">OOBE (Windows 欢迎) 尚未完成。</span><span class="sxs-lookup"><span data-stu-id="5b59d-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="5b59d-225">服务仅在任何 Windows 更新完成安装后启动。</span><span class="sxs-lookup"><span data-stu-id="5b59d-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="5b59d-226">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="5b59d-227">如果在系统重新启动后此错误仍然存在，请确保所有 Windows 更新都已安装完整。</span><span class="sxs-lookup"><span data-stu-id="5b59d-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-228">20</span><span class="sxs-lookup"><span data-stu-id="5b59d-228">20</span></span></td>
<td><span data-ttu-id="5b59d-229">无法等待 OOBE (Windows 欢迎) 完成。</span><span class="sxs-lookup"><span data-stu-id="5b59d-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="5b59d-230">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-231">内部错误。</span><span class="sxs-lookup"><span data-stu-id="5b59d-231">Internal error.</span></span></td>
<td><span data-ttu-id="5b59d-232">如果在系统重新启动后此错误仍然存在，请确保所有 Windows 更新都已安装完整。</span><span class="sxs-lookup"><span data-stu-id="5b59d-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-233">25</span><span class="sxs-lookup"><span data-stu-id="5b59d-233">25</span></span></td>
<td><span data-ttu-id="5b59d-234">Microsoft Defender for Endpoint 服务无法重置注册表中的运行状况状态。</span><span class="sxs-lookup"><span data-stu-id="5b59d-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="5b59d-235">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-236">设备未正确载入。</span><span class="sxs-lookup"><span data-stu-id="5b59d-236">The device did not onboard correctly.</span></span>
<span data-ttu-id="5b59d-237">它将报告给门户，但该服务可能不会显示为在 SCCM 或注册表中注册。</span><span class="sxs-lookup"><span data-stu-id="5b59d-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="5b59d-238">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="5b59d-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5b59d-239">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="5b59d-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5b59d-240">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-241">26</span><span class="sxs-lookup"><span data-stu-id="5b59d-241">26</span></span></td>
<td><span data-ttu-id="5b59d-242">Microsoft Defender for Endpoint 服务未能在注册表中设置载入状态。</span><span class="sxs-lookup"><span data-stu-id="5b59d-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="5b59d-243">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-244">设备未正确载入。</span><span class="sxs-lookup"><span data-stu-id="5b59d-244">The device did not onboard correctly.</span></span><br>
<span data-ttu-id="5b59d-245">它将报告给门户，但该服务可能不会显示为在 SCCM 或注册表中注册。</span><span class="sxs-lookup"><span data-stu-id="5b59d-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="5b59d-246">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="5b59d-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5b59d-247">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="5b59d-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5b59d-248">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-249">27</span><span class="sxs-lookup"><span data-stu-id="5b59d-249">27</span></span></td>
<td><span data-ttu-id="5b59d-250">Microsoft Defender for Endpoint 服务未能在 Microsoft Defender 防病毒中启用 SENSE 感知模式。</span><span class="sxs-lookup"><span data-stu-id="5b59d-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="5b59d-251">载入过程失败。</span><span class="sxs-lookup"><span data-stu-id="5b59d-251">Onboarding process failed.</span></span> <span data-ttu-id="5b59d-252">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-253">通常情况下，如果另一个实时反恶意软件产品正在设备上正常运行，并且设备向 Defender for Endpoint 报告，Microsoft Defender 防病毒将进入特殊的被动状态。</span><span class="sxs-lookup"><span data-stu-id="5b59d-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="5b59d-254">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="5b59d-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5b59d-255">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="5b59d-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5b59d-256">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="5b59d-257">确保实时反恶意软件保护运行正常。</span><span class="sxs-lookup"><span data-stu-id="5b59d-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-258">28</span><span class="sxs-lookup"><span data-stu-id="5b59d-258">28</span></span></td>
<td><span data-ttu-id="5b59d-259">Microsoft Defender 终结点连接用户体验和遥测服务注册失败。</span><span class="sxs-lookup"><span data-stu-id="5b59d-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="5b59d-260">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-261">Windows 遥测服务出错。</span><span class="sxs-lookup"><span data-stu-id="5b59d-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="5b59d-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">确保诊断数据服务已启用</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="5b59d-263">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="5b59d-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5b59d-264">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="5b59d-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5b59d-265">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-266">29</span><span class="sxs-lookup"><span data-stu-id="5b59d-266">29</span></span></td>
<td><span data-ttu-id="5b59d-267">未能读取 offboarding参数。</span><span class="sxs-lookup"><span data-stu-id="5b59d-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="5b59d-268">错误类型：%1，错误代码：%2，说明：%3</span><span class="sxs-lookup"><span data-stu-id="5b59d-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="5b59d-269">当系统无法读取&#39;时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="5b59d-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="5b59d-270">确保设备可以访问 Internet，然后再次运行整个载出过程。</span><span class="sxs-lookup"><span data-stu-id="5b59d-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="5b59d-271">确保载出包尚未过期。</span><span class="sxs-lookup"><span data-stu-id="5b59d-271">Ensure the offboarding package has not expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-272">30</span><span class="sxs-lookup"><span data-stu-id="5b59d-272">30</span></span></td>
<td><span data-ttu-id="5b59d-273">Microsoft Defender for Endpoint 服务在 Microsoft Defender 防病毒中未能禁用 SENSE 感知模式。</span><span class="sxs-lookup"><span data-stu-id="5b59d-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="5b59d-274">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-275">通常情况下，如果另一个实时反恶意软件产品正在设备上正常运行，并且设备向 Defender for Endpoint 报告，Microsoft Defender 防病毒将进入特殊的被动状态。</span><span class="sxs-lookup"><span data-stu-id="5b59d-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="5b59d-276">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="5b59d-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5b59d-277">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="5b59d-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5b59d-278">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a></span><span class="sxs-lookup"><span data-stu-id="5b59d-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="5b59d-279">确保实时反恶意软件保护运行正常。</span><span class="sxs-lookup"><span data-stu-id="5b59d-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-280">31</span><span class="sxs-lookup"><span data-stu-id="5b59d-280">31</span></span></td>
<td><span data-ttu-id="5b59d-281">Microsoft Defender 终结点连接用户体验和遥测服务注销失败。</span><span class="sxs-lookup"><span data-stu-id="5b59d-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="5b59d-282">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-283">载入期间 Windows 遥测服务出错。</span><span class="sxs-lookup"><span data-stu-id="5b59d-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="5b59d-284">载出过程继续进行。</span><span class="sxs-lookup"><span data-stu-id="5b59d-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="5b59d-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">检查 Windows 遥测服务的错误</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-286">32</span><span class="sxs-lookup"><span data-stu-id="5b59d-286">32</span></span></td>
<td><span data-ttu-id="5b59d-287">Microsoft Defender for Endpoint 服务在离开进程后无法请求自行停止。</span><span class="sxs-lookup"><span data-stu-id="5b59d-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="5b59d-288">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="5b59d-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="5b59d-289">在载出期间出错。</span><span class="sxs-lookup"><span data-stu-id="5b59d-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="5b59d-290">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="5b59d-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-291">33</span><span class="sxs-lookup"><span data-stu-id="5b59d-291">33</span></span></td>
<td><span data-ttu-id="5b59d-292">Microsoft Defender for Endpoint 服务无法保留 SENSE GUID。</span><span class="sxs-lookup"><span data-stu-id="5b59d-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="5b59d-293">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-294">唯一标识符用于表示向门户报告的每个设备。</span><span class="sxs-lookup"><span data-stu-id="5b59d-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="5b59d-295">如果标识符未保留，同一设备可能在门户中出现两次。</span><span class="sxs-lookup"><span data-stu-id="5b59d-295">If the identifier does not persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="5b59d-296">检查设备的注册表权限，以确保服务可以更新注册表。</span><span class="sxs-lookup"><span data-stu-id="5b59d-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-297">34</span><span class="sxs-lookup"><span data-stu-id="5b59d-297">34</span></span></td>
<td><span data-ttu-id="5b59d-298">Microsoft Defender for Endpoint 服务无法将自身添加为连接用户体验和遥测服务的依赖项，从而导致载入过程失败。</span><span class="sxs-lookup"><span data-stu-id="5b59d-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="5b59d-299">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-300">Windows 遥测服务出错。</span><span class="sxs-lookup"><span data-stu-id="5b59d-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="5b59d-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">确保诊断数据服务已启用</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="5b59d-302">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="5b59d-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5b59d-303">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="5b59d-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5b59d-304">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="5b59d-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-305">35</span><span class="sxs-lookup"><span data-stu-id="5b59d-305">35</span></span></td>
<td><span data-ttu-id="5b59d-306">Microsoft Defender for Endpoint 服务无法删除自身作为连接用户体验和遥测服务的依赖项。</span><span class="sxs-lookup"><span data-stu-id="5b59d-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="5b59d-307">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-308">在载出期间 Windows 遥测服务出错。</span><span class="sxs-lookup"><span data-stu-id="5b59d-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="5b59d-309">载出过程继续进行。</span><span class="sxs-lookup"><span data-stu-id="5b59d-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="5b59d-310">检查 Windows 诊断数据服务的错误。</span><span class="sxs-lookup"><span data-stu-id="5b59d-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-311">36</span><span class="sxs-lookup"><span data-stu-id="5b59d-311">36</span></span></td>
<td><span data-ttu-id="5b59d-312">Microsoft Defender 终结点连接用户体验和遥测服务注册成功。</span><span class="sxs-lookup"><span data-stu-id="5b59d-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="5b59d-313">完成代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="5b59d-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5b59d-314">为终结点注册已成功完成连接用户体验和遥测服务的 Defender。</span><span class="sxs-lookup"><span data-stu-id="5b59d-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="5b59d-315">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-316">37</span><span class="sxs-lookup"><span data-stu-id="5b59d-316">37</span></span></td>
<td><span data-ttu-id="5b59d-317">Microsoft Defender for Endpoint A 模块即将超过其配额。</span><span class="sxs-lookup"><span data-stu-id="5b59d-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="5b59d-318">模块：%1，配额：{%2} {%3}，配额使用率百分比：%4。</span><span class="sxs-lookup"><span data-stu-id="5b59d-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="5b59d-319">设备几乎已使用当前 24 小时时段的已分配配额。</span><span class="sxs-lookup"><span data-stu-id="5b59d-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="5b59d-320">即将被限制。</span><span class="sxs-lookup"><span data-stu-id="5b59d-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="5b59d-321">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-322">38</span><span class="sxs-lookup"><span data-stu-id="5b59d-322">38</span></span></td>
<td><span data-ttu-id="5b59d-323">网络连接标识为低。</span><span class="sxs-lookup"><span data-stu-id="5b59d-323">Network connection is identified as low.</span></span> <span data-ttu-id="5b59d-324">Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。</span><span class="sxs-lookup"><span data-stu-id="5b59d-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="5b59d-325">按流量计费的连接：%2，Internet 可用：%3，可用网络：%4。</span><span class="sxs-lookup"><span data-stu-id="5b59d-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="5b59d-326">设备使用按流量计费/付费网络，并且与服务器联系的频率将较低。</span><span class="sxs-lookup"><span data-stu-id="5b59d-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="5b59d-327">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-328">39</span><span class="sxs-lookup"><span data-stu-id="5b59d-328">39</span></span></td>
<td><span data-ttu-id="5b59d-329">网络连接被标识为正常连接。</span><span class="sxs-lookup"><span data-stu-id="5b59d-329">Network connection is identified as normal.</span></span> <span data-ttu-id="5b59d-330">Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。</span><span class="sxs-lookup"><span data-stu-id="5b59d-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="5b59d-331">按流量计费的连接：%2，Internet 可用：%3，可用网络：%4。</span><span class="sxs-lookup"><span data-stu-id="5b59d-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="5b59d-332">设备未使用按流量计费/付费连接，将照常与服务器联系。</span><span class="sxs-lookup"><span data-stu-id="5b59d-332">The device is not using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="5b59d-333">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-334">40</span><span class="sxs-lookup"><span data-stu-id="5b59d-334">40</span></span></td>
<td><span data-ttu-id="5b59d-335">电池状态标识为低。</span><span class="sxs-lookup"><span data-stu-id="5b59d-335">Battery state is identified as low.</span></span> <span data-ttu-id="5b59d-336">Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。</span><span class="sxs-lookup"><span data-stu-id="5b59d-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="5b59d-337">电池状态：%2。</span><span class="sxs-lookup"><span data-stu-id="5b59d-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="5b59d-338">设备具有低电池电量，并且与服务器的联系频率较低。</span><span class="sxs-lookup"><span data-stu-id="5b59d-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="5b59d-339">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-340">41</span><span class="sxs-lookup"><span data-stu-id="5b59d-340">41</span></span></td>
<td><span data-ttu-id="5b59d-341">电池状态标识为正常。</span><span class="sxs-lookup"><span data-stu-id="5b59d-341">Battery state is identified as normal.</span></span> <span data-ttu-id="5b59d-342">Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。</span><span class="sxs-lookup"><span data-stu-id="5b59d-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="5b59d-343">电池状态：%2。</span><span class="sxs-lookup"><span data-stu-id="5b59d-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="5b59d-344">设备没有低电池电量，将照常与服务器联系。</span><span class="sxs-lookup"><span data-stu-id="5b59d-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="5b59d-345">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-346">42</span><span class="sxs-lookup"><span data-stu-id="5b59d-346">42</span></span></td>
<td><span data-ttu-id="5b59d-347">Microsoft Defender for Endpoint WDATP 组件无法执行该操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-347">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="5b59d-348">组件：%1，操作：%2，异常类型：%3，异常消息：%4</span><span class="sxs-lookup"><span data-stu-id="5b59d-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="5b59d-349">内部错误。</span><span class="sxs-lookup"><span data-stu-id="5b59d-349">Internal error.</span></span> <span data-ttu-id="5b59d-350">服务启动失败。</span><span class="sxs-lookup"><span data-stu-id="5b59d-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="5b59d-351">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="5b59d-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-352">43</span><span class="sxs-lookup"><span data-stu-id="5b59d-352">43</span></span></td>
<td><span data-ttu-id="5b59d-353">Microsoft Defender for Endpoint WDATP 组件无法执行该操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-353">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="5b59d-354">组件：%1，操作：%2，异常类型：%3，异常错误：%4，异常消息：%5</span><span class="sxs-lookup"><span data-stu-id="5b59d-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="5b59d-355">内部错误。</span><span class="sxs-lookup"><span data-stu-id="5b59d-355">Internal error.</span></span> <span data-ttu-id="5b59d-356">服务启动失败。</span><span class="sxs-lookup"><span data-stu-id="5b59d-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="5b59d-357">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="5b59d-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-358">44</span><span class="sxs-lookup"><span data-stu-id="5b59d-358">44</span></span></td>
<td><span data-ttu-id="5b59d-359">已完成 Defender for Endpoint Service 的载出。</span><span class="sxs-lookup"><span data-stu-id="5b59d-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="5b59d-360">服务已载出。</span><span class="sxs-lookup"><span data-stu-id="5b59d-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="5b59d-361">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-362">45</span><span class="sxs-lookup"><span data-stu-id="5b59d-362">45</span></span></td>
<td><span data-ttu-id="5b59d-363">未能注册和启动事件跟踪会话 [%1]。</span><span class="sxs-lookup"><span data-stu-id="5b59d-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="5b59d-364">错误代码：%2</span><span class="sxs-lookup"><span data-stu-id="5b59d-364">Error code: %2</span></span></td>
<td><span data-ttu-id="5b59d-365">创建 ETW 会话时，服务启动出错。</span><span class="sxs-lookup"><span data-stu-id="5b59d-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="5b59d-366">这导致了服务启动失败。</span><span class="sxs-lookup"><span data-stu-id="5b59d-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="5b59d-367">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="5b59d-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-368">46</span><span class="sxs-lookup"><span data-stu-id="5b59d-368">46</span></span></td>
<td><span data-ttu-id="5b59d-369">由于缺少资源，无法注册和启动事件跟踪会话 [%1]。</span><span class="sxs-lookup"><span data-stu-id="5b59d-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="5b59d-370">错误代码：%2。</span><span class="sxs-lookup"><span data-stu-id="5b59d-370">Error code: %2.</span></span> <span data-ttu-id="5b59d-371">这很可能是因为活动事件跟踪会话过多。</span><span class="sxs-lookup"><span data-stu-id="5b59d-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="5b59d-372">该服务将在 1 分钟内重试。</span><span class="sxs-lookup"><span data-stu-id="5b59d-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="5b59d-373">创建 ETW 会话时，服务启动出错，因为缺少资源。</span><span class="sxs-lookup"><span data-stu-id="5b59d-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="5b59d-374">该服务已启动且正在运行，但在启动 ETW 会话之前不会报告任何传感器事件。</span><span class="sxs-lookup"><span data-stu-id="5b59d-374">The service started and is running, but will not report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="5b59d-375">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="5b59d-376">该服务将尝试每分钟启动会话。</span><span class="sxs-lookup"><span data-stu-id="5b59d-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-377">47</span><span class="sxs-lookup"><span data-stu-id="5b59d-377">47</span></span></td>
<td><span data-ttu-id="5b59d-378">已成功注册并启动事件跟踪会话 - 在上一次尝试失败后恢复。</span><span class="sxs-lookup"><span data-stu-id="5b59d-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="5b59d-379">在成功启动 ETW 会话后，此事件跟在上一个事件之后。</span><span class="sxs-lookup"><span data-stu-id="5b59d-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="5b59d-380">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b59d-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5b59d-381">48</span><span class="sxs-lookup"><span data-stu-id="5b59d-381">48</span></span></td>
<td><span data-ttu-id="5b59d-382">未能将提供程序 [%1] 添加到事件跟踪会话 [%2]。</span><span class="sxs-lookup"><span data-stu-id="5b59d-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="5b59d-383">错误代码：%3。</span><span class="sxs-lookup"><span data-stu-id="5b59d-383">Error code: %3.</span></span> <span data-ttu-id="5b59d-384">这意味着不会报告来自此提供程序的事件。</span><span class="sxs-lookup"><span data-stu-id="5b59d-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="5b59d-385">未能将提供程序添加到 ETW 会话。</span><span class="sxs-lookup"><span data-stu-id="5b59d-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="5b59d-386">因此，不会报告提供程序事件。</span><span class="sxs-lookup"><span data-stu-id="5b59d-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="5b59d-387">检查错误代码。</span><span class="sxs-lookup"><span data-stu-id="5b59d-387">Check the error code.</span></span> <span data-ttu-id="5b59d-388">如果错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="5b59d-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
</tbody>
</table>

><span data-ttu-id="5b59d-389">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5b59d-389">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5b59d-390">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5b59d-390">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="5b59d-391">相关主题</span><span class="sxs-lookup"><span data-stu-id="5b59d-391">Related topics</span></span>
- [<span data-ttu-id="5b59d-392">载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="5b59d-392">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="5b59d-393">配置设备代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="5b59d-393">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="5b59d-394">Microsoft Defender for Endpoint 疑难解答</span><span class="sxs-lookup"><span data-stu-id="5b59d-394">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
