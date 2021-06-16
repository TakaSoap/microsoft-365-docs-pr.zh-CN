---
title: Microsoft Defender 终结点载入问题疑难解答
description: 解决在载入设备或 Microsoft Defender for Endpoint 服务期间可能出现的问题。
keywords: 载入疑难解答， 载入问题， 事件查看器， 数据收集和预览版本， 传感器数据和诊断
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: cb4bebe3f6998b81a00d7fd15bc919f70381a933
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929691"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-onboarding-issues"></a><span data-ttu-id="0816b-104">Microsoft Defender 终结点载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="0816b-104">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0816b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0816b-105">**Applies to:**</span></span>

- [<span data-ttu-id="0816b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0816b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- <span data-ttu-id="0816b-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0816b-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="0816b-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="0816b-108">Windows Server 2016</span></span>
- [<span data-ttu-id="0816b-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0816b-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0816b-110">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="0816b-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0816b-111">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="0816b-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="0816b-112">如果遇到问题，可能需要解决 Microsoft Defender 终结点载入过程的问题。</span><span class="sxs-lookup"><span data-stu-id="0816b-112">You might need to troubleshoot the Microsoft Defender for Endpoint onboarding process if you encounter issues.</span></span>
<span data-ttu-id="0816b-113">此页提供了解决在使用部署工具之一进行部署时可能会发生的载入问题以及设备上可能会发生的常见错误的详细步骤。</span><span class="sxs-lookup"><span data-stu-id="0816b-113">This page provides detailed steps to troubleshoot onboarding issues that might occur when deploying with one of the deployment tools and common errors that might occur on the devices.</span></span>

## <a name="troubleshoot-issues-with-onboarding-tools"></a><span data-ttu-id="0816b-114">载入工具问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="0816b-114">Troubleshoot issues with onboarding tools</span></span>

<span data-ttu-id="0816b-115">如果你已完成载入过程，但一小时后在"设备"列表中看不到设备，这可能表示[](investigate-machines.md)存在载入或连接问题。</span><span class="sxs-lookup"><span data-stu-id="0816b-115">If you have completed the onboarding process and don't see devices in the [Devices list](investigate-machines.md) after an hour, it might indicate an onboarding or connectivity problem.</span></span>

### <a name="troubleshoot-onboarding-when-deploying-with-group-policy"></a><span data-ttu-id="0816b-116">使用组策略进行部署时载入疑难解答</span><span class="sxs-lookup"><span data-stu-id="0816b-116">Troubleshoot onboarding when deploying with Group Policy</span></span>

<span data-ttu-id="0816b-117">使用组策略部署通过运行设备上载入脚本完成。</span><span class="sxs-lookup"><span data-stu-id="0816b-117">Deployment with Group Policy is done by running the onboarding script on the devices.</span></span> <span data-ttu-id="0816b-118">组策略控制台不会指示部署是否成功。</span><span class="sxs-lookup"><span data-stu-id="0816b-118">The Group Policy console does not indicate if the deployment has succeeded or not.</span></span>

<span data-ttu-id="0816b-119">如果你已完成载入过程，一小时后在"设备"列表中看不到设备，你可以检查设备上[](investigate-machines.md)脚本的输出。</span><span class="sxs-lookup"><span data-stu-id="0816b-119">If you have completed the onboarding process and don't see devices in the [Devices list](investigate-machines.md) after an hour, you can check the output of the script on the devices.</span></span> <span data-ttu-id="0816b-120">有关详细信息，请参阅使用脚本进行 [部署时载入疑难解答](#troubleshoot-onboarding-when-deploying-with-a-script)。</span><span class="sxs-lookup"><span data-stu-id="0816b-120">For more information, see [Troubleshoot onboarding when deploying with a script](#troubleshoot-onboarding-when-deploying-with-a-script).</span></span>

<span data-ttu-id="0816b-121">如果脚本成功完成，请参阅解决设备上载入问题 [，](#troubleshoot-onboarding-issues-on-the-device) 了解可能会发生的其他错误。</span><span class="sxs-lookup"><span data-stu-id="0816b-121">If the script completes successfully, see [Troubleshoot onboarding issues on the devices](#troubleshoot-onboarding-issues-on-the-device) for additional errors that might occur.</span></span>

### <a name="troubleshoot-onboarding-issues-when-deploying-with-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="0816b-122">在使用部署时解决载入Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0816b-122">Troubleshoot onboarding issues when deploying with Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="0816b-123">使用以下版本的 Configuration Manager 载入设备时：</span><span class="sxs-lookup"><span data-stu-id="0816b-123">When onboarding devices using the following versions of Configuration Manager:</span></span>

- <span data-ttu-id="0816b-124">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0816b-124">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="0816b-125">System Center 2012 配置管理器</span><span class="sxs-lookup"><span data-stu-id="0816b-125">System Center 2012 Configuration Manager</span></span>
- <span data-ttu-id="0816b-126">系统中心 2012 R2 配置管理器</span><span class="sxs-lookup"><span data-stu-id="0816b-126">System Center 2012 R2 Configuration Manager</span></span>

<span data-ttu-id="0816b-127">使用上述版本的 Configuration Manager 进行部署是在设备上运行载入脚本完成。</span><span class="sxs-lookup"><span data-stu-id="0816b-127">Deployment with the above-mentioned versions of Configuration Manager is done by running the onboarding script on the devices.</span></span> <span data-ttu-id="0816b-128">可以在 Configuration Manager 控制台中跟踪部署。</span><span class="sxs-lookup"><span data-stu-id="0816b-128">You can track the deployment in the Configuration Manager Console.</span></span>

<span data-ttu-id="0816b-129">如果部署失败，你可以检查设备上脚本的输出。</span><span class="sxs-lookup"><span data-stu-id="0816b-129">If the deployment fails, you can check the output of the script on the devices.</span></span>

<span data-ttu-id="0816b-130">如果载入成功完成，但设备未在一小时后显示在"设备"列表中，请参阅解决设备上载入问题，了解可能会发生的其他[](#troubleshoot-onboarding-issues-on-the-device)错误。</span><span class="sxs-lookup"><span data-stu-id="0816b-130">If the onboarding completed successfully but the devices are not showing up in the **Devices list** after an hour, see [Troubleshoot onboarding issues on the device](#troubleshoot-onboarding-issues-on-the-device) for additional errors that might occur.</span></span>

### <a name="troubleshoot-onboarding-when-deploying-with-a-script"></a><span data-ttu-id="0816b-131">使用脚本进行部署时载入疑难解答</span><span class="sxs-lookup"><span data-stu-id="0816b-131">Troubleshoot onboarding when deploying with a script</span></span>

<span data-ttu-id="0816b-132">**检查设备上脚本的结果：**</span><span class="sxs-lookup"><span data-stu-id="0816b-132">**Check the result of the script on the device:**</span></span>

1. <span data-ttu-id="0816b-133">单击 **"开始**"，**键入事件查看器**，然后按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="0816b-133">Click **Start**, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="0816b-134">转到 **"Windows日志**  >  **应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-134">Go to **Windows Logs** > **Application**.</span></span>

3. <span data-ttu-id="0816b-135">从 **WDATPOnboarding 事件源查找** 事件。</span><span class="sxs-lookup"><span data-stu-id="0816b-135">Look for an event from **WDATPOnboarding** event source.</span></span>

<span data-ttu-id="0816b-136">如果脚本失败并且事件是错误，您可以检查下表中的事件 ID，以帮助您解决问题。</span><span class="sxs-lookup"><span data-stu-id="0816b-136">If the script fails and the event is an error, you can check the event ID in the following table to help you troubleshoot the issue.</span></span>

> [!NOTE]
> <span data-ttu-id="0816b-137">以下事件 ID 仅特定于载入脚本。</span><span class="sxs-lookup"><span data-stu-id="0816b-137">The following event IDs are specific to the onboarding script only.</span></span>

<span data-ttu-id="0816b-138">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0816b-138">Event ID</span></span> | <span data-ttu-id="0816b-139">错误类型</span><span class="sxs-lookup"><span data-stu-id="0816b-139">Error Type</span></span> | <span data-ttu-id="0816b-140">解决方案步骤</span><span class="sxs-lookup"><span data-stu-id="0816b-140">Resolution steps</span></span>
:---:|:---|:---
 `5` | <span data-ttu-id="0816b-141">已找到但无法删除载出数据</span><span class="sxs-lookup"><span data-stu-id="0816b-141">Offboarding data was found but couldn't be deleted</span></span> | <span data-ttu-id="0816b-142">检查注册表上的权限，特别是</span><span class="sxs-lookup"><span data-stu-id="0816b-142">Check the permissions on the registry, specifically</span></span><br> <span data-ttu-id="0816b-143">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span><span class="sxs-lookup"><span data-stu-id="0816b-143">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span></span>
`10` | <span data-ttu-id="0816b-144">载入数据无法写入注册表</span><span class="sxs-lookup"><span data-stu-id="0816b-144">Onboarding data couldn't be written to registry</span></span> |  <span data-ttu-id="0816b-145">检查注册表上的权限，特别是</span><span class="sxs-lookup"><span data-stu-id="0816b-145">Check the permissions on the registry, specifically</span></span><br> <span data-ttu-id="0816b-146">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span><span class="sxs-lookup"><span data-stu-id="0816b-146">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span></span><br><span data-ttu-id="0816b-147">验证脚本是否以管理员身份运行。</span><span class="sxs-lookup"><span data-stu-id="0816b-147">Verify that the script has been run as an administrator.</span></span>
`15` |  <span data-ttu-id="0816b-148">无法启动 SENSE 服务</span><span class="sxs-lookup"><span data-stu-id="0816b-148">Failed to start SENSE service</span></span> |<span data-ttu-id="0816b-149">检查服务运行状况 (`sc query sense` 命令) 。</span><span class="sxs-lookup"><span data-stu-id="0816b-149">Check the service health (`sc query sense` command).</span></span> <span data-ttu-id="0816b-150">请确保它未在中间状态 ("Pending_Stopped"，"Pending_Running") 并尝试使用管理员权限 (再次运行) 。 </span><span class="sxs-lookup"><span data-stu-id="0816b-150">Make sure it's not in an intermediate state (*'Pending_Stopped'*, *'Pending_Running'*) and try to run the script again (with administrator rights).</span></span> <br> <br> <span data-ttu-id="0816b-151">如果设备在运行Windows 10版本 1607 并运行 `sc query sense` 命令，则 `START_PENDING` 重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="0816b-151">If the device is running Windows 10, version 1607 and running the command `sc query sense` returns `START_PENDING`, reboot the device.</span></span> <span data-ttu-id="0816b-152">如果重新启动设备无法解决问题，请升级到 KB4015217 并再次尝试载入。</span><span class="sxs-lookup"><span data-stu-id="0816b-152">If rebooting the device doesn't address the issue, upgrade to KB4015217 and try onboarding again.</span></span>
`15` | <span data-ttu-id="0816b-153">无法启动 SENSE 服务</span><span class="sxs-lookup"><span data-stu-id="0816b-153">Failed to start SENSE service</span></span> | <span data-ttu-id="0816b-154">如果错误的消息是：系统错误 577 或错误 1058 已发生，你需要启用 Microsoft Defender 防病毒 ELAM 驱动程序，请参阅确保[策略](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)未禁用 Microsoft Defender 防病毒，了解说明。</span><span class="sxs-lookup"><span data-stu-id="0816b-154">If the message of the error is: System error 577  or error 1058 has occurred, you need to enable the Microsoft Defender Antivirus ELAM driver, see [Ensure that Microsoft Defender Antivirus is not disabled by a policy](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy) for instructions.</span></span>
`30` |  <span data-ttu-id="0816b-155">脚本未能等待服务开始运行</span><span class="sxs-lookup"><span data-stu-id="0816b-155">The script failed to wait for the service to start running</span></span> | <span data-ttu-id="0816b-156">该服务可能有更多的时间来启动或在尝试启动时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="0816b-156">The service could have taken more time to start or has encountered errors while trying to start.</span></span> <span data-ttu-id="0816b-157">有关与 SENSE 相关的事件和错误的详细信息，请参阅使用事件查看器查看 [事件和错误](event-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="0816b-157">For more information on events and errors related to SENSE, see [Review events and errors using Event viewer](event-error-codes.md).</span></span>
`35` |  <span data-ttu-id="0816b-158">脚本未能找到所需的载入状态注册表值</span><span class="sxs-lookup"><span data-stu-id="0816b-158">The script failed to find needed onboarding status registry value</span></span> | <span data-ttu-id="0816b-159">当 SENSE 服务首次启动时，它会将载入状态写入注册表位置</span><span class="sxs-lookup"><span data-stu-id="0816b-159">When the SENSE service starts for the first time, it writes onboarding status to the registry location</span></span><br><span data-ttu-id="0816b-160">`HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status`.</span><span class="sxs-lookup"><span data-stu-id="0816b-160">`HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status`.</span></span><br> <span data-ttu-id="0816b-161">脚本在几秒钟后未能找到它。</span><span class="sxs-lookup"><span data-stu-id="0816b-161">The script failed to find it after several seconds.</span></span> <span data-ttu-id="0816b-162">你可以手动测试它并检查它是否在那里。</span><span class="sxs-lookup"><span data-stu-id="0816b-162">You can manually test it and check if it's there.</span></span> <span data-ttu-id="0816b-163">有关与 SENSE 相关的事件和错误的详细信息，请参阅使用事件查看器查看 [事件和错误](event-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="0816b-163">For more information on events and errors related to SENSE, see [Review events and errors using Event viewer](event-error-codes.md).</span></span>
`40` | <span data-ttu-id="0816b-164">SENSE 服务载入状态未设置为 **1**</span><span class="sxs-lookup"><span data-stu-id="0816b-164">SENSE service onboarding status is not set to **1**</span></span> | <span data-ttu-id="0816b-165">SENSE 服务未能正确载入。</span><span class="sxs-lookup"><span data-stu-id="0816b-165">The SENSE service has failed to onboard properly.</span></span> <span data-ttu-id="0816b-166">有关与 SENSE 相关的事件和错误的详细信息，请参阅使用事件查看器查看 [事件和错误](event-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="0816b-166">For more information on events and errors related to SENSE, see [Review events and errors using Event viewer](event-error-codes.md).</span></span>
`65` | <span data-ttu-id="0816b-167">权限不足</span><span class="sxs-lookup"><span data-stu-id="0816b-167">Insufficient privileges</span></span>| <span data-ttu-id="0816b-168">使用管理员权限再次运行脚本。</span><span class="sxs-lookup"><span data-stu-id="0816b-168">Run the script again with administrator privileges.</span></span>

### <a name="troubleshoot-onboarding-issues-using-microsoft-intune"></a><span data-ttu-id="0816b-169">使用工具解决载入Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0816b-169">Troubleshoot onboarding issues using Microsoft Intune</span></span>

<span data-ttu-id="0816b-170">您可以使用Microsoft Intune检查错误代码并尝试对问题的原因进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="0816b-170">You can use Microsoft Intune to check error codes and attempt to troubleshoot the cause of the issue.</span></span>

<span data-ttu-id="0816b-171">如果你在 Intune 中配置了策略，并且这些策略未在设备上传播，你可能需要配置自动 MDM 注册。</span><span class="sxs-lookup"><span data-stu-id="0816b-171">If you have configured policies in Intune and they are not propagated on devices, you might need to configure automatic MDM enrollment.</span></span>

<span data-ttu-id="0816b-172">使用下表了解载入时可能出现的问题原因：</span><span class="sxs-lookup"><span data-stu-id="0816b-172">Use the following tables to understand the possible causes of issues while onboarding:</span></span>

- <span data-ttu-id="0816b-173">Microsoft Intune错误代码和OMA-URIs表</span><span class="sxs-lookup"><span data-stu-id="0816b-173">Microsoft Intune error codes and OMA-URIs table</span></span>
- <span data-ttu-id="0816b-174">非合规性表的已知问题</span><span class="sxs-lookup"><span data-stu-id="0816b-174">Known issues with non-compliance table</span></span>
- <span data-ttu-id="0816b-175">移动设备管理 (MDM) 事件日志表</span><span class="sxs-lookup"><span data-stu-id="0816b-175">Mobile Device Management (MDM) event logs table</span></span>

<span data-ttu-id="0816b-176">如果任何事件日志和疑难解答步骤都不起作用，请从门户的" **设备** 管理"部分下载本地脚本，在提升的命令提示符中运行它。</span><span class="sxs-lookup"><span data-stu-id="0816b-176">If none of the event logs and troubleshooting steps work, download the Local script from the **Device management** section of the portal, and run it in an elevated command prompt.</span></span>

#### <a name="microsoft-intune-error-codes-and-oma-uris"></a><span data-ttu-id="0816b-177">Microsoft Intune错误代码和OMA-URIs</span><span class="sxs-lookup"><span data-stu-id="0816b-177">Microsoft Intune error codes and OMA-URIs</span></span>

<span data-ttu-id="0816b-178">错误代码十六进制</span><span class="sxs-lookup"><span data-stu-id="0816b-178">Error Code Hex</span></span> | <span data-ttu-id="0816b-179">错误代码 Dec</span><span class="sxs-lookup"><span data-stu-id="0816b-179">Error Code Dec</span></span> | <span data-ttu-id="0816b-180">Error Description</span><span class="sxs-lookup"><span data-stu-id="0816b-180">Error Description</span></span> | <span data-ttu-id="0816b-181">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="0816b-181">OMA-URI</span></span> | <span data-ttu-id="0816b-182">可能的原因和疑难解答步骤</span><span class="sxs-lookup"><span data-stu-id="0816b-182">Possible cause and troubleshooting steps</span></span>
:---:|:---|:---|:---|:---
<span data-ttu-id="0816b-183">0x87D1FDE8</span><span class="sxs-lookup"><span data-stu-id="0816b-183">0x87D1FDE8</span></span> | <span data-ttu-id="0816b-184">-2016281112</span><span class="sxs-lookup"><span data-stu-id="0816b-184">-2016281112</span></span> | <span data-ttu-id="0816b-185">修正失败</span><span class="sxs-lookup"><span data-stu-id="0816b-185">Remediation failed</span></span> | <span data-ttu-id="0816b-186">载入</span><span class="sxs-lookup"><span data-stu-id="0816b-186">Onboarding</span></span> <br> <span data-ttu-id="0816b-187">载出</span><span class="sxs-lookup"><span data-stu-id="0816b-187">Offboarding</span></span> | <span data-ttu-id="0816b-188">**可能的原因：** 载入或载出在错误的 blob 上失败：签名错误或缺少 PreviousOrgIds 字段。</span><span class="sxs-lookup"><span data-stu-id="0816b-188">**Possible cause:** Onboarding or offboarding failed on a wrong blob: wrong signature or missing PreviousOrgIds fields.</span></span> <br><br> <span data-ttu-id="0816b-189">**疑难解答步骤：**</span><span class="sxs-lookup"><span data-stu-id="0816b-189">**Troubleshooting steps:**</span></span> <br> <span data-ttu-id="0816b-190">在"查看设备事件日志中的代理载入错误"部分检查[事件 ID。](#view-agent-onboarding-errors-in-the-device-event-log)</span><span class="sxs-lookup"><span data-stu-id="0816b-190">Check the event IDs in the [View agent onboarding errors in the device event log](#view-agent-onboarding-errors-in-the-device-event-log) section.</span></span> <br><br> <span data-ttu-id="0816b-191">检查下表中的 MDM 事件日志或按照诊断 MDM 故障中的说明操作[Windows 10。](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10)</span><span class="sxs-lookup"><span data-stu-id="0816b-191">Check the MDM event logs in the following table or follow the instructions in [Diagnose MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).</span></span>
 | | | | <span data-ttu-id="0816b-192">载入</span><span class="sxs-lookup"><span data-stu-id="0816b-192">Onboarding</span></span> <br> <span data-ttu-id="0816b-193">载出</span><span class="sxs-lookup"><span data-stu-id="0816b-193">Offboarding</span></span> <br> <span data-ttu-id="0816b-194">SampleSharing</span><span class="sxs-lookup"><span data-stu-id="0816b-194">SampleSharing</span></span> | <span data-ttu-id="0816b-195">**可能的原因：** Microsoft Defender for Endpoint Policy 注册表项不存在，或者 OMA DM 客户端没有写入它的权限。</span><span class="sxs-lookup"><span data-stu-id="0816b-195">**Possible cause:** Microsoft Defender for Endpoint Policy registry key does not exist or the OMA DM client doesn't have permissions to write to it.</span></span> <br><br> <span data-ttu-id="0816b-196">**疑难解答步骤：** 确保存在以下注册表项： `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="0816b-196">**Troubleshooting steps:** Ensure that the following registry key exists: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span> <br> <br> <span data-ttu-id="0816b-197">如果不存在，请打开提升的命令并添加密钥。</span><span class="sxs-lookup"><span data-stu-id="0816b-197">If it doesn't exist, open an elevated command and add the key.</span></span>
 | | | | <span data-ttu-id="0816b-198">SenseIsRunning</span><span class="sxs-lookup"><span data-stu-id="0816b-198">SenseIsRunning</span></span> <br> <span data-ttu-id="0816b-199">OnboardingState</span><span class="sxs-lookup"><span data-stu-id="0816b-199">OnboardingState</span></span> <br> <span data-ttu-id="0816b-200">OrgId</span><span class="sxs-lookup"><span data-stu-id="0816b-200">OrgId</span></span> |  <span data-ttu-id="0816b-201">**可能的原因：** 尝试通过只读属性修正。</span><span class="sxs-lookup"><span data-stu-id="0816b-201">**Possible cause:** An attempt to remediate by read-only property.</span></span> <span data-ttu-id="0816b-202">载入失败。</span><span class="sxs-lookup"><span data-stu-id="0816b-202">Onboarding has failed.</span></span> <br><br> <span data-ttu-id="0816b-203">**疑难解答步骤：** 查看解决设备上载入 [问题中的疑难解答步骤](#troubleshoot-onboarding-issues-on-the-device)。</span><span class="sxs-lookup"><span data-stu-id="0816b-203">**Troubleshooting steps:** Check the troubleshooting steps in [Troubleshoot onboarding issues on the device](#troubleshoot-onboarding-issues-on-the-device).</span></span> <br><br> <span data-ttu-id="0816b-204">检查下表中的 MDM 事件日志或按照诊断 MDM 故障中的说明操作[Windows 10。](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10)</span><span class="sxs-lookup"><span data-stu-id="0816b-204">Check the MDM event logs in the following table or follow the instructions in [Diagnose MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).</span></span>
 | | | | <span data-ttu-id="0816b-205">全部</span><span class="sxs-lookup"><span data-stu-id="0816b-205">All</span></span> | <span data-ttu-id="0816b-206">**可能的原因：** 尝试在不支持的 SKU/平台上部署 Microsoft Defender for Endpoint，尤其是全息 SKU。</span><span class="sxs-lookup"><span data-stu-id="0816b-206">**Possible cause:** Attempt to deploy Microsoft Defender for Endpoint on non-supported SKU/Platform, particularly Holographic SKU.</span></span> <br><br> <span data-ttu-id="0816b-207">当前支持的平台：</span><span class="sxs-lookup"><span data-stu-id="0816b-207">Currently supported platforms:</span></span><br> <span data-ttu-id="0816b-208">Enterprise、教育以及Professional。</span><span class="sxs-lookup"><span data-stu-id="0816b-208">Enterprise, Education, and Professional.</span></span><br> <span data-ttu-id="0816b-209">不支持服务器。</span><span class="sxs-lookup"><span data-stu-id="0816b-209">Server is not supported.</span></span>
 <span data-ttu-id="0816b-210">0x87D101A9</span><span class="sxs-lookup"><span data-stu-id="0816b-210">0x87D101A9</span></span> | <span data-ttu-id="0816b-211">-2016345687</span><span class="sxs-lookup"><span data-stu-id="0816b-211">-2016345687</span></span> |<span data-ttu-id="0816b-212">SyncML (425) ：请求的命令失败，因为发件人没有足够的访问控制权限 (对收件人) ACL 权限。</span><span class="sxs-lookup"><span data-stu-id="0816b-212">SyncML(425): The requested command failed because the sender does not have adequate access control permissions (ACL) on the recipient.</span></span> | <span data-ttu-id="0816b-213">全部</span><span class="sxs-lookup"><span data-stu-id="0816b-213">All</span></span> |  <span data-ttu-id="0816b-214">**可能的原因：** 尝试在不支持的 SKU/平台上部署 Microsoft Defender for Endpoint，尤其是全息 SKU。</span><span class="sxs-lookup"><span data-stu-id="0816b-214">**Possible cause:** Attempt to deploy Microsoft Defender for Endpoint on non-supported SKU/Platform, particularly Holographic SKU.</span></span><br><br> <span data-ttu-id="0816b-215">当前支持的平台：</span><span class="sxs-lookup"><span data-stu-id="0816b-215">Currently supported platforms:</span></span><br>  <span data-ttu-id="0816b-216">Enterprise、教育以及Professional。</span><span class="sxs-lookup"><span data-stu-id="0816b-216">Enterprise, Education, and Professional.</span></span>

#### <a name="known-issues-with-non-compliance"></a><span data-ttu-id="0816b-217">不合规的已知问题</span><span class="sxs-lookup"><span data-stu-id="0816b-217">Known issues with non-compliance</span></span>

<span data-ttu-id="0816b-218">下表提供了有关不合规问题以及如何解决这些问题的信息。</span><span class="sxs-lookup"><span data-stu-id="0816b-218">The following table provides information on issues with non-compliance and how you can address the issues.</span></span>

<span data-ttu-id="0816b-219">情况</span><span class="sxs-lookup"><span data-stu-id="0816b-219">Case</span></span> | <span data-ttu-id="0816b-220">症状</span><span class="sxs-lookup"><span data-stu-id="0816b-220">Symptoms</span></span> | <span data-ttu-id="0816b-221">可能的原因和疑难解答步骤</span><span class="sxs-lookup"><span data-stu-id="0816b-221">Possible cause and troubleshooting steps</span></span>
:---:|:---|:---
 `1` | <span data-ttu-id="0816b-222">设备符合 SenseIsRunning OMA-URI。</span><span class="sxs-lookup"><span data-stu-id="0816b-222">Device is compliant by SenseIsRunning OMA-URI.</span></span> <span data-ttu-id="0816b-223">但不符合 OrgId、Onboarding 和 OnboardingState OMA-URI。</span><span class="sxs-lookup"><span data-stu-id="0816b-223">But is non-compliant by OrgId, Onboarding and OnboardingState OMA-URIs.</span></span> | <span data-ttu-id="0816b-224">**可能的原因：** 检查用户在安装或升级后Windows OOBE。</span><span class="sxs-lookup"><span data-stu-id="0816b-224">**Possible cause:** Check that user passed OOBE after Windows installation or upgrade.</span></span> <span data-ttu-id="0816b-225">在 OOBE 载入期间无法完成，但 SENSE 已在运行。</span><span class="sxs-lookup"><span data-stu-id="0816b-225">During OOBE onboarding couldn't be completed but SENSE is running already.</span></span><br><br> <span data-ttu-id="0816b-226">**疑难解答步骤：** 等待 OOBE 完成。</span><span class="sxs-lookup"><span data-stu-id="0816b-226">**Troubleshooting steps:** Wait for OOBE to complete.</span></span>
 `2` |  <span data-ttu-id="0816b-227">设备符合 OrgId、Onboarding 和 OnboardingState OMA-URI，但不符合 SenseIsRunning OMA-URI。</span><span class="sxs-lookup"><span data-stu-id="0816b-227">Device is compliant by OrgId, Onboarding, and OnboardingState OMA-URIs, but is non-compliant by SenseIsRunning OMA-URI.</span></span> |  <span data-ttu-id="0816b-228">**可能的原因：** Sense 服务的启动类型设置为"延迟启动"。</span><span class="sxs-lookup"><span data-stu-id="0816b-228">**Possible cause:** Sense service's startup type is set as "Delayed Start".</span></span> <span data-ttu-id="0816b-229">有时，当系统Microsoft Intune DM 会话时，这会导致服务器将设备报告为不符合 SenseIsRunning。</span><span class="sxs-lookup"><span data-stu-id="0816b-229">Sometimes this causes the Microsoft Intune server to report the device as non-compliant by SenseIsRunning when DM session occurs on system start.</span></span> <br><br> <span data-ttu-id="0816b-230">**疑难解答步骤：** 该问题应在 24 小时内自动修复。</span><span class="sxs-lookup"><span data-stu-id="0816b-230">**Troubleshooting steps:** The issue should automatically be fixed within 24 hours.</span></span>
 `3` | <span data-ttu-id="0816b-231">设备不兼容</span><span class="sxs-lookup"><span data-stu-id="0816b-231">Device is non-compliant</span></span> | <span data-ttu-id="0816b-232">**疑难解答步骤：** 确保未在同一设备上同时部署载入和载出策略。</span><span class="sxs-lookup"><span data-stu-id="0816b-232">**Troubleshooting steps:** Ensure that Onboarding and Offboarding policies are not deployed on the same device at same time.</span></span>

#### <a name="mobile-device-management-mdm-event-logs"></a><span data-ttu-id="0816b-233">移动设备管理 (MDM) 事件日志</span><span class="sxs-lookup"><span data-stu-id="0816b-233">Mobile Device Management (MDM) event logs</span></span>

<span data-ttu-id="0816b-234">查看 MDM 事件日志，解决载入期间可能出现的问题：</span><span class="sxs-lookup"><span data-stu-id="0816b-234">View the MDM event logs to troubleshoot issues that might arise during onboarding:</span></span>

<span data-ttu-id="0816b-235">日志名称：Microsoft\Windows\DeviceManagement-EnterpriseDiagnostics-Provider</span><span class="sxs-lookup"><span data-stu-id="0816b-235">Log name: Microsoft\Windows\DeviceManagement-EnterpriseDiagnostics-Provider</span></span>

<span data-ttu-id="0816b-236">频道名称：管理员</span><span class="sxs-lookup"><span data-stu-id="0816b-236">Channel name: Admin</span></span>

<span data-ttu-id="0816b-237">ID</span><span class="sxs-lookup"><span data-stu-id="0816b-237">ID</span></span> | <span data-ttu-id="0816b-238">严重性</span><span class="sxs-lookup"><span data-stu-id="0816b-238">Severity</span></span> | <span data-ttu-id="0816b-239">事件描述</span><span class="sxs-lookup"><span data-stu-id="0816b-239">Event description</span></span> | <span data-ttu-id="0816b-240">故障排除步骤</span><span class="sxs-lookup"><span data-stu-id="0816b-240">Troubleshooting steps</span></span>
:---|:---|:---|:---
<span data-ttu-id="0816b-241">1819</span><span class="sxs-lookup"><span data-stu-id="0816b-241">1819</span></span> | <span data-ttu-id="0816b-242">错误</span><span class="sxs-lookup"><span data-stu-id="0816b-242">Error</span></span> | <span data-ttu-id="0816b-243">适用于终结点 CSP 的 Microsoft Defender：未能设置节点的值。</span><span class="sxs-lookup"><span data-stu-id="0816b-243">Microsoft Defender for Endpoint CSP: Failed to Set Node's Value.</span></span> <span data-ttu-id="0816b-244">NodeId： (%1) ，TokenName： (%2) ，结果： (%3) 。</span><span class="sxs-lookup"><span data-stu-id="0816b-244">NodeId: (%1), TokenName: (%2), Result: (%3).</span></span> | <span data-ttu-id="0816b-245">下载[1607 年 Windows 10 累积更新](https://go.microsoft.com/fwlink/?linkid=829760)。</span><span class="sxs-lookup"><span data-stu-id="0816b-245">Download the [Cumulative Update for Windows 10, 1607](https://go.microsoft.com/fwlink/?linkid=829760).</span></span>

## <a name="troubleshoot-onboarding-issues-on-the-device"></a><span data-ttu-id="0816b-246">解决设备上载入问题</span><span class="sxs-lookup"><span data-stu-id="0816b-246">Troubleshoot onboarding issues on the device</span></span>

<span data-ttu-id="0816b-247">如果使用的部署工具未指示载入过程中的错误，但设备在一小时内仍不显示在设备列表中，请浏览以下验证主题，检查 Microsoft Defender for Endpoint 代理是否发生了错误。</span><span class="sxs-lookup"><span data-stu-id="0816b-247">If the deployment tools used does not indicate an error in the onboarding process, but devices are still not appearing in the devices list in an hour, go through the following verification topics to check if an error occurred with the Microsoft Defender for Endpoint agent.</span></span>

- [<span data-ttu-id="0816b-248">查看设备事件日志中的代理载入错误</span><span class="sxs-lookup"><span data-stu-id="0816b-248">View agent onboarding errors in the device event log</span></span>](#view-agent-onboarding-errors-in-the-device-event-log)
- [<span data-ttu-id="0816b-249">确保诊断数据服务已启用</span><span class="sxs-lookup"><span data-stu-id="0816b-249">Ensure the diagnostic data service is enabled</span></span>](#ensure-the-diagnostics-service-is-enabled)
- [<span data-ttu-id="0816b-250">确保服务设置为启动</span><span class="sxs-lookup"><span data-stu-id="0816b-250">Ensure the service is set to start</span></span>](#ensure-the-service-is-set-to-start)
- [<span data-ttu-id="0816b-251">确保设备具有 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="0816b-251">Ensure the device has an Internet connection</span></span>](#ensure-the-device-has-an-internet-connection)
- [<span data-ttu-id="0816b-252">确保Microsoft Defender 防病毒策略未禁用此策略</span><span class="sxs-lookup"><span data-stu-id="0816b-252">Ensure that Microsoft Defender Antivirus is not disabled by a policy</span></span>](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

### <a name="view-agent-onboarding-errors-in-the-device-event-log"></a><span data-ttu-id="0816b-253">查看设备事件日志中的代理载入错误</span><span class="sxs-lookup"><span data-stu-id="0816b-253">View agent onboarding errors in the device event log</span></span>

1. <span data-ttu-id="0816b-254">单击 **"开始**"，**键入事件查看器**，然后按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="0816b-254">Click **Start**, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="0816b-255">在事件 **查看器 (本地)** 窗格中，展开应用程序 **和服务** 日志 Microsoft Windows  >    >    >  **SENSE**。</span><span class="sxs-lookup"><span data-stu-id="0816b-255">In the **Event Viewer (Local)** pane, expand **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0816b-256">SENSE 是内部名称，用于引用支持 Microsoft Defender for Endpoint 的行为传感器。</span><span class="sxs-lookup"><span data-stu-id="0816b-256">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="0816b-257">选择 **"操作** "以加载日志。</span><span class="sxs-lookup"><span data-stu-id="0816b-257">Select **Operational** to load the log.</span></span>

4. <span data-ttu-id="0816b-258">在"**操作"窗格中**，单击"**筛选当前日志"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-258">In the **Action** pane, click **Filter Current log**.</span></span>

5. <span data-ttu-id="0816b-259">在"**筛选器"** 选项卡上的"**事件级别：** 选择 **严重**、**警告** 和 **错误**"下，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-259">On the **Filter** tab, under **Event level:** select **Critical**, **Warning**, and **Error**, and click **OK**.</span></span>

   ![事件查看器日志筛选器的图像](images/filter-log.png)

6. <span data-ttu-id="0816b-261">可指示问题的事件将显示在"操作" **窗格中** 。</span><span class="sxs-lookup"><span data-stu-id="0816b-261">Events which can indicate issues will appear in the **Operational** pane.</span></span> <span data-ttu-id="0816b-262">您可以尝试根据下表中的解决方案进行疑难解答：</span><span class="sxs-lookup"><span data-stu-id="0816b-262">You can attempt to troubleshoot them based on the solutions in the following table:</span></span>

<span data-ttu-id="0816b-263">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0816b-263">Event ID</span></span> | <span data-ttu-id="0816b-264">邮件</span><span class="sxs-lookup"><span data-stu-id="0816b-264">Message</span></span> | <span data-ttu-id="0816b-265">解决方案步骤</span><span class="sxs-lookup"><span data-stu-id="0816b-265">Resolution steps</span></span>
:---:|:---|:---
 `5` | <span data-ttu-id="0816b-266">Microsoft Defender for Endpoint 服务无法连接到位于 _variable 的服务器_</span><span class="sxs-lookup"><span data-stu-id="0816b-266">Microsoft Defender for Endpoint service failed to connect to the server at _variable_</span></span> | <span data-ttu-id="0816b-267">[确保设备可以访问 Internet。](#ensure-the-device-has-an-internet-connection)</span><span class="sxs-lookup"><span data-stu-id="0816b-267">[Ensure the device has Internet access](#ensure-the-device-has-an-internet-connection).</span></span>
 `6` | <span data-ttu-id="0816b-268">Microsoft Defender for Endpoint 服务未载入，并且未找到任何载入参数。</span><span class="sxs-lookup"><span data-stu-id="0816b-268">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span> <span data-ttu-id="0816b-269">失败代码： _变量_</span><span class="sxs-lookup"><span data-stu-id="0816b-269">Failure code: _variable_</span></span> | <span data-ttu-id="0816b-270">[再次运行载入脚本](configure-endpoints-script.md)。</span><span class="sxs-lookup"><span data-stu-id="0816b-270">[Run the onboarding script again](configure-endpoints-script.md).</span></span>
 `7` | <span data-ttu-id="0816b-271">Microsoft Defender for Endpoint 服务无法读取载入参数。</span><span class="sxs-lookup"><span data-stu-id="0816b-271">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="0816b-272">失败代码： _变量_</span><span class="sxs-lookup"><span data-stu-id="0816b-272">Failure code: _variable_</span></span> | <span data-ttu-id="0816b-273">[确保设备可以访问 Internet，](#ensure-the-device-has-an-internet-connection)然后再次运行整个载入过程。</span><span class="sxs-lookup"><span data-stu-id="0816b-273">[Ensure the device has Internet access](#ensure-the-device-has-an-internet-connection), then run the entire onboarding process again.</span></span>
 `9` | <span data-ttu-id="0816b-274">Microsoft Defender for Endpoint 服务未能更改其启动类型。</span><span class="sxs-lookup"><span data-stu-id="0816b-274">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="0816b-275">失败代码：变量</span><span class="sxs-lookup"><span data-stu-id="0816b-275">Failure code: variable</span></span> | <span data-ttu-id="0816b-276">如果事件在载入期间发生，请重新启动并重新尝试运行载入脚本。</span><span class="sxs-lookup"><span data-stu-id="0816b-276">If the event happened during onboarding, reboot and re-attempt running the onboarding script.</span></span> <span data-ttu-id="0816b-277">有关详细信息，请参阅再次 [运行载入脚本](configure-endpoints-script.md)。</span><span class="sxs-lookup"><span data-stu-id="0816b-277">For more information, see [Run the onboarding script again](configure-endpoints-script.md).</span></span> <br><br><span data-ttu-id="0816b-278">如果事件在载出期间发生，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="0816b-278">If the event happened during offboarding, contact support.</span></span>
`10` | <span data-ttu-id="0816b-279">Microsoft Defender for Endpoint 服务无法保留载入信息。</span><span class="sxs-lookup"><span data-stu-id="0816b-279">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="0816b-280">失败代码：变量</span><span class="sxs-lookup"><span data-stu-id="0816b-280">Failure code: variable</span></span> | <span data-ttu-id="0816b-281">如果事件在载入期间发生，请重新尝试运行载入脚本。</span><span class="sxs-lookup"><span data-stu-id="0816b-281">If the event happened during onboarding, re-attempt running the onboarding script.</span></span> <span data-ttu-id="0816b-282">有关详细信息，请参阅再次 [运行载入脚本](configure-endpoints-script.md)。</span><span class="sxs-lookup"><span data-stu-id="0816b-282">For more information, see [Run the onboarding script again](configure-endpoints-script.md).</span></span> <br><br><span data-ttu-id="0816b-283">如果问题仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="0816b-283">If the problem persists, contact support.</span></span>
`15` | <span data-ttu-id="0816b-284">Microsoft Defender for Endpoint 无法使用 URL 启动命令 _通道：变量_</span><span class="sxs-lookup"><span data-stu-id="0816b-284">Microsoft Defender for Endpoint cannot start command channel with URL: _variable_</span></span> | <span data-ttu-id="0816b-285">[确保设备可以访问 Internet。](#ensure-the-device-has-an-internet-connection)</span><span class="sxs-lookup"><span data-stu-id="0816b-285">[Ensure the device has Internet access](#ensure-the-device-has-an-internet-connection).</span></span>
`17` | <span data-ttu-id="0816b-286">Microsoft Defender for Endpoint 服务未能更改连接用户体验和遥测服务位置。</span><span class="sxs-lookup"><span data-stu-id="0816b-286">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="0816b-287">失败代码：变量</span><span class="sxs-lookup"><span data-stu-id="0816b-287">Failure code: variable</span></span> | <span data-ttu-id="0816b-288">[再次运行载入脚本](configure-endpoints-script.md)。</span><span class="sxs-lookup"><span data-stu-id="0816b-288">[Run the onboarding script again](configure-endpoints-script.md).</span></span> <span data-ttu-id="0816b-289">如果问题仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="0816b-289">If the problem persists, contact support.</span></span>
`25` | <span data-ttu-id="0816b-290">Microsoft Defender for Endpoint 服务无法重置注册表中的运行状况状态。</span><span class="sxs-lookup"><span data-stu-id="0816b-290">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="0816b-291">失败代码： _变量_</span><span class="sxs-lookup"><span data-stu-id="0816b-291">Failure code: _variable_</span></span> | <span data-ttu-id="0816b-292">请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="0816b-292">Contact support.</span></span>
`27` | <span data-ttu-id="0816b-293">未能在终结点模式下启用 Microsoft Defender Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="0816b-293">Failed to enable Microsoft Defender for Endpoint mode in Windows Defender.</span></span> <span data-ttu-id="0816b-294">载入过程失败。</span><span class="sxs-lookup"><span data-stu-id="0816b-294">Onboarding process failed.</span></span> <span data-ttu-id="0816b-295">失败代码：变量</span><span class="sxs-lookup"><span data-stu-id="0816b-295">Failure code: variable</span></span> | <span data-ttu-id="0816b-296">请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="0816b-296">Contact support.</span></span>
`29` | <span data-ttu-id="0816b-297">未能读取 offboarding参数。</span><span class="sxs-lookup"><span data-stu-id="0816b-297">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="0816b-298">错误类型：%1，错误代码：%2，说明：%3</span><span class="sxs-lookup"><span data-stu-id="0816b-298">Error type: %1, Error code: %2, Description: %3</span></span> | <span data-ttu-id="0816b-299">确保设备可以访问 Internet，然后再次运行整个载出过程。</span><span class="sxs-lookup"><span data-stu-id="0816b-299">Ensure the device has Internet access, then run the entire offboarding process again.</span></span>
`30` | <span data-ttu-id="0816b-300">在 Microsoft Defender for Endpoint (禁用 $ build.sense.productDisplayName) 模式失败。</span><span class="sxs-lookup"><span data-stu-id="0816b-300">Failed to disable $(build.sense.productDisplayName) mode in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="0816b-301">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="0816b-301">Failure code: %1</span></span> | <span data-ttu-id="0816b-302">请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="0816b-302">Contact support.</span></span>
`32` | <span data-ttu-id="0816b-303">$ (build.sense.productDisplayName) 服务在板载过程后无法请求自行停止。</span><span class="sxs-lookup"><span data-stu-id="0816b-303">$(build.sense.productDisplayName) service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="0816b-304">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="0816b-304">Failure code: %1</span></span> | <span data-ttu-id="0816b-305">验证服务启动类型是手动的，然后重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="0816b-305">Verify that the service start type is manual and reboot the device.</span></span>
`55` | <span data-ttu-id="0816b-306">未能创建安全 ETW 自动记录器。</span><span class="sxs-lookup"><span data-stu-id="0816b-306">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="0816b-307">失败代码：%1</span><span class="sxs-lookup"><span data-stu-id="0816b-307">Failure code: %1</span></span> | <span data-ttu-id="0816b-308">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="0816b-308">Reboot the device.</span></span>
`63` | <span data-ttu-id="0816b-309">更新外部服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="0816b-309">Updating the start type of external service.</span></span> <span data-ttu-id="0816b-310">名称：%1，实际开始类型：%2，预期开始类型：%3，退出代码：%4</span><span class="sxs-lookup"><span data-stu-id="0816b-310">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span> | <span data-ttu-id="0816b-311">确定导致上述服务启动类型发生更改的原因。</span><span class="sxs-lookup"><span data-stu-id="0816b-311">Identify what is causing changes in start type of mentioned service.</span></span> <span data-ttu-id="0816b-312">如果退出代码不为 0，请手动将启动类型修复为预期的开始类型。</span><span class="sxs-lookup"><span data-stu-id="0816b-312">If the exit code is not 0, fix the start type manually to expected start type.</span></span>
`64` | <span data-ttu-id="0816b-313">启动已停止的外部服务。</span><span class="sxs-lookup"><span data-stu-id="0816b-313">Starting stopped external service.</span></span> <span data-ttu-id="0816b-314">名称：%1，退出代码：%2</span><span class="sxs-lookup"><span data-stu-id="0816b-314">Name: %1, exit code: %2</span></span> | <span data-ttu-id="0816b-315">如果事件一直重新显示，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="0816b-315">Contact support if the event keeps re-appearing.</span></span>
`68` | <span data-ttu-id="0816b-316">服务的启动类型是意外的。</span><span class="sxs-lookup"><span data-stu-id="0816b-316">The start type of the service is unexpected.</span></span> <span data-ttu-id="0816b-317">服务名称：%1，实际启动类型：%2，预期启动类型：%3</span><span class="sxs-lookup"><span data-stu-id="0816b-317">Service name: %1, actual start type: %2, expected start type: %3</span></span> | <span data-ttu-id="0816b-318">确定导致开始类型更改的原因。</span><span class="sxs-lookup"><span data-stu-id="0816b-318">Identify what is causing changes in start type.</span></span> <span data-ttu-id="0816b-319">修复了提及的服务启动类型。</span><span class="sxs-lookup"><span data-stu-id="0816b-319">Fix mentioned service start type.</span></span>
`69` | <span data-ttu-id="0816b-320">服务已停止。</span><span class="sxs-lookup"><span data-stu-id="0816b-320">The service is stopped.</span></span> <span data-ttu-id="0816b-321">服务名称：%1</span><span class="sxs-lookup"><span data-stu-id="0816b-321">Service name: %1</span></span> | <span data-ttu-id="0816b-322">启动提及的服务。</span><span class="sxs-lookup"><span data-stu-id="0816b-322">Start the mentioned service.</span></span> <span data-ttu-id="0816b-323">如果仍然存在，请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="0816b-323">Contact support if persists.</span></span>

<br />

<span data-ttu-id="0816b-324">设备上还有 Microsoft Defender for Endpoint 代理正常运行所依赖的其他组件。</span><span class="sxs-lookup"><span data-stu-id="0816b-324">There are additional components on the device that the Microsoft Defender for Endpoint agent depends on to function properly.</span></span> <span data-ttu-id="0816b-325">如果 Microsoft Defender for Endpoint 代理事件日志中没有载入相关错误，请继续执行以下步骤，以确保正确配置其他组件。</span><span class="sxs-lookup"><span data-stu-id="0816b-325">If there are no onboarding related errors in the Microsoft Defender for Endpoint agent event log, proceed with the following steps to ensure that the additional components are configured correctly.</span></span>

<span id="ensure-the-diagnostics-service-is-enabled" />

### <a name="ensure-the-diagnostic-data-service-is-enabled"></a><span data-ttu-id="0816b-326">确保诊断数据服务已启用</span><span class="sxs-lookup"><span data-stu-id="0816b-326">Ensure the diagnostic data service is enabled</span></span>

<span data-ttu-id="0816b-327">如果设备未正确报告，你可能需要检查Windows 10数据服务是否设置为自动启动并且正在设备上运行。</span><span class="sxs-lookup"><span data-stu-id="0816b-327">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the device.</span></span> <span data-ttu-id="0816b-328">该服务可能已被其他程序或用户配置更改禁用。</span><span class="sxs-lookup"><span data-stu-id="0816b-328">The service might have been disabled by other programs or user configuration changes.</span></span>

<span data-ttu-id="0816b-329">首先，应检查服务是否设置为在 Windows 启动时自动启动，然后应检查服务当前是否正在运行 (如果未运行该服务，则启动) 。</span><span class="sxs-lookup"><span data-stu-id="0816b-329">First, you should check that the service is set to start automatically when Windows starts, then you should check that the service is currently running (and start it if it isn't).</span></span>

### <a name="ensure-the-service-is-set-to-start"></a><span data-ttu-id="0816b-330">确保服务设置为启动</span><span class="sxs-lookup"><span data-stu-id="0816b-330">Ensure the service is set to start</span></span>

<span data-ttu-id="0816b-331">**使用命令行检查诊断Windows 10服务启动类型**：</span><span class="sxs-lookup"><span data-stu-id="0816b-331">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="0816b-332">在设备上打开提升的命令行提示符：</span><span class="sxs-lookup"><span data-stu-id="0816b-332">Open an elevated command-line prompt on the device:</span></span>

   <span data-ttu-id="0816b-333">a.</span><span class="sxs-lookup"><span data-stu-id="0816b-333">a.</span></span> <span data-ttu-id="0816b-334">单击 **"开始**"，键入 **cmd**，然后按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="0816b-334">Click **Start**, type **cmd**, and press **Enter**.</span></span>

   <span data-ttu-id="0816b-335">b.</span><span class="sxs-lookup"><span data-stu-id="0816b-335">b.</span></span> <span data-ttu-id="0816b-336">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="0816b-336">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="0816b-337">输入以下命令，然后按 **Enter：**</span><span class="sxs-lookup"><span data-stu-id="0816b-337">Enter the following command, and press **Enter**:</span></span>

   ```text
   sc qc diagtrack
   ```

   <span data-ttu-id="0816b-338">如果服务已启用，则结果应如以下屏幕截图所示：</span><span class="sxs-lookup"><span data-stu-id="0816b-338">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![diagtrack 的 sc 查询命令的结果](images/windefatp-sc-qc-diagtrack.png)

   <span data-ttu-id="0816b-340">如果未设置为 ，则需要将服务设置为 `START_TYPE` `AUTO_START` 自动启动。</span><span class="sxs-lookup"><span data-stu-id="0816b-340">If the `START_TYPE` is not set to `AUTO_START`, then you'll need to set the service to automatically start.</span></span>

<span data-ttu-id="0816b-341">**使用命令行将 Windows 10数据服务设置为自动启动：**</span><span class="sxs-lookup"><span data-stu-id="0816b-341">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1. <span data-ttu-id="0816b-342">在设备上打开提升的命令行提示符：</span><span class="sxs-lookup"><span data-stu-id="0816b-342">Open an elevated command-line prompt on the device:</span></span>

   <span data-ttu-id="0816b-343">a.</span><span class="sxs-lookup"><span data-stu-id="0816b-343">a.</span></span> <span data-ttu-id="0816b-344">单击 **"开始**"，键入 **cmd**，然后按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="0816b-344">Click **Start**, type **cmd**, and press **Enter**.</span></span>

   <span data-ttu-id="0816b-345">b.</span><span class="sxs-lookup"><span data-stu-id="0816b-345">b.</span></span> <span data-ttu-id="0816b-346">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="0816b-346">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="0816b-347">输入以下命令，然后按 **Enter：**</span><span class="sxs-lookup"><span data-stu-id="0816b-347">Enter the following command, and press **Enter**:</span></span>

   ```text
   sc config diagtrack start=auto
   ```

3. <span data-ttu-id="0816b-348">将显示成功消息。</span><span class="sxs-lookup"><span data-stu-id="0816b-348">A success message is displayed.</span></span> <span data-ttu-id="0816b-349">通过输入以下命令验证更改，然后按 **Enter：**</span><span class="sxs-lookup"><span data-stu-id="0816b-349">Verify the change by entering the following command, and press **Enter**:</span></span>

   ```text
   sc qc diagtrack
   ```

4. <span data-ttu-id="0816b-350">启动服务。</span><span class="sxs-lookup"><span data-stu-id="0816b-350">Start the service.</span></span>

   <span data-ttu-id="0816b-351">a.</span><span class="sxs-lookup"><span data-stu-id="0816b-351">a.</span></span> <span data-ttu-id="0816b-352">在命令提示符中，键入以下命令并按 **Enter：**</span><span class="sxs-lookup"><span data-stu-id="0816b-352">In the command prompt, type the following command and press **Enter**:</span></span>

   ```text
   sc start diagtrack
   ```

### <a name="ensure-the-device-has-an-internet-connection"></a><span data-ttu-id="0816b-353">确保设备具有 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="0816b-353">Ensure the device has an Internet connection</span></span>

<span data-ttu-id="0816b-354">Microsoft Defender for Endpoint 感官方案需要 Microsoft Windows HTTP （WinHTTP） 报告感官数据，并与 Microsoft Defender for Endpoint 服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="0816b-354">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="0816b-355">WinHTTP 独立于 Internet 浏览代理设置和其他用户上下文应用程序，必须能够检测特定环境中可用的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="0816b-355">WinHTTP is independent of the Internet browsing proxy settings and other user context applications and must be able to detect the proxy servers that are available in your particular environment.</span></span>

<span data-ttu-id="0816b-356">若要确保传感器具有服务连接，请按照验证客户端与 Microsoft [Defender for Endpoint 服务 URL](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls) 的连接主题中所述的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="0816b-356">To ensure that sensor has service connectivity, follow the steps described in the [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls) topic.</span></span>

<span data-ttu-id="0816b-357">如果验证失败，并且您的环境正在使用代理连接到 Internet，请按照配置代理和 Internet 连接设置主题 [中所述](configure-proxy-internet.md) 的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="0816b-357">If the verification fails and your environment is using a proxy to connect to the Internet, then follow the steps described in [Configure proxy and Internet connectivity settings](configure-proxy-internet.md) topic.</span></span>

### <a name="ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy"></a><span data-ttu-id="0816b-358">确保Microsoft Defender 防病毒策略未禁用此策略</span><span class="sxs-lookup"><span data-stu-id="0816b-358">Ensure that Microsoft Defender Antivirus is not disabled by a policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0816b-359">以下仅适用于尚未收到 2020年 8 月 (版本 4.18.2007.8) 更新的设备Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="0816b-359">The following only applies to devices that have **not** yet received the August 2020 (version 4.18.2007.8) update to Microsoft Defender Antivirus.</span></span>
>
> <span data-ttu-id="0816b-360">更新可确保Microsoft Defender 防病毒策略在客户端设备上关闭此配置。</span><span class="sxs-lookup"><span data-stu-id="0816b-360">The update ensures that Microsoft Defender Antivirus cannot be turned off on client devices via system policy.</span></span>

<span data-ttu-id="0816b-361">**问题**：载入后 Microsoft Defender for Endpoint 服务未启动。</span><span class="sxs-lookup"><span data-stu-id="0816b-361">**Problem**: The Microsoft Defender for Endpoint service does not start after onboarding.</span></span>

<span data-ttu-id="0816b-362">**症状**：载入成功完成，但在尝试启动服务时看到错误 577 或错误 1058。</span><span class="sxs-lookup"><span data-stu-id="0816b-362">**Symptom**: Onboarding successfully completes, but you see error 577 or error 1058 when trying to start the service.</span></span>

<span data-ttu-id="0816b-363">**解决方案**：如果你的设备正在运行第三方反恶意软件客户端，Microsoft Defender for Endpoint 代理需要启用"提前启动反恶意软件 (ELAM) 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="0816b-363">**Solution**: If your devices are running a third-party antimalware client, the Microsoft Defender for Endpoint agent needs the Early Launch Antimalware (ELAM) driver to be enabled.</span></span> <span data-ttu-id="0816b-364">必须确保系统策略未将其关闭。</span><span class="sxs-lookup"><span data-stu-id="0816b-364">You must ensure that it's not turned off by a system policy.</span></span>

- <span data-ttu-id="0816b-365">根据用于实现策略的工具，需要验证是否清除以下Windows Defender策略：</span><span class="sxs-lookup"><span data-stu-id="0816b-365">Depending on the tool that you use to implement policies, you'll need to verify that the following Windows Defender policies are cleared:</span></span>

  - <span data-ttu-id="0816b-366">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="0816b-366">DisableAntiSpyware</span></span>
  - <span data-ttu-id="0816b-367">DisableAntiVirus</span><span class="sxs-lookup"><span data-stu-id="0816b-367">DisableAntiVirus</span></span>

  <span data-ttu-id="0816b-368">例如，在组策略中，应该没有诸如以下值这样的条目：</span><span class="sxs-lookup"><span data-stu-id="0816b-368">For example, in Group Policy there should be no entries such as the following values:</span></span>

  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiSpyware"/></Key>`
  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiVirus"/></Key>`

> [!IMPORTANT]
> <span data-ttu-id="0816b-369">从 2020 年 8 月 (版本 4.18.2007.8 开始，该设置将停止使用，并且将在所有客户端设备上) 更新到 `disableAntiSpyware` Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="0816b-369">The `disableAntiSpyware` setting is discontinued and will be ignored on all client devices, as of the August 2020 (version 4.18.2007.8) update to Microsoft Defender Antivirus.</span></span>

- <span data-ttu-id="0816b-370">清除策略后，再次运行载入步骤。</span><span class="sxs-lookup"><span data-stu-id="0816b-370">After clearing the policy, run the onboarding steps again.</span></span>

- <span data-ttu-id="0816b-371">您还可以通过打开注册表项来检查以前的注册表项值，以验证策略是否被禁用 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` 。</span><span class="sxs-lookup"><span data-stu-id="0816b-371">You can also check the previous registry key values to verify that the policy is disabled, by opening the registry key `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.</span></span>

    ![注册表项的图像Microsoft Defender 防病毒](images/atp-disableantispyware-regkey.png)

   > [!NOTE]
   > <span data-ttu-id="0816b-373">Windows Defender wdboot (wdboot、wdfilter、wdnisdrv、wdnissvc 和 windefend) 所有服务都应在默认状态下。</span><span class="sxs-lookup"><span data-stu-id="0816b-373">All Windows Defender services (wdboot, wdfilter, wdnisdrv, wdnissvc, and windefend) should be in their default state.</span></span> <span data-ttu-id="0816b-374">更改这些服务的启动不受支持，可能会强制你重新映像系统。</span><span class="sxs-lookup"><span data-stu-id="0816b-374">Changing the startup of these services is unsupported and may force you to reimage your system.</span></span>
   >
   > <span data-ttu-id="0816b-375">WdBoot 和 WdFilter 的默认配置示例：</span><span class="sxs-lookup"><span data-stu-id="0816b-375">Example default configurations for WdBoot and WdFilter:</span></span>
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdBoot"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdFilter"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`

## <a name="troubleshoot-onboarding-issues-on-a-server"></a><span data-ttu-id="0816b-376">在服务器上载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="0816b-376">Troubleshoot onboarding issues on a server</span></span>

<span data-ttu-id="0816b-377">如果在载入服务器时遇到问题，请执行以下验证步骤来解决可能的问题。</span><span class="sxs-lookup"><span data-stu-id="0816b-377">If you encounter issues while onboarding a server, go through the following verification steps to address possible issues.</span></span>

- [<span data-ttu-id="0816b-378">确保Microsoft Monitoring Agent (MMA) 并配置为向服务报告传感器数据</span><span class="sxs-lookup"><span data-stu-id="0816b-378">Ensure Microsoft Monitoring Agent (MMA) is installed and configured to report sensor data to the service</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="0816b-379">确保正确配置服务器代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="0816b-379">Ensure that the server proxy and Internet connectivity settings are configured properly</span></span>](configure-server-endpoints.md)

<span data-ttu-id="0816b-380">您可能还需要检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="0816b-380">You might also need to check the following:</span></span>

- <span data-ttu-id="0816b-381">检查在任务管理器 的"进程"选项卡中是否正在运行适用于 Endpoint Service 的 Microsoft **Defender。**</span><span class="sxs-lookup"><span data-stu-id="0816b-381">Check that there is a Microsoft Defender for Endpoint Service running in the **Processes** tab in **Task Manager**.</span></span> <span data-ttu-id="0816b-382">例如：</span><span class="sxs-lookup"><span data-stu-id="0816b-382">For example:</span></span>

    ![运行 Microsoft Defender for Endpoint Service 的进程视图的图像](images/atp-task-manager.png)

- <span data-ttu-id="0816b-384">检查 **事件**  >  **查看器应用程序和服务日志**  >  **操作管理器**，以查看是否有错误。</span><span class="sxs-lookup"><span data-stu-id="0816b-384">Check **Event Viewer** > **Applications and Services Logs** > **Operation Manager** to see if there are any errors.</span></span>

- <span data-ttu-id="0816b-385">在 **"** 服务"**中，Microsoft Monitoring Agent** 服务器是否在服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="0816b-385">In **Services**, check if the **Microsoft Monitoring Agent** is running on the server.</span></span> <span data-ttu-id="0816b-386">例如，</span><span class="sxs-lookup"><span data-stu-id="0816b-386">For example,</span></span>

    ![服务的图像](images/atp-services.png)

- <span data-ttu-id="0816b-388">In **Microsoft Monitoring Agent**  >  **Azure Log Analytics (OMS) ，** check the Workspaces and verify that the status is running.</span><span class="sxs-lookup"><span data-stu-id="0816b-388">In **Microsoft Monitoring Agent** > **Azure Log Analytics (OMS)**, check the Workspaces and verify that the status is running.</span></span>

    ![属性Microsoft Monitoring Agent图像](images/atp-mma-properties.png)

- <span data-ttu-id="0816b-390">检查设备是否反映在门户中的 **"设备"** 列表中。</span><span class="sxs-lookup"><span data-stu-id="0816b-390">Check to see that devices are reflected in the **Devices list** in the portal.</span></span>

## <a name="confirming-onboarding-of-newly-built-devices"></a><span data-ttu-id="0816b-391">确认新构建设备的载入</span><span class="sxs-lookup"><span data-stu-id="0816b-391">Confirming onboarding of newly built devices</span></span>

<span data-ttu-id="0816b-392">在新构建的设备上部署载入时，可能会存在一些实例，但未完成。</span><span class="sxs-lookup"><span data-stu-id="0816b-392">There may be instances when onboarding is deployed on a newly built device but not completed.</span></span>

<span data-ttu-id="0816b-393">以下步骤为以下方案提供指导：</span><span class="sxs-lookup"><span data-stu-id="0816b-393">The steps below provide guidance for the following scenario:</span></span>

- <span data-ttu-id="0816b-394">载入包部署到新构建的设备</span><span class="sxs-lookup"><span data-stu-id="0816b-394">Onboarding package is deployed to newly built devices</span></span>
- <span data-ttu-id="0816b-395">传感器未启动，因为尚未完成 (OOBE) 或第一个用户登录</span><span class="sxs-lookup"><span data-stu-id="0816b-395">Sensor does not start because the Out-of-box experience (OOBE) or first user logon has not been completed</span></span>
- <span data-ttu-id="0816b-396">在最终用户执行第一次登录之前，设备已关闭或重新启动</span><span class="sxs-lookup"><span data-stu-id="0816b-396">Device is turned off or restarted before the end user performs a first logon</span></span>
- <span data-ttu-id="0816b-397">在此方案中，SENSE 服务不会自动启动，即使已部署载入包</span><span class="sxs-lookup"><span data-stu-id="0816b-397">In this scenario, the SENSE service will not start automatically even though onboarding package was deployed</span></span>

<div class="alert"><span data-ttu-id="0816b-398"><b>注意：</b>OOBE 后的用户登录不再需要 SENSE 服务启动以下或更新的 Windows 版本：Windows 10 版本 1809 或 Windows Server 2019（[包含 2021](https://support.microsoft.com/kb/5001384)年 4 月 22 日更新汇总） </span><span class="sxs-lookup"><span data-stu-id="0816b-398"><b>NOTE:</b> User Logon after OOBE is no longer required for SENSE service to start on the following or more recent Windows versions: Windows 10, version 1809 or Windows Server 2019 with [April 22 2021 update rollup](https://support.microsoft.com/kb/5001384) </span></span></br> <span data-ttu-id="0816b-399">Windows 10 2021 年 4 月更新汇总的版本[1909](https://support.microsoft.com/kb/5001396) </span><span class="sxs-lookup"><span data-stu-id="0816b-399">Windows 10, version 1909 with [April 2021 update rollup](https://support.microsoft.com/kb/5001396) </span></span></br> <span data-ttu-id="0816b-400">Windows 10 2021 年 4 月 28 日更新汇总的[2004/20H2 版本](https://support.microsoft.com/kb/5001391) </span><span class="sxs-lookup"><span data-stu-id="0816b-400">Windows 10, version 2004/20H2 with [April 28 2021 update rollup](https://support.microsoft.com/kb/5001391) </span></span></div> 
<br></br>
> [!NOTE]
> <span data-ttu-id="0816b-401">以下步骤仅在使用 Microsoft Endpoint Configuration Manager 时Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="0816b-401">The following steps are only relevant when using Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="0816b-402">有关使用应用载入的Microsoft Endpoint Configuration Manager，请参阅[Microsoft Defender for Endpoint](/mem/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="0816b-402">For more details about onboarding using Microsoft Endpoint Configuration Manager, see [Microsoft Defender for Endpoint](/mem/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection).</span></span>

1. <span data-ttu-id="0816b-403">在应用程序中创建Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="0816b-403">Create an application in Microsoft Endpoint Configuration Manager.</span></span>

    ![配置Microsoft Endpoint Configuration Manager图像1](images/mecm-1.png)

2. <span data-ttu-id="0816b-405">选择 **"手动指定应用程序信息"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-405">Select **Manually specify the application information**.</span></span>

    ![Microsoft Endpoint Configuration Manager配置 2 的图像](images/mecm-2.png)

3. <span data-ttu-id="0816b-407">指定有关应用程序的信息，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-407">Specify information about the application, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager配置的图像3](images/mecm-3.png)

4. <span data-ttu-id="0816b-409">指定有关软件中心的信息，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-409">Specify information about the software center, then select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager的图像4](images/mecm-4.png)

5. <span data-ttu-id="0816b-411">在 **"部署类型"中，** 选择"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-411">In **Deployment types** select **Add**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager的图像5](images/mecm-5.png)

6. <span data-ttu-id="0816b-413">选择 **"手动指定部署类型信息"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-413">Select **Manually specify the deployment type information**, then select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager图像6](images/mecm-6.png)

7. <span data-ttu-id="0816b-415">指定有关部署类型的信息，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-415">Specify information about the deployment type, then select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager映像7](images/mecm-7.png)

8. <span data-ttu-id="0816b-417">在 **内容**  >  **安装程序中**，指定命令 `net start sense` ：。</span><span class="sxs-lookup"><span data-stu-id="0816b-417">In **Content** > **Installation program** specify the command: `net start sense`.</span></span>

    ![配置Microsoft Endpoint Configuration Manager的图像8](images/mecm-8.png)

9. <span data-ttu-id="0816b-419">在 **检测方法** 中，**选择"配置规则以检测此部署类型是否存在"，** 然后选择"**添加子句"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-419">In **Detection method**, select **Configure rules to detect the presence of this deployment type**, then select **Add Clause**.</span></span>

    ![Microsoft Endpoint Configuration Manager配置9 的图像](images/mecm-9.png)

10. <span data-ttu-id="0816b-421">指定以下检测规则详细信息，然后选择"确定 **"：**</span><span class="sxs-lookup"><span data-stu-id="0816b-421">Specify the following detection rule details, then select **OK**:</span></span>

    ![Microsoft Endpoint Configuration Manager配置10 的图像](images/mecm-10.png)

11. <span data-ttu-id="0816b-423">在 **"检测方法"中，** 选择"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-423">In **Detection method** select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager图像11](images/mecm-11.png)

12. <span data-ttu-id="0816b-425">在 **"用户体验"** 中，指定以下信息，然后选择"下一 **步"：**</span><span class="sxs-lookup"><span data-stu-id="0816b-425">In **User Experience**, specify the following information, then select **Next**:</span></span>

    ![Microsoft Endpoint Configuration Manager configuration12 的图像](images/mecm-12.png)

13. <span data-ttu-id="0816b-427">在 **"要求"** 中，选择"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-427">In **Requirements**, select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager图像13](images/mecm-13.png)

14. <span data-ttu-id="0816b-429">在 **"依赖项"中**，选择"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-429">In **Dependencies**, select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager的图像14](images/mecm-14.png)

15. <span data-ttu-id="0816b-431">在 **"摘要"中**，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-431">In **Summary**, select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager图像15](images/mecm-15.png)

16. <span data-ttu-id="0816b-433">在 **"完成"** 中，选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-433">In **Completion**, select **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager配置16 的图像](images/mecm-16.png)

17. <span data-ttu-id="0816b-435">在 **"部署类型"中**，选择"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-435">In **Deployment types**, select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager配置17 的图像](images/mecm-17.png)

18. <span data-ttu-id="0816b-437">在 **"摘要"中**，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-437">In **Summary**, select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager图像18](images/mecm-18.png)

    <span data-ttu-id="0816b-439">然后显示状态： ![ 配置Microsoft Endpoint Configuration Manager图像19](images/mecm-19.png)</span><span class="sxs-lookup"><span data-stu-id="0816b-439">The status is then displayed: ![Image of Microsoft Endpoint Configuration Manager configuration19](images/mecm-19.png)</span></span>

19. <span data-ttu-id="0816b-440">在 **"完成"** 中，选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-440">In **Completion**, select **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager配置20 的图像](images/mecm-20.png)

20. <span data-ttu-id="0816b-442">现在，可以通过右键单击应用并选择部署 来部署 **应用程序**。</span><span class="sxs-lookup"><span data-stu-id="0816b-442">You can now deploy the application by right-clicking the app and selecting **Deploy**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager的图像21](images/mecm-21.png)

21. <span data-ttu-id="0816b-444">在 **"常规\*\*\*\*"中，选择"自动分配依赖项的内容"和"\*\*\*\*浏览"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-444">In **General** select **Automatically distribute content for dependencies** and **Browse**.</span></span>

    ![Microsoft Endpoint Configuration Manager配置22 的图像](images/mecm-22.png)

22. <span data-ttu-id="0816b-446">在 **"内容"中**，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-446">In **Content** select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager的图像23](images/mecm-23.png)

23. <span data-ttu-id="0816b-448">在 **"部署设置"中**，选择"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-448">In **Deployment settings**, select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager的图像24](images/mecm-24.png)

24. <span data-ttu-id="0816b-450">在 **"计划"** 中 **，选择"在可用时间后尽快"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-450">In **Scheduling** select **As soon as possible after the available time**, then select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager的图像25](images/mecm-25.png)

25. <span data-ttu-id="0816b-452">在 **用户体验中，** 选择"在截止时间或维护时段内提交更改 (需要重新启动) ，然后选择"下 **一\*\*\*\*步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-452">In **User experience**, select **Commit changes at deadline or during a maintenance window (requires restarts)**, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager配置26 的图像](images/mecm-26.png)

26. <span data-ttu-id="0816b-454">在 **警报中选择下** 一 **步**。</span><span class="sxs-lookup"><span data-stu-id="0816b-454">In **Alerts** select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager的图像27](images/mecm-27.png)

27. <span data-ttu-id="0816b-456">在 **"摘要"中**，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-456">In **Summary**, select **Next**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager的图像28](images/mecm-28.png)

    <span data-ttu-id="0816b-458">然后显示状态"配置 ![ Microsoft Endpoint Configuration Manager图像29](images/mecm-29.png)</span><span class="sxs-lookup"><span data-stu-id="0816b-458">The status is then displayed ![Image of Microsoft Endpoint Configuration Manager configuration29](images/mecm-29.png)</span></span>

28. <span data-ttu-id="0816b-459">在 **"完成"** 中，选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="0816b-459">In **Completion**, select **Close**.</span></span>

    ![配置Microsoft Endpoint Configuration Manager的图像30](images/mecm-30.png)


## <a name="related-topics"></a><span data-ttu-id="0816b-461">相关主题</span><span class="sxs-lookup"><span data-stu-id="0816b-461">Related topics</span></span>

- [<span data-ttu-id="0816b-462">Microsoft Defender for Endpoint 疑难解答</span><span class="sxs-lookup"><span data-stu-id="0816b-462">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-mdatp.md)
- [<span data-ttu-id="0816b-463">载入设备</span><span class="sxs-lookup"><span data-stu-id="0816b-463">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="0816b-464">配置设备代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="0816b-464">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
