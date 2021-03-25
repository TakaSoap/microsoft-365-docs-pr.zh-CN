---
title: 在 Microsoft Defender ATP 中调查使用实时响应的设备上的实体
description: 使用安全的远程 Shell 连接访问设备，以执行调查工作，并实时对设备执行即时响应操作。
keywords: 远程， shell， 连接， 实时， 响应， 实时， 命令， 脚本， 修正， 搜寻， 导出， 日志， 拖放， 下载， 文件，
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
ms.openlocfilehash: 784e73467efc114f05ebdfca9bc4034e2d75f6c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185703"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="a1961-104">使用实时响应调查设备上的实体</span><span class="sxs-lookup"><span data-stu-id="a1961-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a1961-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a1961-105">**Applies to:**</span></span>
- [<span data-ttu-id="a1961-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a1961-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a1961-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1961-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="a1961-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="a1961-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a1961-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a1961-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a1961-110">实时响应使安全运营团队能够即时访问 (也称为计算机) 使用远程 shell 连接的设备。</span><span class="sxs-lookup"><span data-stu-id="a1961-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="a1961-111">这让你能够实时执行深入调查工作，并立即采取响应操作，以迅速包含识别的威胁。</span><span class="sxs-lookup"><span data-stu-id="a1961-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="a1961-112">实时响应旨在增强调查，使安全运营团队能够收集取证数据、运行脚本、发送可疑实体进行分析、修正威胁并主动搜寻新出现的威胁。</span><span class="sxs-lookup"><span data-stu-id="a1961-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="a1961-113">使用实时响应，分析员可以执行以下所有任务：</span><span class="sxs-lookup"><span data-stu-id="a1961-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="a1961-114">运行基本和高级命令以在设备上执行调查工作。</span><span class="sxs-lookup"><span data-stu-id="a1961-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="a1961-115">下载恶意软件示例和 PowerShell 脚本结果等文件。</span><span class="sxs-lookup"><span data-stu-id="a1961-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="a1961-116">在后台下载新 (！) 。</span><span class="sxs-lookup"><span data-stu-id="a1961-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="a1961-117">将 PowerShell 脚本或可执行文件上传到库，然后从租户级别在设备上运行它。</span><span class="sxs-lookup"><span data-stu-id="a1961-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="a1961-118">执行或撤消修正操作。</span><span class="sxs-lookup"><span data-stu-id="a1961-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a1961-119">准备工作</span><span class="sxs-lookup"><span data-stu-id="a1961-119">Before you begin</span></span>

<span data-ttu-id="a1961-120">在设备上启动会话之前，请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="a1961-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="a1961-121">**验证你运行的是受支持的 Windows 版本**。</span><span class="sxs-lookup"><span data-stu-id="a1961-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="a1961-122">设备必须运行以下 Windows 版本之一</span><span class="sxs-lookup"><span data-stu-id="a1961-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="a1961-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="a1961-123">**Windows 10**</span></span>
    - <span data-ttu-id="a1961-124">[版本 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="a1961-124">[Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="a1961-125">[版本 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) [和 KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="a1961-125">[Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="a1961-126">[版本 1809 (RS 5 ](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)) [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="a1961-126">[Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="a1961-127">[版本 1803 (RS 4) ](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="a1961-127">[Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="a1961-128">[版本 1709 (RS 3) ](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="a1961-128">[Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="a1961-129">**Windows Server 2019 - 仅适用于公共预览版**</span><span class="sxs-lookup"><span data-stu-id="a1961-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="a1961-130">版本 1903 或 ([KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384) 版本) 更高版本</span><span class="sxs-lookup"><span data-stu-id="a1961-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="a1961-131">版本 1809 ([KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818)) </span><span class="sxs-lookup"><span data-stu-id="a1961-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="a1961-132">**从高级设置页面启用实时响应**。</span><span class="sxs-lookup"><span data-stu-id="a1961-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="a1961-133">你需要在"高级功能设置"页中启用 [实时响应](advanced-features.md) 功能。</span><span class="sxs-lookup"><span data-stu-id="a1961-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="a1961-134">只有具有管理安全性或全局管理员角色的用户才能编辑这些设置。</span><span class="sxs-lookup"><span data-stu-id="a1961-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="a1961-135">**从高级设置页面启用服务器** 实时响应 (推荐) 。</span><span class="sxs-lookup"><span data-stu-id="a1961-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="a1961-136">只有具有管理安全性或全局管理员角色的用户才能编辑这些设置。</span><span class="sxs-lookup"><span data-stu-id="a1961-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="a1961-137">**确保设备具有分配给它的自动化修正级别**。</span><span class="sxs-lookup"><span data-stu-id="a1961-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="a1961-138">你至少需要启用给定设备组的最低修正级别。</span><span class="sxs-lookup"><span data-stu-id="a1961-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="a1961-139">否则，将无法与该组的成员建立实时响应会话。</span><span class="sxs-lookup"><span data-stu-id="a1961-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="a1961-140">您将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="a1961-140">You'll receive the following error:</span></span>

    ![错误消息的图像](images/live-response-error.png)

- <span data-ttu-id="a1961-142">**启用实时响应未签名脚本执行 (** 可选) 。</span><span class="sxs-lookup"><span data-stu-id="a1961-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="a1961-143">允许使用未签名脚本可能会增加你面临的威胁。</span><span class="sxs-lookup"><span data-stu-id="a1961-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="a1961-144">不建议运行未签名的脚本，因为它会增加你面临的威胁。</span><span class="sxs-lookup"><span data-stu-id="a1961-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="a1961-145">但是，如果必须使用这些功能，则需要在"高级功能设置"页 [中启用设置](advanced-features.md) 。</span><span class="sxs-lookup"><span data-stu-id="a1961-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="a1961-146">**确保您具有适当的权限**。</span><span class="sxs-lookup"><span data-stu-id="a1961-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="a1961-147">只有已预配了相应权限的用户才能启动会话。</span><span class="sxs-lookup"><span data-stu-id="a1961-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="a1961-148">有关角色分配详细信息，请参阅 [创建和管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a1961-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="a1961-149">将文件上载到库的选项仅适用于具有相应 RBAC 权限的用户。</span><span class="sxs-lookup"><span data-stu-id="a1961-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="a1961-150">对于仅具有委派权限的用户，按钮显示为灰色。</span><span class="sxs-lookup"><span data-stu-id="a1961-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="a1961-151">根据已授予的角色，可以运行基本或高级实时响应命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="a1961-152">用户权限由 RBAC 自定义角色控制。</span><span class="sxs-lookup"><span data-stu-id="a1961-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="a1961-153">实时响应仪表板概述</span><span class="sxs-lookup"><span data-stu-id="a1961-153">Live response dashboard overview</span></span>
<span data-ttu-id="a1961-154">在设备上启动实时响应会话时，将打开仪表板。</span><span class="sxs-lookup"><span data-stu-id="a1961-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="a1961-155">仪表板提供有关会话的信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a1961-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="a1961-156">创建会话的人</span><span class="sxs-lookup"><span data-stu-id="a1961-156">Who created the session</span></span>
- <span data-ttu-id="a1961-157">会话开始时间</span><span class="sxs-lookup"><span data-stu-id="a1961-157">When the session started</span></span>
- <span data-ttu-id="a1961-158">会话的持续时间</span><span class="sxs-lookup"><span data-stu-id="a1961-158">The duration of the session</span></span>

<span data-ttu-id="a1961-159">通过仪表板还可以访问：</span><span class="sxs-lookup"><span data-stu-id="a1961-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="a1961-160">断开会话连接</span><span class="sxs-lookup"><span data-stu-id="a1961-160">Disconnect session</span></span>
- <span data-ttu-id="a1961-161">将文件上载到库</span><span class="sxs-lookup"><span data-stu-id="a1961-161">Upload files to the library</span></span> 
- <span data-ttu-id="a1961-162">命令控制台</span><span class="sxs-lookup"><span data-stu-id="a1961-162">Command console</span></span>
- <span data-ttu-id="a1961-163">命令日志</span><span class="sxs-lookup"><span data-stu-id="a1961-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="a1961-164">在设备上启动实时响应会话</span><span class="sxs-lookup"><span data-stu-id="a1961-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="a1961-165">登录到 Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="a1961-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="a1961-166">导航到设备列表页面，然后选择要调查的设备。</span><span class="sxs-lookup"><span data-stu-id="a1961-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="a1961-167">设备页面将打开。</span><span class="sxs-lookup"><span data-stu-id="a1961-167">The devices page opens.</span></span>

3. <span data-ttu-id="a1961-168">通过选择"启动实时响应会话 **"启动实时响应会话**。</span><span class="sxs-lookup"><span data-stu-id="a1961-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="a1961-169">将显示命令控制台。</span><span class="sxs-lookup"><span data-stu-id="a1961-169">A command console is displayed.</span></span> <span data-ttu-id="a1961-170">在会话连接到设备时等待。</span><span class="sxs-lookup"><span data-stu-id="a1961-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="a1961-171">使用内置命令执行调查工作。</span><span class="sxs-lookup"><span data-stu-id="a1961-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="a1961-172">有关详细信息，请参阅实时 [响应命令](#live-response-commands)。</span><span class="sxs-lookup"><span data-stu-id="a1961-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="a1961-173">完成调查后，选择"断开连接 **会话"，** 然后选择"确认 **"。**</span><span class="sxs-lookup"><span data-stu-id="a1961-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="a1961-174">实时响应命令</span><span class="sxs-lookup"><span data-stu-id="a1961-174">Live response commands</span></span>

<span data-ttu-id="a1961-175">根据已授予的角色，可以运行基本或高级实时响应命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="a1961-176">用户权限由 RBAC 自定义角色控制。</span><span class="sxs-lookup"><span data-stu-id="a1961-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="a1961-177">有关角色分配详细信息，请参阅 [创建和管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a1961-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="a1961-178">实时响应是基于云的交互式 Shell，因此，特定命令体验在响应时间上可能会有所不同，具体取决于最终用户和目标设备之间的网络质量和系统负载。</span><span class="sxs-lookup"><span data-stu-id="a1961-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="a1961-179">基本命令</span><span class="sxs-lookup"><span data-stu-id="a1961-179">Basic commands</span></span>

<span data-ttu-id="a1961-180">以下命令适用于被授予运行基本实时响应 **命令的能力的用户** 角色。</span><span class="sxs-lookup"><span data-stu-id="a1961-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="a1961-181">有关角色分配详细信息，请参阅 [创建和管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a1961-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="a1961-182">命令</span><span class="sxs-lookup"><span data-stu-id="a1961-182">Command</span></span> | <span data-ttu-id="a1961-183">说明</span><span class="sxs-lookup"><span data-stu-id="a1961-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="a1961-184">更改当前目录。</span><span class="sxs-lookup"><span data-stu-id="a1961-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="a1961-185">清除控制台屏幕。</span><span class="sxs-lookup"><span data-stu-id="a1961-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="a1961-186">启动到设备的实时响应会话。</span><span class="sxs-lookup"><span data-stu-id="a1961-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="a1961-187">显示所有活动连接。</span><span class="sxs-lookup"><span data-stu-id="a1961-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="a1961-188">显示目录中的文件和子目录的列表。</span><span class="sxs-lookup"><span data-stu-id="a1961-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`download <file_path> &` | <span data-ttu-id="a1961-189">在后台下载文件。</span><span class="sxs-lookup"><span data-stu-id="a1961-189">Downloads a file in the background.</span></span> |
<span data-ttu-id="a1961-190">drivers</span><span class="sxs-lookup"><span data-stu-id="a1961-190">drivers</span></span> |  <span data-ttu-id="a1961-191">显示设备上安装的所有驱动程序。</span><span class="sxs-lookup"><span data-stu-id="a1961-191">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="a1961-192">返回文件下载到前台。</span><span class="sxs-lookup"><span data-stu-id="a1961-192">Returns a file download to the foreground.</span></span> |
|`fileinfo` | <span data-ttu-id="a1961-193">获取有关文件的信息。</span><span class="sxs-lookup"><span data-stu-id="a1961-193">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="a1961-194">在设备上按给定名称查找文件。</span><span class="sxs-lookup"><span data-stu-id="a1961-194">Locates files by a given name on the device.</span></span> |
|`help` | <span data-ttu-id="a1961-195">提供实时响应命令的帮助信息。</span><span class="sxs-lookup"><span data-stu-id="a1961-195">Provides help information for live response commands.</span></span> |
|`persistence` | <span data-ttu-id="a1961-196">显示设备上所有已知的持久性方法。</span><span class="sxs-lookup"><span data-stu-id="a1961-196">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="a1961-197">显示设备上运行的所有进程。</span><span class="sxs-lookup"><span data-stu-id="a1961-197">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="a1961-198">显示注册表值。</span><span class="sxs-lookup"><span data-stu-id="a1961-198">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="a1961-199">显示设备上的所有计划任务。</span><span class="sxs-lookup"><span data-stu-id="a1961-199">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="a1961-200">显示设备上的所有服务。</span><span class="sxs-lookup"><span data-stu-id="a1961-200">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="a1961-201">将终端的日志记录模式设置为调试。</span><span class="sxs-lookup"><span data-stu-id="a1961-201">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="a1961-202">高级命令</span><span class="sxs-lookup"><span data-stu-id="a1961-202">Advanced commands</span></span>
<span data-ttu-id="a1961-203">以下命令适用于被授予运行高级实时响应 **命令权限的用户** 角色。</span><span class="sxs-lookup"><span data-stu-id="a1961-203">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="a1961-204">有关角色分配详细信息，请参阅 [创建和管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a1961-204">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="a1961-205">命令</span><span class="sxs-lookup"><span data-stu-id="a1961-205">Command</span></span> | <span data-ttu-id="a1961-206">说明</span><span class="sxs-lookup"><span data-stu-id="a1961-206">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="a1961-207">使用各种描述引擎分析实体以作出裁定。</span><span class="sxs-lookup"><span data-stu-id="a1961-207">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `getfile` | <span data-ttu-id="a1961-208">从设备获取文件。</span><span class="sxs-lookup"><span data-stu-id="a1961-208">Gets a file from the device.</span></span> <br> <span data-ttu-id="a1961-209">注意：此命令具有先决条件命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-209">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="a1961-210">可以将 命令 `-auto` 与 结合使用 `getfile` 来自动运行必备组件命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-210">You can use the `-auto` command in conjunction with `getfile` to automatically run the prerequisite command.</span></span> |
| `run` | <span data-ttu-id="a1961-211">从设备的库中运行 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="a1961-211">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="a1961-212">列出上载到实时响应库的文件。</span><span class="sxs-lookup"><span data-stu-id="a1961-212">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="a1961-213">将库中的文件置于设备。</span><span class="sxs-lookup"><span data-stu-id="a1961-213">Puts a file from the library to the device.</span></span> <span data-ttu-id="a1961-214">文件保存在工作文件夹中，在设备默认重启时将被删除。</span><span class="sxs-lookup"><span data-stu-id="a1961-214">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="a1961-215">修正设备上的实体。</span><span class="sxs-lookup"><span data-stu-id="a1961-215">Remediates an entity on the device.</span></span> <span data-ttu-id="a1961-216">修正操作因实体类型而异：</span><span class="sxs-lookup"><span data-stu-id="a1961-216">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="a1961-217">- 文件：删除</span><span class="sxs-lookup"><span data-stu-id="a1961-217">- File: delete</span></span><br><span data-ttu-id="a1961-218">- 进程：停止、删除图像文件</span><span class="sxs-lookup"><span data-stu-id="a1961-218">- Process: stop, delete image file</span></span><br><span data-ttu-id="a1961-219">- 服务：停止、删除图像文件</span><span class="sxs-lookup"><span data-stu-id="a1961-219">- Service: stop, delete image file</span></span><br><span data-ttu-id="a1961-220">- 注册表项：删除</span><span class="sxs-lookup"><span data-stu-id="a1961-220">- Registry entry: delete</span></span><br><span data-ttu-id="a1961-221">- 计划任务：删除</span><span class="sxs-lookup"><span data-stu-id="a1961-221">- Scheduled task: remove</span></span><br><span data-ttu-id="a1961-222">- 启动文件夹项：删除文件</span><span class="sxs-lookup"><span data-stu-id="a1961-222">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="a1961-223">注意：此命令具有先决条件命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-223">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="a1961-224">可以将 命令 `-auto` 与 结合使用 `remediate` 来自动运行必备组件命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-224">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="a1961-225">还原已修正的实体。</span><span class="sxs-lookup"><span data-stu-id="a1961-225">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="a1961-226">使用实时响应命令</span><span class="sxs-lookup"><span data-stu-id="a1961-226">Use live response commands</span></span>

<span data-ttu-id="a1961-227">控制台中可以使用的命令遵循与 Windows 命令类似的 [原则](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c)。</span><span class="sxs-lookup"><span data-stu-id="a1961-227">The commands that you can use in the console follow similar principles as [Windows Commands](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="a1961-228">高级命令提供了一组更可靠的操作，允许你执行更强大的操作，如下载和上载文件、在设备上运行脚本，以及对实体执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="a1961-228">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="a1961-229">从设备获取文件</span><span class="sxs-lookup"><span data-stu-id="a1961-229">Get a file from the device</span></span>

<span data-ttu-id="a1961-230">对于希望从正在调查的设备获取文件的情况，可以使用 `getfile` 命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-230">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="a1961-231">这允许你从设备保存文件以进一步调查。</span><span class="sxs-lookup"><span data-stu-id="a1961-231">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="a1961-232">以下文件大小限制适用：</span><span class="sxs-lookup"><span data-stu-id="a1961-232">The following file size limits apply:</span></span>
>- <span data-ttu-id="a1961-233">`getfile` 限制：3 GB</span><span class="sxs-lookup"><span data-stu-id="a1961-233">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="a1961-234">`fileinfo` 限制：10 GB</span><span class="sxs-lookup"><span data-stu-id="a1961-234">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="a1961-235">`library` 限制：250 MB</span><span class="sxs-lookup"><span data-stu-id="a1961-235">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="a1961-236">在后台下载文件</span><span class="sxs-lookup"><span data-stu-id="a1961-236">Download a file in the background</span></span>

<span data-ttu-id="a1961-237">若要使安全运营团队继续调查受影响的设备，现在可以在后台下载文件。</span><span class="sxs-lookup"><span data-stu-id="a1961-237">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="a1961-238">若要在后台下载文件，在实时响应命令控制台中，键入 `download <file_path> &` 。</span><span class="sxs-lookup"><span data-stu-id="a1961-238">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="a1961-239">如果你正在等待下载文件，可以使用 Ctrl + Z 将其移动到后台。</span><span class="sxs-lookup"><span data-stu-id="a1961-239">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="a1961-240">若要将文件下载引入前台，在实时响应命令控制台中，键入 `fg <command_id>` 。</span><span class="sxs-lookup"><span data-stu-id="a1961-240">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="a1961-241">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="a1961-241">Here are some examples:</span></span>


|<span data-ttu-id="a1961-242">命令</span><span class="sxs-lookup"><span data-stu-id="a1961-242">Command</span></span>  |<span data-ttu-id="a1961-243">功能</span><span class="sxs-lookup"><span data-stu-id="a1961-243">What it does</span></span>  |
|---------|---------|
|`Download "C:\windows\some_file.exe" &`     |<span data-ttu-id="a1961-244">开始在后台下载名为 *some_file.exe* 的文件。</span><span class="sxs-lookup"><span data-stu-id="a1961-244">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="a1961-245">将命令 ID 为 *1234* 的下载返回到前台。</span><span class="sxs-lookup"><span data-stu-id="a1961-245">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="a1961-246">将文件放入库中</span><span class="sxs-lookup"><span data-stu-id="a1961-246">Put a file in the library</span></span>

<span data-ttu-id="a1961-247">实时响应具有一个库，您可以将文件放入其中。</span><span class="sxs-lookup"><span data-stu-id="a1961-247">Live response has a library where you can put files into.</span></span> <span data-ttu-id="a1961-248">库存储可在 (级实时响应) 运行的文件，如脚本和脚本。</span><span class="sxs-lookup"><span data-stu-id="a1961-248">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="a1961-249">实时响应允许运行 PowerShell 脚本，但是必须先将文件放入库中，然后才能运行它们。</span><span class="sxs-lookup"><span data-stu-id="a1961-249">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="a1961-250">你可以拥有可以在启动实时响应会话的设备上运行的 PowerShell 脚本集合。</span><span class="sxs-lookup"><span data-stu-id="a1961-250">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="a1961-251">上载库中的文件</span><span class="sxs-lookup"><span data-stu-id="a1961-251">To upload a file in the library</span></span>

1. <span data-ttu-id="a1961-252">单击 **"将文件上载到库"。**</span><span class="sxs-lookup"><span data-stu-id="a1961-252">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="a1961-253">单击 **"** 浏览"，然后选择文件。</span><span class="sxs-lookup"><span data-stu-id="a1961-253">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="a1961-254">提供简要说明。</span><span class="sxs-lookup"><span data-stu-id="a1961-254">Provide a brief description.</span></span>

4. <span data-ttu-id="a1961-255">指定您是否要覆盖同名的文件。</span><span class="sxs-lookup"><span data-stu-id="a1961-255">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="a1961-256">如果需要，请了解脚本需要哪些参数，请选中"脚本参数"复选框。</span><span class="sxs-lookup"><span data-stu-id="a1961-256">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="a1961-257">在文本字段中，输入示例和说明。</span><span class="sxs-lookup"><span data-stu-id="a1961-257">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="a1961-258">单击"**确认"。**</span><span class="sxs-lookup"><span data-stu-id="a1961-258">Click **Confirm**.</span></span> 

7. <span data-ttu-id="a1961-259"> (可选) 若要验证文件已上载到库，请运行 `library` 命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-259">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="a1961-260">取消命令</span><span class="sxs-lookup"><span data-stu-id="a1961-260">Cancel a command</span></span>
<span data-ttu-id="a1961-261">在会话期间，您可以随时按 Ctrl + C 取消命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-261">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="a1961-262">使用此快捷方式不会在代理端停止命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-262">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="a1961-263">它将仅取消门户中的命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-263">It will only cancel the command in the portal.</span></span> <span data-ttu-id="a1961-264">因此，更改操作（如"修正"）可能会继续，同时取消命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-264">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

### <a name="automatically-run-prerequisite-commands"></a><span data-ttu-id="a1961-265">自动运行必备组件命令</span><span class="sxs-lookup"><span data-stu-id="a1961-265">Automatically run prerequisite commands</span></span>

<span data-ttu-id="a1961-266">某些命令具有要运行的先决条件命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-266">Some commands have prerequisite commands to run.</span></span> <span data-ttu-id="a1961-267">如果不运行必备组件命令，将会看到错误消息。</span><span class="sxs-lookup"><span data-stu-id="a1961-267">If you don't run the prerequisite command, you'll get an error.</span></span> <span data-ttu-id="a1961-268">例如，运行命令 `download` 而不运行 `fileinfo` 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="a1961-268">For example, running the `download` command without `fileinfo` will return an error.</span></span>

<span data-ttu-id="a1961-269">可以使用自动标志自动运行先决条件命令，例如：</span><span class="sxs-lookup"><span data-stu-id="a1961-269">You can use the auto flag to automatically run prerequisite commands, for example:</span></span>

```console
getfile c:\Users\user\Desktop\work.txt -auto
```

## <a name="run-a-powershell-script"></a><span data-ttu-id="a1961-270">运行 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="a1961-270">Run a PowerShell script</span></span> 

<span data-ttu-id="a1961-271">必须先将其上载到库中，然后才能运行 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="a1961-271">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="a1961-272">将脚本上载到库后，使用 `run` 命令运行脚本。</span><span class="sxs-lookup"><span data-stu-id="a1961-272">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="a1961-273">如果计划在会话中使用未签名的脚本，则需要在"高级功能设置" [页中启用该](advanced-features.md) 设置。</span><span class="sxs-lookup"><span data-stu-id="a1961-273">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="a1961-274">允许使用未签名脚本可能会增加你面临的威胁。</span><span class="sxs-lookup"><span data-stu-id="a1961-274">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="a1961-275">应用命令参数</span><span class="sxs-lookup"><span data-stu-id="a1961-275">Apply command parameters</span></span>

- <span data-ttu-id="a1961-276">查看控制台帮助以了解命令参数。</span><span class="sxs-lookup"><span data-stu-id="a1961-276">View the console help to learn about command parameters.</span></span> <span data-ttu-id="a1961-277">若要了解单个命令，请运行：</span><span class="sxs-lookup"><span data-stu-id="a1961-277">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="a1961-278">将参数应用于命令时，请注意，参数基于固定顺序进行处理：</span><span class="sxs-lookup"><span data-stu-id="a1961-278">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="a1961-279">指定固定顺序之外的参数时，在提供值之前，使用连字符指定参数的名称：</span><span class="sxs-lookup"><span data-stu-id="a1961-279">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="a1961-280">使用具有必备命令的命令时，可以使用标志：</span><span class="sxs-lookup"><span data-stu-id="a1961-280">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="a1961-281">`<command name> -type file -id <file path> - auto` 或 `remediate file <file path> - auto`）。</span><span class="sxs-lookup"><span data-stu-id="a1961-281">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="a1961-282">支持的输出类型</span><span class="sxs-lookup"><span data-stu-id="a1961-282">Supported output types</span></span>

<span data-ttu-id="a1961-283">实时响应支持表和 JSON 格式输出类型。</span><span class="sxs-lookup"><span data-stu-id="a1961-283">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="a1961-284">对于每个命令，都有一个默认输出行为。</span><span class="sxs-lookup"><span data-stu-id="a1961-284">For each command, there's a default output behavior.</span></span> <span data-ttu-id="a1961-285">可以使用以下命令修改首选输出格式的输出：</span><span class="sxs-lookup"><span data-stu-id="a1961-285">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="a1961-286">由于空间有限，表格式中显示的字段较少。</span><span class="sxs-lookup"><span data-stu-id="a1961-286">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="a1961-287">若要在输出中查看更多详细信息，可以使用 JSON 输出命令显示更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="a1961-287">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="a1961-288">支持的输出管道</span><span class="sxs-lookup"><span data-stu-id="a1961-288">Supported output pipes</span></span>

<span data-ttu-id="a1961-289">实时响应支持通过管道将输出传输至 CLI 和文件。</span><span class="sxs-lookup"><span data-stu-id="a1961-289">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="a1961-290">CLI 是默认输出行为。</span><span class="sxs-lookup"><span data-stu-id="a1961-290">CLI is the default output behavior.</span></span> <span data-ttu-id="a1961-291">可以使用以下命令将输出通过管道传输至文件：[command] > [filename].txt。</span><span class="sxs-lookup"><span data-stu-id="a1961-291">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="a1961-292">示例：</span><span class="sxs-lookup"><span data-stu-id="a1961-292">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="a1961-293">查看命令日志</span><span class="sxs-lookup"><span data-stu-id="a1961-293">View the command log</span></span>

<span data-ttu-id="a1961-294">选择 **"命令日志** "选项卡以查看会话期间在设备上使用的命令。</span><span class="sxs-lookup"><span data-stu-id="a1961-294">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="a1961-295">每个命令都使用完整详细信息进行跟踪，例如：</span><span class="sxs-lookup"><span data-stu-id="a1961-295">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="a1961-296">ID</span><span class="sxs-lookup"><span data-stu-id="a1961-296">ID</span></span>
- <span data-ttu-id="a1961-297">命令行</span><span class="sxs-lookup"><span data-stu-id="a1961-297">Command line</span></span>
- <span data-ttu-id="a1961-298">持续时间</span><span class="sxs-lookup"><span data-stu-id="a1961-298">Duration</span></span>
- <span data-ttu-id="a1961-299">状态和输入或输出侧栏</span><span class="sxs-lookup"><span data-stu-id="a1961-299">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="a1961-300">限制</span><span class="sxs-lookup"><span data-stu-id="a1961-300">Limitations</span></span>

- <span data-ttu-id="a1961-301">实时响应会话一次限制为 10 个实时响应会话。</span><span class="sxs-lookup"><span data-stu-id="a1961-301">Live response sessions are limited to 10 live response sessions at a time.</span></span>
- <span data-ttu-id="a1961-302">不支持大规模命令执行。</span><span class="sxs-lookup"><span data-stu-id="a1961-302">Large-scale command execution is not supported.</span></span>
- <span data-ttu-id="a1961-303">实时响应会话非活动超时值为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="a1961-303">Live response session inactive timeout value is 5 minutes.</span></span> 
- <span data-ttu-id="a1961-304">用户一次只能启动一个会话。</span><span class="sxs-lookup"><span data-stu-id="a1961-304">A user can only initiate one session at a time.</span></span>
- <span data-ttu-id="a1961-305">设备一次只能在一个会话中。</span><span class="sxs-lookup"><span data-stu-id="a1961-305">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="a1961-306">以下文件大小限制适用：</span><span class="sxs-lookup"><span data-stu-id="a1961-306">The following file size limits apply:</span></span>
   - <span data-ttu-id="a1961-307">`getfile` 限制：3 GB</span><span class="sxs-lookup"><span data-stu-id="a1961-307">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="a1961-308">`fileinfo` 限制：10 GB</span><span class="sxs-lookup"><span data-stu-id="a1961-308">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="a1961-309">`library` 限制：250 MB</span><span class="sxs-lookup"><span data-stu-id="a1961-309">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="a1961-310">相关文章</span><span class="sxs-lookup"><span data-stu-id="a1961-310">Related article</span></span>
- [<span data-ttu-id="a1961-311">实时响应命令示例</span><span class="sxs-lookup"><span data-stu-id="a1961-311">Live response command examples</span></span>](live-response-command-examples.md)
