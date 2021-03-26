---
title: 使用事件查看器查看事件和错误
description: 获取说明和进一步疑难解答步骤 (如有必要) Microsoft Defender for Endpoint 服务报告的所有事件的说明。
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
ms.openlocfilehash: 1b8454107b6a2737f1236a066c3a24a2b9c776cb
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222645"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="c0126-104">使用事件查看器查看事件和错误</span><span class="sxs-lookup"><span data-stu-id="c0126-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c0126-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c0126-105">**Applies to:**</span></span>
- <span data-ttu-id="c0126-106">事件查看器</span><span class="sxs-lookup"><span data-stu-id="c0126-106">Event Viewer</span></span>
- [<span data-ttu-id="c0126-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c0126-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="c0126-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0126-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c0126-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c0126-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c0126-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c0126-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="c0126-111">可以在各个设备上的事件查看器 [中查看](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) 事件 ID。</span><span class="sxs-lookup"><span data-stu-id="c0126-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="c0126-112">例如，如果设备未显示在"设备"列表中，你可能需要在设备上查找事件 ID。</span><span class="sxs-lookup"><span data-stu-id="c0126-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="c0126-113">然后，可以使用此表确定进一步的疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="c0126-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="c0126-114">**打开事件查看器并查找 Microsoft Defender for Endpoint 服务事件日志：**</span><span class="sxs-lookup"><span data-stu-id="c0126-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="c0126-115">单击 **Windows** 菜单上的"开始"，键入 **"事件查看器"，** 然后按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="c0126-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="c0126-116">在日志列表中的"日志 **摘要"下**，滚动到看到 **"Microsoft-Windows-SENSE/Operational"。**</span><span class="sxs-lookup"><span data-stu-id="c0126-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="c0126-117">双击该项以打开日志。</span><span class="sxs-lookup"><span data-stu-id="c0126-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="c0126-118">a.</span><span class="sxs-lookup"><span data-stu-id="c0126-118">a.</span></span>  <span data-ttu-id="c0126-119">您还可以通过展开"应用程序和服务日志  >  **""Microsoft**  >  **Windows**  >  **SENSE"** 并单击"操作"来访问 **日志**。</span><span class="sxs-lookup"><span data-stu-id="c0126-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c0126-120">SENSE 是内部名称，用于引用支持 Microsoft Defender for Endpoint 的行为传感器。</span><span class="sxs-lookup"><span data-stu-id="c0126-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="c0126-121">服务记录的事件将显示在日志中。</span><span class="sxs-lookup"><span data-stu-id="c0126-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="c0126-122">有关服务记录的事件的列表，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c0126-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="c0126-123">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c0126-123">Event ID</span></span></th>
<th><span data-ttu-id="c0126-124">邮件</span><span class="sxs-lookup"><span data-stu-id="c0126-124">Message</span></span></th>
<th><span data-ttu-id="c0126-125">说明</span><span class="sxs-lookup"><span data-stu-id="c0126-125">Description</span></span></th>
<th><span data-ttu-id="c0126-126">操作</span><span class="sxs-lookup"><span data-stu-id="c0126-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="c0126-127">1</span><span class="sxs-lookup"><span data-stu-id="c0126-127">1</span></span></td>
<td><span data-ttu-id="c0126-128">Microsoft Defender for Endpoint 服务 (版本 <code>variable</code>) 。</span><span class="sxs-lookup"><span data-stu-id="c0126-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="c0126-129">在系统启动、关闭和载入期间发生。</span><span class="sxs-lookup"><span data-stu-id="c0126-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="c0126-130">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-131">2</span><span class="sxs-lookup"><span data-stu-id="c0126-131">2</span></span></td>
<td><span data-ttu-id="c0126-132">Microsoft Defender for Endpoint 服务关闭。</span><span class="sxs-lookup"><span data-stu-id="c0126-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="c0126-133">在设备关闭或载出时发生。</span><span class="sxs-lookup"><span data-stu-id="c0126-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="c0126-134">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-135">3</span><span class="sxs-lookup"><span data-stu-id="c0126-135">3</span></span></td>
<td><span data-ttu-id="c0126-136">Microsoft Defender for Endpoint 服务启动失败。</span><span class="sxs-lookup"><span data-stu-id="c0126-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="c0126-137">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-138">服务未启动。</span><span class="sxs-lookup"><span data-stu-id="c0126-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="c0126-139">查看其他消息以确定可能的原因和疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="c0126-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-140">4 </span><span class="sxs-lookup"><span data-stu-id="c0126-140">4</span></span></td>
<td><span data-ttu-id="c0126-141">Microsoft Defender for Endpoint 服务与 位于 的服务器联系 <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="c0126-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-142">变量 = 适用于终结点处理服务器的 Defender 的 URL。</span><span class="sxs-lookup"><span data-stu-id="c0126-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="c0126-143">此 URL 将匹配防火墙或网络活动中显示的内容。</span><span class="sxs-lookup"><span data-stu-id="c0126-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="c0126-144">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-145">5 </span><span class="sxs-lookup"><span data-stu-id="c0126-145">5</span></span></td>
<td><span data-ttu-id="c0126-146">Microsoft Defender for Endpoint 服务无法连接到 位于 的服务器 <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="c0126-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-147">变量 = 适用于终结点处理服务器的 Defender 的 URL。</span><span class="sxs-lookup"><span data-stu-id="c0126-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="c0126-148">该服务无法通过该 URL 与外部处理服务器联系。</span><span class="sxs-lookup"><span data-stu-id="c0126-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="c0126-149">检查与 URL 的连接。</span><span class="sxs-lookup"><span data-stu-id="c0126-149">Check the connection to the URL.</span></span> <span data-ttu-id="c0126-150">请参阅 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">配置代理和 Internet 连接</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-151">6 </span><span class="sxs-lookup"><span data-stu-id="c0126-151">6</span></span></td>
<td><span data-ttu-id="c0126-152">Microsoft Defender for Endpoint 服务未载入，并且未找到任何载入参数。</span><span class="sxs-lookup"><span data-stu-id="c0126-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="c0126-153">设备未正确载入，不会向门户报告。</span><span class="sxs-lookup"><span data-stu-id="c0126-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="c0126-154">在启动该服务之前，必须运行载入。</span><span class="sxs-lookup"><span data-stu-id="c0126-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="c0126-155">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="c0126-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="c0126-156">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="c0126-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="c0126-157">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-158">7 </span><span class="sxs-lookup"><span data-stu-id="c0126-158">7</span></span></td>
<td><span data-ttu-id="c0126-159">Microsoft Defender for Endpoint 服务无法读取载入参数。</span><span class="sxs-lookup"><span data-stu-id="c0126-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="c0126-160">失败 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-161">变量 = 详细的错误描述。</span><span class="sxs-lookup"><span data-stu-id="c0126-161">Variable = detailed error description.</span></span> <span data-ttu-id="c0126-162">设备未正确载入，不会向门户报告。</span><span class="sxs-lookup"><span data-stu-id="c0126-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="c0126-163">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="c0126-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="c0126-164">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="c0126-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="c0126-165">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-166">8 </span><span class="sxs-lookup"><span data-stu-id="c0126-166">8</span></span></td>
<td><span data-ttu-id="c0126-167">Microsoft Defender for Endpoint 服务无法清理其配置。</span><span class="sxs-lookup"><span data-stu-id="c0126-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="c0126-168">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-169"><b>载入期间：</b> 服务在载入期间未能清理其配置。</span><span class="sxs-lookup"><span data-stu-id="c0126-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="c0126-170">载入过程继续进行。</span><span class="sxs-lookup"><span data-stu-id="c0126-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="c0126-171"><b>在载出期间：</b> 该服务在载出过程中未能清理其配置。</span><span class="sxs-lookup"><span data-stu-id="c0126-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="c0126-172">载出过程已完成，但服务继续运行。</span><span class="sxs-lookup"><span data-stu-id="c0126-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="c0126-173"><b>载入：</b> 无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="c0126-174"><b>载出：</b> 重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="c0126-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="c0126-175">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-176">9 </span><span class="sxs-lookup"><span data-stu-id="c0126-176">9</span></span></td>
<td><span data-ttu-id="c0126-177">Microsoft Defender for Endpoint 服务未能更改其启动类型。</span><span class="sxs-lookup"><span data-stu-id="c0126-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="c0126-178">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-179"><b>载入期间：</b> 设备未正确载入，不会向门户报告。</span><span class="sxs-lookup"><span data-stu-id="c0126-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="c0126-180"><b>在载出期间：</b> 未能更改服务启动类型。</span><span class="sxs-lookup"><span data-stu-id="c0126-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="c0126-181">载出过程继续进行。</span><span class="sxs-lookup"><span data-stu-id="c0126-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="c0126-182">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="c0126-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="c0126-183">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="c0126-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="c0126-184">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-185">10  </span><span class="sxs-lookup"><span data-stu-id="c0126-185">10</span></span></td>
<td><span data-ttu-id="c0126-186">Microsoft Defender for Endpoint 服务无法保留载入信息。</span><span class="sxs-lookup"><span data-stu-id="c0126-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="c0126-187">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-188">设备未正确载入，不会向门户报告。</span><span class="sxs-lookup"><span data-stu-id="c0126-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="c0126-189">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="c0126-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="c0126-190">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="c0126-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="c0126-191">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-192">11</span><span class="sxs-lookup"><span data-stu-id="c0126-192">11</span></span></td>
<td><span data-ttu-id="c0126-193">已完成 Defender for Endpoint 服务的载入或重新载入。</span><span class="sxs-lookup"><span data-stu-id="c0126-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="c0126-194">设备已正确载入。</span><span class="sxs-lookup"><span data-stu-id="c0126-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="c0126-195">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="c0126-196">设备可能需要几个小时才能显示在门户中。</span><span class="sxs-lookup"><span data-stu-id="c0126-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-197">12 </span><span class="sxs-lookup"><span data-stu-id="c0126-197">12</span></span></td>
<td><span data-ttu-id="c0126-198">Microsoft Defender for Endpoint 无法应用默认配置。</span><span class="sxs-lookup"><span data-stu-id="c0126-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="c0126-199">服务无法应用默认配置。</span><span class="sxs-lookup"><span data-stu-id="c0126-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="c0126-200">此错误应在短时间内解决。</span><span class="sxs-lookup"><span data-stu-id="c0126-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-201">13</span><span class="sxs-lookup"><span data-stu-id="c0126-201">13</span></span></td>
<td><span data-ttu-id="c0126-202">计算得出的 Microsoft Defender for Endpoint 设备 <code>variable</code> ID：。</span><span class="sxs-lookup"><span data-stu-id="c0126-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-203">正常操作过程。</span><span class="sxs-lookup"><span data-stu-id="c0126-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="c0126-204">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-205">15 </span><span class="sxs-lookup"><span data-stu-id="c0126-205">15</span></span></td>
<td><span data-ttu-id="c0126-206">Microsoft Defender for Endpoint 无法使用 URL 启动命令通道 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-207">变量 = 适用于终结点处理服务器的 Defender 的 URL。</span><span class="sxs-lookup"><span data-stu-id="c0126-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="c0126-208">该服务无法通过该 URL 与外部处理服务器联系。</span><span class="sxs-lookup"><span data-stu-id="c0126-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="c0126-209">检查与 URL 的连接。</span><span class="sxs-lookup"><span data-stu-id="c0126-209">Check the connection to the URL.</span></span> <span data-ttu-id="c0126-210">请参阅 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">配置代理和 Internet 连接</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-211">17 </span><span class="sxs-lookup"><span data-stu-id="c0126-211">17</span></span></td>
<td><span data-ttu-id="c0126-212">Microsoft Defender for Endpoint 服务未能更改连接用户体验和遥测服务位置。</span><span class="sxs-lookup"><span data-stu-id="c0126-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="c0126-213">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-214">Windows 遥测服务出错。</span><span class="sxs-lookup"><span data-stu-id="c0126-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="c0126-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">确保诊断数据服务已启用</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="c0126-216">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="c0126-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="c0126-217">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="c0126-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="c0126-218">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-219">18 </span><span class="sxs-lookup"><span data-stu-id="c0126-219">18</span></span></td>
<td><span data-ttu-id="c0126-220">OOBE (Windows 欢迎) 已完成。</span><span class="sxs-lookup"><span data-stu-id="c0126-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="c0126-221">服务仅在任何 Windows 更新完成安装后启动。</span><span class="sxs-lookup"><span data-stu-id="c0126-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="c0126-222">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-223">19</span><span class="sxs-lookup"><span data-stu-id="c0126-223">19</span></span></td>
<td><span data-ttu-id="c0126-224">OOBE (Windows 欢迎) 尚未完成。</span><span class="sxs-lookup"><span data-stu-id="c0126-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="c0126-225">服务仅在任何 Windows 更新完成安装后启动。</span><span class="sxs-lookup"><span data-stu-id="c0126-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="c0126-226">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="c0126-227">如果在系统重新启动后此错误仍然存在，请确保所有 Windows 更新都已安装完整。</span><span class="sxs-lookup"><span data-stu-id="c0126-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-228">20</span><span class="sxs-lookup"><span data-stu-id="c0126-228">20</span></span></td>
<td><span data-ttu-id="c0126-229">无法等待 OOBE (Windows 欢迎) 完成。</span><span class="sxs-lookup"><span data-stu-id="c0126-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="c0126-230">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-231">内部错误。</span><span class="sxs-lookup"><span data-stu-id="c0126-231">Internal error.</span></span></td>
<td><span data-ttu-id="c0126-232">如果在系统重新启动后此错误仍然存在，请确保所有 Windows 更新都已安装完整。</span><span class="sxs-lookup"><span data-stu-id="c0126-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-233">25</span><span class="sxs-lookup"><span data-stu-id="c0126-233">25</span></span></td>
<td><span data-ttu-id="c0126-234">Microsoft Defender for Endpoint 服务无法重置注册表中的运行状况状态。</span><span class="sxs-lookup"><span data-stu-id="c0126-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="c0126-235">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-236">设备未正确载入。</span><span class="sxs-lookup"><span data-stu-id="c0126-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="c0126-237">它将报告给门户，但该服务可能不会显示为在 SCCM 或注册表中注册。</span><span class="sxs-lookup"><span data-stu-id="c0126-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="c0126-238">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="c0126-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="c0126-239">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="c0126-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="c0126-240">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-241">26</span><span class="sxs-lookup"><span data-stu-id="c0126-241">26</span></span></td>
<td><span data-ttu-id="c0126-242">Microsoft Defender for Endpoint 服务未能在注册表中设置载入状态。</span><span class="sxs-lookup"><span data-stu-id="c0126-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="c0126-243">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-244">设备未正确载入。</span><span class="sxs-lookup"><span data-stu-id="c0126-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="c0126-245">它将报告给门户，但该服务可能不会显示为在 SCCM 或注册表中注册。</span><span class="sxs-lookup"><span data-stu-id="c0126-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="c0126-246">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="c0126-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="c0126-247">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="c0126-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="c0126-248">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-249">27</span><span class="sxs-lookup"><span data-stu-id="c0126-249">27</span></span></td>
<td><span data-ttu-id="c0126-250">Microsoft Defender for Endpoint 服务未能在 Microsoft Defender 防病毒中启用 SENSE 感知模式。</span><span class="sxs-lookup"><span data-stu-id="c0126-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="c0126-251">载入过程失败。</span><span class="sxs-lookup"><span data-stu-id="c0126-251">Onboarding process failed.</span></span> <span data-ttu-id="c0126-252">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-253">通常情况下，如果另一个实时反恶意软件产品正在设备上正常运行，并且设备向 Defender for Endpoint 报告，Microsoft Defender 防病毒将进入特殊的被动状态。</span><span class="sxs-lookup"><span data-stu-id="c0126-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="c0126-254">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="c0126-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="c0126-255">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="c0126-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="c0126-256">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="c0126-257">确保实时反恶意软件保护运行正常。</span><span class="sxs-lookup"><span data-stu-id="c0126-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-258">28</span><span class="sxs-lookup"><span data-stu-id="c0126-258">28</span></span></td>
<td><span data-ttu-id="c0126-259">Microsoft Defender 终结点连接用户体验和遥测服务注册失败。</span><span class="sxs-lookup"><span data-stu-id="c0126-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="c0126-260">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-261">Windows 遥测服务出错。</span><span class="sxs-lookup"><span data-stu-id="c0126-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="c0126-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">确保诊断数据服务已启用</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="c0126-263">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="c0126-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="c0126-264">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="c0126-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="c0126-265">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-266">29</span><span class="sxs-lookup"><span data-stu-id="c0126-266">29</span></span></td>
<td><span data-ttu-id="c0126-267">未能读取 offboarding参数。</span><span class="sxs-lookup"><span data-stu-id="c0126-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="c0126-268">错误类型：%1，错误代码：%2，说明：%3</span><span class="sxs-lookup"><span data-stu-id="c0126-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="c0126-269">当系统无法读取&#39;时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="c0126-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="c0126-270">确保设备可以访问 Internet，然后再次运行整个载出过程。</span><span class="sxs-lookup"><span data-stu-id="c0126-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="c0126-271">确保载出包尚未过期。</span><span class="sxs-lookup"><span data-stu-id="c0126-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-272">30</span><span class="sxs-lookup"><span data-stu-id="c0126-272">30</span></span></td>
<td><span data-ttu-id="c0126-273">Microsoft Defender for Endpoint 服务在 Microsoft Defender 防病毒中未能禁用 SENSE 感知模式。</span><span class="sxs-lookup"><span data-stu-id="c0126-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="c0126-274">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-275">通常情况下，如果另一个实时反恶意软件产品正在设备上正常运行，并且设备向 Defender for Endpoint 报告，Microsoft Defender 防病毒将进入特殊的被动状态。</span><span class="sxs-lookup"><span data-stu-id="c0126-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="c0126-276">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="c0126-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="c0126-277">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="c0126-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="c0126-278">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a></span><span class="sxs-lookup"><span data-stu-id="c0126-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="c0126-279">确保实时反恶意软件保护运行正常。</span><span class="sxs-lookup"><span data-stu-id="c0126-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-280">31</span><span class="sxs-lookup"><span data-stu-id="c0126-280">31</span></span></td>
<td><span data-ttu-id="c0126-281">Microsoft Defender 终结点连接用户体验和遥测服务注销失败。</span><span class="sxs-lookup"><span data-stu-id="c0126-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="c0126-282">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-283">载入期间 Windows 遥测服务出错。</span><span class="sxs-lookup"><span data-stu-id="c0126-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="c0126-284">载出过程继续进行。</span><span class="sxs-lookup"><span data-stu-id="c0126-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="c0126-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">检查 Windows 遥测服务的错误</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-286">32</span><span class="sxs-lookup"><span data-stu-id="c0126-286">32</span></span></td>
<td><span data-ttu-id="c0126-287">Microsoft Defender for Endpoint 服务在离开进程后无法请求自行停止。</span><span class="sxs-lookup"><span data-stu-id="c0126-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="c0126-288">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="c0126-289">在载出期间出错。</span><span class="sxs-lookup"><span data-stu-id="c0126-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="c0126-290">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="c0126-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-291">33</span><span class="sxs-lookup"><span data-stu-id="c0126-291">33</span></span></td>
<td><span data-ttu-id="c0126-292">Microsoft Defender for Endpoint 服务无法保留 SENSE GUID。</span><span class="sxs-lookup"><span data-stu-id="c0126-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="c0126-293">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-294">唯一标识符用于表示向门户报告的每个设备。</span><span class="sxs-lookup"><span data-stu-id="c0126-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="c0126-295">如果标识符未保留，同一设备可能在门户中出现两次。</span><span class="sxs-lookup"><span data-stu-id="c0126-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="c0126-296">检查设备的注册表权限，以确保服务可以更新注册表。</span><span class="sxs-lookup"><span data-stu-id="c0126-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-297">34</span><span class="sxs-lookup"><span data-stu-id="c0126-297">34</span></span></td>
<td><span data-ttu-id="c0126-298">Microsoft Defender for Endpoint 服务无法将自身添加为连接用户体验和遥测服务的依赖项，从而导致载入过程失败。</span><span class="sxs-lookup"><span data-stu-id="c0126-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="c0126-299">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-300">Windows 遥测服务出错。</span><span class="sxs-lookup"><span data-stu-id="c0126-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="c0126-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">确保诊断数据服务已启用</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="c0126-302">检查载入设置和脚本是否正确部署。</span><span class="sxs-lookup"><span data-stu-id="c0126-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="c0126-303">尝试重新部署配置包。</span><span class="sxs-lookup"><span data-stu-id="c0126-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="c0126-304">请参阅 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">载入 Windows 10 设备</a>。</span><span class="sxs-lookup"><span data-stu-id="c0126-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-305">35</span><span class="sxs-lookup"><span data-stu-id="c0126-305">35</span></span></td>
<td><span data-ttu-id="c0126-306">Microsoft Defender for Endpoint 服务无法删除自身作为连接用户体验和遥测服务的依赖项。</span><span class="sxs-lookup"><span data-stu-id="c0126-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="c0126-307">失败代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-308">在载出期间 Windows 遥测服务出错。</span><span class="sxs-lookup"><span data-stu-id="c0126-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="c0126-309">载出过程继续进行。</span><span class="sxs-lookup"><span data-stu-id="c0126-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="c0126-310">检查 Windows 诊断数据服务的错误。</span><span class="sxs-lookup"><span data-stu-id="c0126-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-311">36</span><span class="sxs-lookup"><span data-stu-id="c0126-311">36</span></span></td>
<td><span data-ttu-id="c0126-312">Microsoft Defender 终结点连接用户体验和遥测服务注册成功。</span><span class="sxs-lookup"><span data-stu-id="c0126-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="c0126-313">完成代码 <code>variable</code> ：。</span><span class="sxs-lookup"><span data-stu-id="c0126-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="c0126-314">为终结点注册已成功完成连接用户体验和遥测服务的 Defender。</span><span class="sxs-lookup"><span data-stu-id="c0126-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="c0126-315">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-316">37</span><span class="sxs-lookup"><span data-stu-id="c0126-316">37</span></span></td>
<td><span data-ttu-id="c0126-317">Microsoft Defender for Endpoint A 模块即将超过其配额。</span><span class="sxs-lookup"><span data-stu-id="c0126-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="c0126-318">模块：%1，配额：{%2} {%3}，配额使用率百分比：%4。</span><span class="sxs-lookup"><span data-stu-id="c0126-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="c0126-319">设备几乎已使用当前 24 小时时段的已分配配额。</span><span class="sxs-lookup"><span data-stu-id="c0126-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="c0126-320">即将被限制。</span><span class="sxs-lookup"><span data-stu-id="c0126-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="c0126-321">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-322">38</span><span class="sxs-lookup"><span data-stu-id="c0126-322">38</span></span></td>
<td><span data-ttu-id="c0126-323">网络连接标识为低。</span><span class="sxs-lookup"><span data-stu-id="c0126-323">Network connection is identified as low.</span></span> <span data-ttu-id="c0126-324">Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。</span><span class="sxs-lookup"><span data-stu-id="c0126-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="c0126-325">按流量计费的连接：%2，Internet 可用：%3，可用网络：%4。</span><span class="sxs-lookup"><span data-stu-id="c0126-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="c0126-326">设备使用按流量计费/付费网络，并且与服务器联系的频率将较低。</span><span class="sxs-lookup"><span data-stu-id="c0126-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="c0126-327">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-328">39</span><span class="sxs-lookup"><span data-stu-id="c0126-328">39</span></span></td>
<td><span data-ttu-id="c0126-329">网络连接被标识为正常连接。</span><span class="sxs-lookup"><span data-stu-id="c0126-329">Network connection is identified as normal.</span></span> <span data-ttu-id="c0126-330">Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。</span><span class="sxs-lookup"><span data-stu-id="c0126-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="c0126-331">按流量计费的连接：%2，Internet 可用：%3，可用网络：%4。</span><span class="sxs-lookup"><span data-stu-id="c0126-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="c0126-332">设备没有使用按流量计费/付费的连接，将照常与服务器联系。</span><span class="sxs-lookup"><span data-stu-id="c0126-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="c0126-333">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-334">40</span><span class="sxs-lookup"><span data-stu-id="c0126-334">40</span></span></td>
<td><span data-ttu-id="c0126-335">电池状态标识为低。</span><span class="sxs-lookup"><span data-stu-id="c0126-335">Battery state is identified as low.</span></span> <span data-ttu-id="c0126-336">Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。</span><span class="sxs-lookup"><span data-stu-id="c0126-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="c0126-337">电池状态：%2。</span><span class="sxs-lookup"><span data-stu-id="c0126-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="c0126-338">设备具有低电池电量，并且与服务器的联系频率较低。</span><span class="sxs-lookup"><span data-stu-id="c0126-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="c0126-339">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-340">41</span><span class="sxs-lookup"><span data-stu-id="c0126-340">41</span></span></td>
<td><span data-ttu-id="c0126-341">电池状态标识为正常。</span><span class="sxs-lookup"><span data-stu-id="c0126-341">Battery state is identified as normal.</span></span> <span data-ttu-id="c0126-342">Microsoft Defender for Endpoint 将每 %1 分钟与服务器联系一次。</span><span class="sxs-lookup"><span data-stu-id="c0126-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="c0126-343">电池状态：%2。</span><span class="sxs-lookup"><span data-stu-id="c0126-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="c0126-344">设备没有低电池电量，将照常与服务器联系。</span><span class="sxs-lookup"><span data-stu-id="c0126-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="c0126-345">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-346">42</span><span class="sxs-lookup"><span data-stu-id="c0126-346">42</span></span></td>
<td><span data-ttu-id="c0126-347">Microsoft Defender for Endpoint WDATP 组件无法执行该操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-347">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="c0126-348">组件：%1，操作：%2，异常类型：%3，异常消息：%4</span><span class="sxs-lookup"><span data-stu-id="c0126-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="c0126-349">内部错误。</span><span class="sxs-lookup"><span data-stu-id="c0126-349">Internal error.</span></span> <span data-ttu-id="c0126-350">服务启动失败。</span><span class="sxs-lookup"><span data-stu-id="c0126-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="c0126-351">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-352">43</span><span class="sxs-lookup"><span data-stu-id="c0126-352">43</span></span></td>
<td><span data-ttu-id="c0126-353">Microsoft Defender for Endpoint WDATP 组件无法执行该操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-353">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="c0126-354">组件：%1，操作：%2，异常类型：%3，异常错误：%4，异常消息：%5</span><span class="sxs-lookup"><span data-stu-id="c0126-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="c0126-355">内部错误。</span><span class="sxs-lookup"><span data-stu-id="c0126-355">Internal error.</span></span> <span data-ttu-id="c0126-356">服务启动失败。</span><span class="sxs-lookup"><span data-stu-id="c0126-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="c0126-357">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-358">44</span><span class="sxs-lookup"><span data-stu-id="c0126-358">44</span></span></td>
<td><span data-ttu-id="c0126-359">已完成 Defender for Endpoint Service 的载出。</span><span class="sxs-lookup"><span data-stu-id="c0126-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="c0126-360">服务已载出。</span><span class="sxs-lookup"><span data-stu-id="c0126-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="c0126-361">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-362">45</span><span class="sxs-lookup"><span data-stu-id="c0126-362">45</span></span></td>
<td><span data-ttu-id="c0126-363">未能注册和启动事件跟踪会话 [%1]。</span><span class="sxs-lookup"><span data-stu-id="c0126-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="c0126-364">错误代码：%2</span><span class="sxs-lookup"><span data-stu-id="c0126-364">Error code: %2</span></span></td>
<td><span data-ttu-id="c0126-365">创建 ETW 会话时，服务启动出错。</span><span class="sxs-lookup"><span data-stu-id="c0126-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="c0126-366">这导致了服务启动失败。</span><span class="sxs-lookup"><span data-stu-id="c0126-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="c0126-367">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-368">46</span><span class="sxs-lookup"><span data-stu-id="c0126-368">46</span></span></td>
<td><span data-ttu-id="c0126-369">由于缺少资源，无法注册和启动事件跟踪会话 [%1]。</span><span class="sxs-lookup"><span data-stu-id="c0126-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="c0126-370">错误代码：%2。</span><span class="sxs-lookup"><span data-stu-id="c0126-370">Error code: %2.</span></span> <span data-ttu-id="c0126-371">这很可能是因为活动事件跟踪会话过多。</span><span class="sxs-lookup"><span data-stu-id="c0126-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="c0126-372">该服务将在 1 分钟内重试。</span><span class="sxs-lookup"><span data-stu-id="c0126-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="c0126-373">创建 ETW 会话时，服务启动出错，因为缺少资源。</span><span class="sxs-lookup"><span data-stu-id="c0126-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="c0126-374">该服务已启动且正在运行，但在启动 ETW 会话之前不会报告任何传感器事件。</span><span class="sxs-lookup"><span data-stu-id="c0126-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="c0126-375">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="c0126-376">该服务将尝试每分钟启动会话。</span><span class="sxs-lookup"><span data-stu-id="c0126-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-377">47</span><span class="sxs-lookup"><span data-stu-id="c0126-377">47</span></span></td>
<td><span data-ttu-id="c0126-378">已成功注册并启动事件跟踪会话 - 在上一次尝试失败后恢复。</span><span class="sxs-lookup"><span data-stu-id="c0126-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="c0126-379">在成功启动 ETW 会话后，此事件跟在上一个事件之后。</span><span class="sxs-lookup"><span data-stu-id="c0126-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="c0126-380">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0126-381">48</span><span class="sxs-lookup"><span data-stu-id="c0126-381">48</span></span></td>
<td><span data-ttu-id="c0126-382">未能将提供程序 [%1] 添加到事件跟踪会话 [%2]。</span><span class="sxs-lookup"><span data-stu-id="c0126-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="c0126-383">错误代码：%3。</span><span class="sxs-lookup"><span data-stu-id="c0126-383">Error code: %3.</span></span> <span data-ttu-id="c0126-384">这意味着不会报告来自此提供程序的事件。</span><span class="sxs-lookup"><span data-stu-id="c0126-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="c0126-385">未能将提供程序添加到 ETW 会话。</span><span class="sxs-lookup"><span data-stu-id="c0126-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="c0126-386">因此，不会报告提供程序事件。</span><span class="sxs-lookup"><span data-stu-id="c0126-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="c0126-387">检查错误代码。</span><span class="sxs-lookup"><span data-stu-id="c0126-387">Check the error code.</span></span> <span data-ttu-id="c0126-388">如果错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="c0126-389">49</span><span class="sxs-lookup"><span data-stu-id="c0126-389">49</span></span></td>
   <td><span data-ttu-id="c0126-390">收到并忽略无效的云配置命令。</span><span class="sxs-lookup"><span data-stu-id="c0126-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="c0126-391">版本：%1，状态：%2，错误代码：%3，消息：%4</span><span class="sxs-lookup"><span data-stu-id="c0126-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="c0126-392">从已忽略的云服务收到无效的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c0126-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="c0126-393">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-394">50</span><span class="sxs-lookup"><span data-stu-id="c0126-394">50</span></span></td>
   <td><span data-ttu-id="c0126-395">已成功应用新的云配置。</span><span class="sxs-lookup"><span data-stu-id="c0126-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="c0126-396">版本：%1。</span><span class="sxs-lookup"><span data-stu-id="c0126-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="c0126-397">已成功应用云服务中的新配置。</span><span class="sxs-lookup"><span data-stu-id="c0126-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="c0126-398">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-399">51</span><span class="sxs-lookup"><span data-stu-id="c0126-399">51</span></span></td>
   <td><span data-ttu-id="c0126-400">新云配置应用失败，版本：%1。</span><span class="sxs-lookup"><span data-stu-id="c0126-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="c0126-401">已成功应用上一个已知良好的配置版本 %2。</span><span class="sxs-lookup"><span data-stu-id="c0126-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="c0126-402">从云服务收到错误配置文件。</span><span class="sxs-lookup"><span data-stu-id="c0126-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="c0126-403">已成功应用上一个已知良好的配置。</span><span class="sxs-lookup"><span data-stu-id="c0126-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="c0126-404">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-405">52</span><span class="sxs-lookup"><span data-stu-id="c0126-405">52</span></span></td>
   <td><span data-ttu-id="c0126-406">新云配置应用失败，版本：%1。</span><span class="sxs-lookup"><span data-stu-id="c0126-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="c0126-407">还未能应用上一个已知良好的配置版本 %2。</span><span class="sxs-lookup"><span data-stu-id="c0126-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="c0126-408">已成功应用默认配置。</span><span class="sxs-lookup"><span data-stu-id="c0126-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="c0126-409">从云服务收到错误配置文件。</span><span class="sxs-lookup"><span data-stu-id="c0126-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="c0126-410">未能应用上一个已知的良好配置，并且应用了默认配置。</span><span class="sxs-lookup"><span data-stu-id="c0126-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="c0126-411">该服务将尝试在 5 分钟内下载新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c0126-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="c0126-412">如果看不到事件或#50联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-413">53</span><span class="sxs-lookup"><span data-stu-id="c0126-413">53</span></span></td>
   <td><span data-ttu-id="c0126-414">从持久性存储加载的云配置，版本：%1。</span><span class="sxs-lookup"><span data-stu-id="c0126-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="c0126-415">配置是在服务启动时从永久性存储加载的。</span><span class="sxs-lookup"><span data-stu-id="c0126-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="c0126-416">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-417">55</span><span class="sxs-lookup"><span data-stu-id="c0126-417">55</span></span></td>
   <td><span data-ttu-id="c0126-418">未能创建安全 ETW 自动记录器。</span><span class="sxs-lookup"><span data-stu-id="c0126-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="c0126-419">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="c0126-420">未能创建安全的 ETW 记录器。</span><span class="sxs-lookup"><span data-stu-id="c0126-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="c0126-421">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="c0126-421">Reboot the device.</span></span> <span data-ttu-id="c0126-422">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-423">56</span><span class="sxs-lookup"><span data-stu-id="c0126-423">56</span></span></td>
   <td><span data-ttu-id="c0126-424">未能删除安全 ETW 自动记录器。</span><span class="sxs-lookup"><span data-stu-id="c0126-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="c0126-425">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="c0126-426">在载出时未能删除安全 ETW 会话。</span><span class="sxs-lookup"><span data-stu-id="c0126-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="c0126-427">联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-428">57</span><span class="sxs-lookup"><span data-stu-id="c0126-428">57</span></span></td>
   <td><span data-ttu-id="c0126-429">捕获计算机快照以进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="c0126-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="c0126-430">正在收集调查包（也称为取证包）。</span><span class="sxs-lookup"><span data-stu-id="c0126-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="c0126-431">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-432">59</span><span class="sxs-lookup"><span data-stu-id="c0126-432">59</span></span></td>
   <td><span data-ttu-id="c0126-433">启动命令：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="c0126-434">开始执行响应命令。</span><span class="sxs-lookup"><span data-stu-id="c0126-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="c0126-435">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-436">60</span><span class="sxs-lookup"><span data-stu-id="c0126-436">60</span></span></td>
   <td><span data-ttu-id="c0126-437">未能运行命令 %1，错误：%2。</span><span class="sxs-lookup"><span data-stu-id="c0126-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="c0126-438">未能执行响应命令。</span><span class="sxs-lookup"><span data-stu-id="c0126-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="c0126-439">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-440">61</span><span class="sxs-lookup"><span data-stu-id="c0126-440">61</span></span></td>
   <td><span data-ttu-id="c0126-441">数据收集命令参数无效：SasUri：%1，compressionLevel：%2。</span><span class="sxs-lookup"><span data-stu-id="c0126-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="c0126-442">无法读取或分析数据集合命令参数， (参数) 。</span><span class="sxs-lookup"><span data-stu-id="c0126-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="c0126-443">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-444">62</span><span class="sxs-lookup"><span data-stu-id="c0126-444">62</span></span></td>
   <td><span data-ttu-id="c0126-445">无法启动连接用户体验和遥测服务。</span><span class="sxs-lookup"><span data-stu-id="c0126-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="c0126-446">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="c0126-447">diagtrack 服务 (连接用户体验) 遥测服务失败。</span><span class="sxs-lookup"><span data-stu-id="c0126-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="c0126-448">不会从此计算机发送非 Microsoft Defender for Endpoint 遥测。</span><span class="sxs-lookup"><span data-stu-id="c0126-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="c0126-449">在事件日志中查找更多疑难解答提示：Microsoft-Windows-UniversalTelemetryClient/Operational。</span><span class="sxs-lookup"><span data-stu-id="c0126-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-450">63</span><span class="sxs-lookup"><span data-stu-id="c0126-450">63</span></span></td>
   <td><span data-ttu-id="c0126-451">更新外部服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="c0126-451">Updating the start type of external service.</span></span> <span data-ttu-id="c0126-452">名称：%1，实际开始类型：%2，预期开始类型：%3，退出代码：%4</span><span class="sxs-lookup"><span data-stu-id="c0126-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="c0126-453">更新了外部服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="c0126-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="c0126-454">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-455">64</span><span class="sxs-lookup"><span data-stu-id="c0126-455">64</span></span></td>
   <td><span data-ttu-id="c0126-456">启动已停止的外部服务。</span><span class="sxs-lookup"><span data-stu-id="c0126-456">Starting stopped external service.</span></span> <span data-ttu-id="c0126-457">名称：%1，退出代码：%2</span><span class="sxs-lookup"><span data-stu-id="c0126-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="c0126-458">启动外部服务。</span><span class="sxs-lookup"><span data-stu-id="c0126-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="c0126-459">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-460">65</span><span class="sxs-lookup"><span data-stu-id="c0126-460">65</span></span></td>
   <td><span data-ttu-id="c0126-461">未能加载 Microsoft 安全事件组件微筛选器驱动程序。</span><span class="sxs-lookup"><span data-stu-id="c0126-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="c0126-462">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="c0126-463">未能加载MsSecFlt.sys微筛选器。</span><span class="sxs-lookup"><span data-stu-id="c0126-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="c0126-464">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="c0126-464">Reboot the device.</span></span> <span data-ttu-id="c0126-465">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-466">66</span><span class="sxs-lookup"><span data-stu-id="c0126-466">66</span></span></td>
   <td><span data-ttu-id="c0126-467">策略更新：延迟模式 - %1</span><span class="sxs-lookup"><span data-stu-id="c0126-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="c0126-468">更新C&C 连接频率策略。</span><span class="sxs-lookup"><span data-stu-id="c0126-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="c0126-469">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-470">68</span><span class="sxs-lookup"><span data-stu-id="c0126-470">68</span></span></td>
   <td><span data-ttu-id="c0126-471">服务的启动类型是意外的。</span><span class="sxs-lookup"><span data-stu-id="c0126-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="c0126-472">服务名称：%1，实际启动类型：%2，预期启动类型：%3</span><span class="sxs-lookup"><span data-stu-id="c0126-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="c0126-473">意外的外部服务启动类型。</span><span class="sxs-lookup"><span data-stu-id="c0126-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="c0126-474">修复外部服务启动类型。</span><span class="sxs-lookup"><span data-stu-id="c0126-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-475">69</span><span class="sxs-lookup"><span data-stu-id="c0126-475">69</span></span></td>
   <td><span data-ttu-id="c0126-476">服务已停止。</span><span class="sxs-lookup"><span data-stu-id="c0126-476">The service is stopped.</span></span> <span data-ttu-id="c0126-477">服务名称：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="c0126-478">外部服务已停止。</span><span class="sxs-lookup"><span data-stu-id="c0126-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="c0126-479">启动外部服务。</span><span class="sxs-lookup"><span data-stu-id="c0126-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-480">70</span><span class="sxs-lookup"><span data-stu-id="c0126-480">70</span></span></td>
   <td><span data-ttu-id="c0126-481">策略更新：允许示例集合 - %1</span><span class="sxs-lookup"><span data-stu-id="c0126-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="c0126-482">示例集合策略已更新。</span><span class="sxs-lookup"><span data-stu-id="c0126-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="c0126-483">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-484">71</span><span class="sxs-lookup"><span data-stu-id="c0126-484">71</span></span></td>
   <td><span data-ttu-id="c0126-485">成功运行命令：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="c0126-486">命令已成功执行。</span><span class="sxs-lookup"><span data-stu-id="c0126-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="c0126-487">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-488">72</span><span class="sxs-lookup"><span data-stu-id="c0126-488">72</span></span></td>
   <td><span data-ttu-id="c0126-489">尝试发送第一个完整的计算机配置文件报告。</span><span class="sxs-lookup"><span data-stu-id="c0126-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="c0126-490">结果代码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="c0126-491">仅供参考。</span><span class="sxs-lookup"><span data-stu-id="c0126-491">Informational only.</span></span></td>
   <td><span data-ttu-id="c0126-492">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-493">73</span><span class="sxs-lookup"><span data-stu-id="c0126-493">73</span></span></td>
   <td><span data-ttu-id="c0126-494">从平台开始感知：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="c0126-495">仅供参考。</span><span class="sxs-lookup"><span data-stu-id="c0126-495">Informational only.</span></span></td>
   <td><span data-ttu-id="c0126-496">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-497">74</span><span class="sxs-lookup"><span data-stu-id="c0126-497">74</span></span></td>
   <td><span data-ttu-id="c0126-498">注册表中的设备标记超出长度限制。</span><span class="sxs-lookup"><span data-stu-id="c0126-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="c0126-499">标记名称：%2。</span><span class="sxs-lookup"><span data-stu-id="c0126-499">Tag name: %2.</span></span> <span data-ttu-id="c0126-500">长度限制：%1。</span><span class="sxs-lookup"><span data-stu-id="c0126-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="c0126-501">设备标记超出长度限制。</span><span class="sxs-lookup"><span data-stu-id="c0126-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="c0126-502">使用较短的设备标记。</span><span class="sxs-lookup"><span data-stu-id="c0126-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-503">81</span><span class="sxs-lookup"><span data-stu-id="c0126-503">81</span></span></td>
   <td><span data-ttu-id="c0126-504">创建高级威胁Windows Defender ETW 自动记录器失败。</span><span class="sxs-lookup"><span data-stu-id="c0126-504">Failed to create Windows Defender Advanced Threat Protection ETW autologger.</span></span> <span data-ttu-id="c0126-505">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="c0126-506">未能创建 ETW 会话。</span><span class="sxs-lookup"><span data-stu-id="c0126-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="c0126-507">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="c0126-507">Reboot the device.</span></span> <span data-ttu-id="c0126-508">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-509">82</span><span class="sxs-lookup"><span data-stu-id="c0126-509">82</span></span></td>
   <td><span data-ttu-id="c0126-510">无法删除高级Windows Defender ETW 自动记录器。</span><span class="sxs-lookup"><span data-stu-id="c0126-510">Failed to remove Windows Defender Advanced Threat Protection ETW autologger.</span></span> <span data-ttu-id="c0126-511">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="c0126-512">未能删除 ETW 会话。</span><span class="sxs-lookup"><span data-stu-id="c0126-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="c0126-513">联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-514">84</span><span class="sxs-lookup"><span data-stu-id="c0126-514">84</span></span></td>
   <td><span data-ttu-id="c0126-515">设置Windows Defender防病毒运行模式。</span><span class="sxs-lookup"><span data-stu-id="c0126-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="c0126-516">强制被动模式：%1，结果代码：%2。</span><span class="sxs-lookup"><span data-stu-id="c0126-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="c0126-517">将 defender 运行模式设置为 (或被动) 。</span><span class="sxs-lookup"><span data-stu-id="c0126-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="c0126-518">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-519">85</span><span class="sxs-lookup"><span data-stu-id="c0126-519">85</span></span></td>
   <td><span data-ttu-id="c0126-520">无法触发高级Windows Defender高级威胁防护可执行文件。</span><span class="sxs-lookup"><span data-stu-id="c0126-520">Failed to trigger Windows Defender Advanced Threat Protection executable.</span></span> <span data-ttu-id="c0126-521">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="c0126-522">Starring SenseIR 可执行文件失败。</span><span class="sxs-lookup"><span data-stu-id="c0126-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="c0126-523">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="c0126-523">Reboot the device.</span></span> <span data-ttu-id="c0126-524">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-525">86</span><span class="sxs-lookup"><span data-stu-id="c0126-525">86</span></span></td>
   <td><span data-ttu-id="c0126-526">再次启动已停止应启动的外部服务。</span><span class="sxs-lookup"><span data-stu-id="c0126-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="c0126-527">名称：%1，退出代码：%2</span><span class="sxs-lookup"><span data-stu-id="c0126-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="c0126-528">再次启动外部服务。</span><span class="sxs-lookup"><span data-stu-id="c0126-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="c0126-529">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-530">87</span><span class="sxs-lookup"><span data-stu-id="c0126-530">87</span></span></td>
   <td><span data-ttu-id="c0126-531">无法启动外部服务。</span><span class="sxs-lookup"><span data-stu-id="c0126-531">Cannot start the external service.</span></span> <span data-ttu-id="c0126-532">名称：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-532">Name: %1</span></span></td>
   <td><span data-ttu-id="c0126-533">无法启动外部服务。</span><span class="sxs-lookup"><span data-stu-id="c0126-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="c0126-534">联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-535">88</span><span class="sxs-lookup"><span data-stu-id="c0126-535">88</span></span></td>
   <td><span data-ttu-id="c0126-536">再次更新外部服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="c0126-536">Updating the start type of external service again.</span></span> <span data-ttu-id="c0126-537">名称：%1，实际开始类型：%2，预期开始类型：%3，退出代码：%4</span><span class="sxs-lookup"><span data-stu-id="c0126-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="c0126-538">更新了外部服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="c0126-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="c0126-539">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-540">89</span><span class="sxs-lookup"><span data-stu-id="c0126-540">89</span></span></td>
   <td><span data-ttu-id="c0126-541">无法更新外部服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="c0126-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="c0126-542">名称：%1，实际开始类型：%2，预期开始类型：%3</span><span class="sxs-lookup"><span data-stu-id="c0126-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="c0126-543">无法更新外部服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="c0126-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="c0126-544">联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-545">90</span><span class="sxs-lookup"><span data-stu-id="c0126-545">90</span></span></td>
   <td><span data-ttu-id="c0126-546">未能将 System Guard 运行时监视器配置为连接到地理位置 %1 中的云服务。</span><span class="sxs-lookup"><span data-stu-id="c0126-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="c0126-547">失败代码：%2</span><span class="sxs-lookup"><span data-stu-id="c0126-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="c0126-548">System Guard 运行时监视器不会向云服务发送证明数据。</span><span class="sxs-lookup"><span data-stu-id="c0126-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="c0126-549">检查注册路径上的权限："HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。</span><span class="sxs-lookup"><span data-stu-id="c0126-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="c0126-550">如果没有问题，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-551">91</span><span class="sxs-lookup"><span data-stu-id="c0126-551">91</span></span></td>
   <td><span data-ttu-id="c0126-552">未能删除 System Guard 运行时监视器地理位置信息。</span><span class="sxs-lookup"><span data-stu-id="c0126-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="c0126-553">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="c0126-554">System Guard 运行时监视器不会向云服务发送证明数据。</span><span class="sxs-lookup"><span data-stu-id="c0126-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="c0126-555">检查注册路径上的权限："HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。</span><span class="sxs-lookup"><span data-stu-id="c0126-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="c0126-556">如果没有问题，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-557">92</span><span class="sxs-lookup"><span data-stu-id="c0126-557">92</span></span></td>
   <td><span data-ttu-id="c0126-558">由于超过数据配额，停止发送传感器网络数据配额。</span><span class="sxs-lookup"><span data-stu-id="c0126-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="c0126-559">配额期通过后，将恢复发送。</span><span class="sxs-lookup"><span data-stu-id="c0126-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="c0126-560">状态掩码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="c0126-561">超过限制。</span><span class="sxs-lookup"><span data-stu-id="c0126-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="c0126-562">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-563">93</span><span class="sxs-lookup"><span data-stu-id="c0126-563">93</span></span></td>
   <td><span data-ttu-id="c0126-564">恢复发送传感器网络数据。</span><span class="sxs-lookup"><span data-stu-id="c0126-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="c0126-565">状态掩码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="c0126-566">恢复网络数据提交。</span><span class="sxs-lookup"><span data-stu-id="c0126-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="c0126-567">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-568">94</span><span class="sxs-lookup"><span data-stu-id="c0126-568">94</span></span></td>
   <td><span data-ttu-id="c0126-569">Windows Defender高级威胁防护可执行文件已启动</span><span class="sxs-lookup"><span data-stu-id="c0126-569">Windows Defender Advanced Threat Protection executable has started</span></span></td>
   <td><span data-ttu-id="c0126-570">SenseCE 可执行文件已启动。</span><span class="sxs-lookup"><span data-stu-id="c0126-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="c0126-571">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-572">95</span><span class="sxs-lookup"><span data-stu-id="c0126-572">95</span></span></td>
   <td><span data-ttu-id="c0126-573">Windows Defender高级威胁防护可执行文件已结束</span><span class="sxs-lookup"><span data-stu-id="c0126-573">Windows Defender Advanced Threat Protection executable has ended</span></span></td>
   <td><span data-ttu-id="c0126-574">SenseCE 可执行文件已结束。</span><span class="sxs-lookup"><span data-stu-id="c0126-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="c0126-575">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-576">96</span><span class="sxs-lookup"><span data-stu-id="c0126-576">96</span></span></td>
   <td><span data-ttu-id="c0126-577">Windows Defender高级威胁防护 Init 已调用。</span><span class="sxs-lookup"><span data-stu-id="c0126-577">Windows Defender Advanced Threat Protection Init has called.</span></span> <span data-ttu-id="c0126-578">结果代码：%2</span><span class="sxs-lookup"><span data-stu-id="c0126-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="c0126-579">SenseCE 可执行文件称为 MCE 初始化。</span><span class="sxs-lookup"><span data-stu-id="c0126-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="c0126-580">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-581">97</span><span class="sxs-lookup"><span data-stu-id="c0126-581">97</span></span></td>
   <td><span data-ttu-id="c0126-582">DLP 方案的云存在连接问题</span><span class="sxs-lookup"><span data-stu-id="c0126-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="c0126-583">存在影响 DLP 分类流的网络连接问题。</span><span class="sxs-lookup"><span data-stu-id="c0126-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="c0126-584">检查网络连接。</span><span class="sxs-lookup"><span data-stu-id="c0126-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-585">98</span><span class="sxs-lookup"><span data-stu-id="c0126-585">98</span></span></td>
   <td><span data-ttu-id="c0126-586">已还原与 DLP 方案的云的连接</span><span class="sxs-lookup"><span data-stu-id="c0126-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="c0126-587">已还原与网络的连接，DLP 分类流可以继续。</span><span class="sxs-lookup"><span data-stu-id="c0126-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="c0126-588">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-589">99</span><span class="sxs-lookup"><span data-stu-id="c0126-589">99</span></span></td>
   <td><span data-ttu-id="c0126-590">与服务器通信时，Sense 遇到以下错误： (%1) 。</span><span class="sxs-lookup"><span data-stu-id="c0126-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="c0126-591">结果： (%2) </span><span class="sxs-lookup"><span data-stu-id="c0126-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="c0126-592">发生通信错误。</span><span class="sxs-lookup"><span data-stu-id="c0126-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="c0126-593">检查事件日志中的以下事件，了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="c0126-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-594">100</span><span class="sxs-lookup"><span data-stu-id="c0126-594">100</span></span></td>
   <td><span data-ttu-id="c0126-595">Windows Defender高级威胁防护可执行文件无法启动。</span><span class="sxs-lookup"><span data-stu-id="c0126-595">Windows Defender Advanced Threat Protection executable failed to start.</span></span> <span data-ttu-id="c0126-596">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="c0126-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="c0126-597">SenseCE 可执行文件无法启动。</span><span class="sxs-lookup"><span data-stu-id="c0126-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="c0126-598">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="c0126-598">Reboot the device.</span></span> <span data-ttu-id="c0126-599">如果此错误仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0126-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-600">102</span><span class="sxs-lookup"><span data-stu-id="c0126-600">102</span></span></td>
   <td><span data-ttu-id="c0126-601">Windows Defender高级威胁防护网络检测和响应可执行文件已启动</span><span class="sxs-lookup"><span data-stu-id="c0126-601">Windows Defender Advanced Threat Protection Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="c0126-602">SenseNdr 可执行文件已启动。</span><span class="sxs-lookup"><span data-stu-id="c0126-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="c0126-603">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="c0126-604">103</span><span class="sxs-lookup"><span data-stu-id="c0126-604">103</span></span></td>
   <td><span data-ttu-id="c0126-605">Windows Defender高级威胁防护网络检测和响应可执行文件已结束</span><span class="sxs-lookup"><span data-stu-id="c0126-605">Windows Defender Advanced Threat Protection Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="c0126-606">SenseNdr 可执行文件已结束。</span><span class="sxs-lookup"><span data-stu-id="c0126-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="c0126-607">正常操作通知;无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="c0126-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="c0126-608">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="c0126-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c0126-609">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c0126-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="c0126-610">相关主题</span><span class="sxs-lookup"><span data-stu-id="c0126-610">Related topics</span></span>
- [<span data-ttu-id="c0126-611">载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="c0126-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="c0126-612">配置设备代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="c0126-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="c0126-613">Microsoft Defender for Endpoint 疑难解答</span><span class="sxs-lookup"><span data-stu-id="c0126-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
