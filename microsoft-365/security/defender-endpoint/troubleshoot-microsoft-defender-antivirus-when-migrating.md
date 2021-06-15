---
title: 从第三方解决方案迁移时解决 Microsoft Defender 防病毒软件问题
description: 解决迁移到迁移过程时出现Microsoft Defender 防病毒
keywords: 事件， 错误代码， 日志记录， 疑难解答， microsoft defender 防病毒， windows defender 防病毒， 迁移
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3eb4d01957383efc8df47e9fee6eb6394c80015a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924379"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a><span data-ttu-id="bf4de-104">从第三方解决方案迁移时解决 Microsoft Defender 防病毒软件问题</span><span class="sxs-lookup"><span data-stu-id="bf4de-104">Troubleshoot Microsoft Defender Antivirus while migrating from a third-party solution</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bf4de-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bf4de-105">**Applies to:**</span></span>

- [<span data-ttu-id="bf4de-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bf4de-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="bf4de-107">如果在从第三方安全解决方案迁移到第三方安全解决方案时遇到问题，可以在此处Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="bf4de-107">You can find help here if you encounter issues while migrating from a third-party security solution to Microsoft Defender Antivirus.</span></span>

## <a name="review-event-logs"></a><span data-ttu-id="bf4de-108">查看事件日志</span><span class="sxs-lookup"><span data-stu-id="bf4de-108">Review event logs</span></span>

<span data-ttu-id="bf4de-109">通过选择任务栏中的"搜索"图标并搜索事件查看器，打开 *事件查看器应用*。</span><span class="sxs-lookup"><span data-stu-id="bf4de-109">Open the Event viewer app by selecting the **Search** icon in the taskbar, and searching for *event viewer*.</span></span>

<span data-ttu-id="bf4de-110">有关应用程序Microsoft Defender 防病毒信息，请参阅Microsoft Windows Windows Defender 应用程序和服务  >    >    >  **日志**。</span><span class="sxs-lookup"><span data-stu-id="bf4de-110">Information about Microsoft Defender Antivirus can be found under  **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender**.</span></span> 

<span data-ttu-id="bf4de-111">从"操作"**下方选择**"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="bf4de-111">From there, select **Open** underneath **Operational**.</span></span>

<span data-ttu-id="bf4de-112">从详细信息窗格中选择事件将在下窗格中的"常规"和"详细信息"选项卡下显示有关 **事件的详细信息**。 </span><span class="sxs-lookup"><span data-stu-id="bf4de-112">Selecting an event from the details pane will show you more information about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

## <a name="microsoft-defender-antivirus-wont-start"></a><span data-ttu-id="bf4de-113">Microsoft Defender 防病毒无法启动</span><span class="sxs-lookup"><span data-stu-id="bf4de-113">Microsoft Defender Antivirus won't start</span></span>

<span data-ttu-id="bf4de-114">此问题可能以多个不同的事件 ID 的形式显示，所有这些事件都有相同的基本原因。</span><span class="sxs-lookup"><span data-stu-id="bf4de-114">This issue can manifest in the form of  several different event IDs, all of which have the same underlying cause.</span></span>

### <a name="associated-event-ids"></a><span data-ttu-id="bf4de-115">关联的事件 ID</span><span class="sxs-lookup"><span data-stu-id="bf4de-115">Associated event IDs</span></span>

 <span data-ttu-id="bf4de-116">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bf4de-116">Event ID</span></span> | <span data-ttu-id="bf4de-117">日志名称</span><span class="sxs-lookup"><span data-stu-id="bf4de-117">Log name</span></span> | <span data-ttu-id="bf4de-118">说明</span><span class="sxs-lookup"><span data-stu-id="bf4de-118">Description</span></span> | <span data-ttu-id="bf4de-119">源</span><span class="sxs-lookup"><span data-stu-id="bf4de-119">Source</span></span>
-|-|-|-
<span data-ttu-id="bf4de-120">15</span><span class="sxs-lookup"><span data-stu-id="bf4de-120">15</span></span> | <span data-ttu-id="bf4de-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="bf4de-121">Application</span></span> | <span data-ttu-id="bf4de-122">更新Windows Defender状态以SECURITY_PRODUCT_STATE_OFF。</span><span class="sxs-lookup"><span data-stu-id="bf4de-122">Updated Windows Defender status successfully to SECURITY_PRODUCT_STATE_OFF.</span></span> | <span data-ttu-id="bf4de-123">安全中心</span><span class="sxs-lookup"><span data-stu-id="bf4de-123">Security Center</span></span>
<span data-ttu-id="bf4de-124">5007</span><span class="sxs-lookup"><span data-stu-id="bf4de-124">5007</span></span> | <span data-ttu-id="bf4de-125">Microsoft-Windows-Windows Defender/Operational</span><span class="sxs-lookup"><span data-stu-id="bf4de-125">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="bf4de-126">Windows Defender 防病毒配置已更改。</span><span class="sxs-lookup"><span data-stu-id="bf4de-126">Windows Defender Antivirus Configuration has changed.</span></span>  <span data-ttu-id="bf4de-127">如果这是意外事件，你应该查看设置，因为这可能是恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="bf4de-127">If this is an unexpected event you should review the settings as this may be the result of malware.</span></span><br /><br /><span data-ttu-id="bf4de-128">**旧值：** Default\IsServiceRunning = 0x0</span><span class="sxs-lookup"><span data-stu-id="bf4de-128">**Old value:** Default\IsServiceRunning = 0x0</span></span><br /><span data-ttu-id="bf4de-129">**新值：** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span><span class="sxs-lookup"><span data-stu-id="bf4de-129">**New value:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span></span> | <span data-ttu-id="bf4de-130">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="bf4de-130">Windows Defender</span></span>
<span data-ttu-id="bf4de-131">5010</span><span class="sxs-lookup"><span data-stu-id="bf4de-131">5010</span></span> | <span data-ttu-id="bf4de-132">Microsoft-Windows-Windows Defender/Operational</span><span class="sxs-lookup"><span data-stu-id="bf4de-132">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="bf4de-133">Windows Defender 防病毒间谍软件和其他可能不需要的软件扫描处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="bf4de-133">Windows Defender Antivirus scanning for spyware and other potentially unwanted software is disabled.</span></span> | <span data-ttu-id="bf4de-134">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="bf4de-134">Windows Defender</span></span>

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a><span data-ttu-id="bf4de-135">如何判断Microsoft Defender 防病毒安装第三方防病毒后无法启动</span><span class="sxs-lookup"><span data-stu-id="bf4de-135">How to tell if Microsoft Defender Antivirus won't start because a third-party antivirus is installed</span></span>

<span data-ttu-id="bf4de-136">在Windows 10设备上，如果未使用 Microsoft Defender for Endpoint，并且安装了第三方防病毒，Microsoft Defender 防病毒将自动关闭。</span><span class="sxs-lookup"><span data-stu-id="bf4de-136">On a Windows 10 device, if you are not using Microsoft Defender for Endpoint, and you have a third-party antivirus installed, then Microsoft Defender Antivirus will be automatically turned off.</span></span> <span data-ttu-id="bf4de-137">如果你使用的是安装了第三方防病毒的 Microsoft Defender for Endpoint，Microsoft Defender 防病毒被动模式启动，功能会减少。</span><span class="sxs-lookup"><span data-stu-id="bf4de-137">If you are using Microsoft Defender for Endpoint with a third-party antivirus installed, Microsoft Defender Antivirus will start in passive mode, with reduced functionality.</span></span>

> [!TIP]
> <span data-ttu-id="bf4de-138">上述方案仅适用于Windows 10。</span><span class="sxs-lookup"><span data-stu-id="bf4de-138">The scenario just described applies only to Windows 10.</span></span> <span data-ttu-id="bf4de-139">其他版本的 Windows对第三[Microsoft Defender 防病毒](microsoft-defender-antivirus-compatibility.md)安全软件一起运行的其他版本有不同的响应。</span><span class="sxs-lookup"><span data-stu-id="bf4de-139">Other versions of Windows have [different responses](microsoft-defender-antivirus-compatibility.md) to Microsoft Defender Antivirus being run alongside third-party security software.</span></span>

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a><span data-ttu-id="bf4de-140">使用"服务"应用检查Microsoft Defender 防病毒是否已关闭</span><span class="sxs-lookup"><span data-stu-id="bf4de-140">Use Services app to check if Microsoft Defender Antivirus is turned off</span></span>

<span data-ttu-id="bf4de-141">若要打开"服务"应用，请从 **任务栏中选择"** 搜索"图标，然后搜索 *服务*。</span><span class="sxs-lookup"><span data-stu-id="bf4de-141">To open the Services app, select the **Search** icon from the taskbar and search for *services*.</span></span> <span data-ttu-id="bf4de-142">您还可以通过键入 *services.msc* 从命令行打开应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf4de-142">You can also open the app from the command-line by typing *services.msc*.</span></span>

<span data-ttu-id="bf4de-143">有关Microsoft Defender 防病毒的信息将在服务应用下"操作 **"Windows Defender**  >  **列出**。</span><span class="sxs-lookup"><span data-stu-id="bf4de-143">Information about Microsoft Defender Antivirus will be listed within the Services app under **Windows Defender** > **Operational**.</span></span> <span data-ttu-id="bf4de-144">防病毒服务名称是Windows Defender 防病毒 *服务*。</span><span class="sxs-lookup"><span data-stu-id="bf4de-144">The antivirus service name is *Windows Defender Antivirus Service*.</span></span>

<span data-ttu-id="bf4de-145">在检查应用时，你可能会看到 *Windows Defender 防病毒 Service* 设置为手动 ，但在尝试手动启动此服务时，你收到一条警告，指出"本地计算机上 Windows Defender 防病毒 *服务服务已启动，然后已停止"。如果某些服务未由其他服务或程序* 使用，则会自动停止这些服务。</span><span class="sxs-lookup"><span data-stu-id="bf4de-145">While checking the app, you may see that *Windows Defender Antivirus Service* is set to manual — but when you try to start this service manually, you get a warning stating, *The Windows Defender Antivirus Service service on Local Computer started and then stopped. Some services stop automatically if they are not in use by other services or programs.*</span></span>

<span data-ttu-id="bf4de-146">这表示Microsoft Defender 防病毒已自动关闭，以保留和第三方防病毒的兼容性。</span><span class="sxs-lookup"><span data-stu-id="bf4de-146">This indicates that Microsoft Defender Antivirus has been automatically turned off to preserve compatibility with a third-party antivirus.</span></span>

#### <a name="generate-a-detailed-report"></a><span data-ttu-id="bf4de-147">生成详细报告</span><span class="sxs-lookup"><span data-stu-id="bf4de-147">Generate a detailed report</span></span>

<span data-ttu-id="bf4de-148">可以通过在以管理员模式运行中打开命令提示符，然后输入以下命令来生成有关当前活动组策略的详细报告：</span><span class="sxs-lookup"><span data-stu-id="bf4de-148">You can generate a detailed report about currently active group policies by opening a command prompt in **Run as admin** mode, then entering the following command:</span></span>

```powershell
GPresult.exe /h gpresult.html
```

<span data-ttu-id="bf4de-149">这将生成位于 *./gpresult.html 的报告*。</span><span class="sxs-lookup"><span data-stu-id="bf4de-149">This will generate a report located at *./gpresult.html*.</span></span> <span data-ttu-id="bf4de-150">打开此文件，你可能会看到以下结果，具体取决于Microsoft Defender 防病毒关闭方式。</span><span class="sxs-lookup"><span data-stu-id="bf4de-150">Open this file and you might see the following results, depending on how Microsoft Defender Antivirus was turned off.</span></span>

##### <a name="group-policy-results"></a><span data-ttu-id="bf4de-151">组策略结果</span><span class="sxs-lookup"><span data-stu-id="bf4de-151">Group policy results</span></span>

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a><span data-ttu-id="bf4de-152">如果安全设置是通过组策略 (GPO) 在域或本地级别实现，或者通过 System center configuration manager (SCCM) </span><span class="sxs-lookup"><span data-stu-id="bf4de-152">If security settings are implemented via group policy (GPO) at the domain or local level, or though System center configuration manager (SCCM)</span></span>

<span data-ttu-id="bf4de-153">在 GPResults 报告中，在标题 Windows *Components/Windows Defender 防病毒* 下，你可能会看到如下条目，指示Microsoft Defender 防病毒关闭。</span><span class="sxs-lookup"><span data-stu-id="bf4de-153">Within the GPResults report, under the heading, *Windows Components/Windows Defender Antivirus*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="bf4de-154">策略</span><span class="sxs-lookup"><span data-stu-id="bf4de-154">Policy</span></span> | <span data-ttu-id="bf4de-155">设置</span><span class="sxs-lookup"><span data-stu-id="bf4de-155">Setting</span></span> | <span data-ttu-id="bf4de-156">获胜的 GPO</span><span class="sxs-lookup"><span data-stu-id="bf4de-156">Winning GPO</span></span>
-|-|-
<span data-ttu-id="bf4de-157">关闭Windows Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="bf4de-157">Turn off Windows Defender Antivirus</span></span> | <span data-ttu-id="bf4de-158">已启用</span><span class="sxs-lookup"><span data-stu-id="bf4de-158">Enabled</span></span> | <span data-ttu-id="bf4de-159">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="bf4de-159">Win10-Workstations</span></span>

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a><span data-ttu-id="bf4de-160">如果安全设置通过组策略首选项 (GPP) </span><span class="sxs-lookup"><span data-stu-id="bf4de-160">If security settings are implemented via Group policy preference (GPP)</span></span>

<span data-ttu-id="bf4de-161">在标题"注册表项 (项路径 *：HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender，值名称：DisableAntiSpyware) "* 下，你可能会看到如下条目，指示 Microsoft Defender 防病毒 已关闭。</span><span class="sxs-lookup"><span data-stu-id="bf4de-161">Under the heading, *Registry item (Key path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Value name: DisableAntiSpyware)*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="bf4de-162">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="bf4de-162">DisableAntiSpyware</span></span> | -
-|-
<span data-ttu-id="bf4de-163">获胜的 GPO</span><span class="sxs-lookup"><span data-stu-id="bf4de-163">Winning GPO</span></span> | <span data-ttu-id="bf4de-164">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="bf4de-164">Win10-Workstations</span></span>
<span data-ttu-id="bf4de-165">结果：成功</span><span class="sxs-lookup"><span data-stu-id="bf4de-165">Result: Success</span></span> | 
<span data-ttu-id="bf4de-166">**常规**</span><span class="sxs-lookup"><span data-stu-id="bf4de-166">**General**</span></span> | 
<span data-ttu-id="bf4de-167">操作</span><span class="sxs-lookup"><span data-stu-id="bf4de-167">Action</span></span> | <span data-ttu-id="bf4de-168">更新</span><span class="sxs-lookup"><span data-stu-id="bf4de-168">Update</span></span>
<span data-ttu-id="bf4de-169">**属性**</span><span class="sxs-lookup"><span data-stu-id="bf4de-169">**Properties**</span></span> | 
<span data-ttu-id="bf4de-170">配置单元</span><span class="sxs-lookup"><span data-stu-id="bf4de-170">Hive</span></span> | <span data-ttu-id="bf4de-171">HKEY_LOCAL_MACHINE</span><span class="sxs-lookup"><span data-stu-id="bf4de-171">HKEY_LOCAL_MACHINE</span></span>
<span data-ttu-id="bf4de-172">密钥路径</span><span class="sxs-lookup"><span data-stu-id="bf4de-172">Key path</span></span> | <span data-ttu-id="bf4de-173">SOFTWARE\Policies\Microsoft\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="bf4de-173">SOFTWARE\Policies\Microsoft\Windows Defender</span></span>
<span data-ttu-id="bf4de-174">值名称</span><span class="sxs-lookup"><span data-stu-id="bf4de-174">Value name</span></span> | <span data-ttu-id="bf4de-175">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="bf4de-175">DisableAntiSpyware</span></span>
<span data-ttu-id="bf4de-176">值类型</span><span class="sxs-lookup"><span data-stu-id="bf4de-176">Value type</span></span> | <span data-ttu-id="bf4de-177">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="bf4de-177">REG_DWORD</span></span>
<span data-ttu-id="bf4de-178">值数据</span><span class="sxs-lookup"><span data-stu-id="bf4de-178">Value data</span></span> | <span data-ttu-id="bf4de-179">0x1 (1) </span><span class="sxs-lookup"><span data-stu-id="bf4de-179">0x1 (1)</span></span>

###### <a name="if-security-settings-are-implemented-via-registry-key"></a><span data-ttu-id="bf4de-180">如果安全设置是通过注册表项实现的</span><span class="sxs-lookup"><span data-stu-id="bf4de-180">If security settings are implemented via registry key</span></span>

<span data-ttu-id="bf4de-181">报告可能包含以下文本，指示Microsoft Defender 防病毒关闭状态：</span><span class="sxs-lookup"><span data-stu-id="bf4de-181">The report may contain the following text, indicating that Microsoft Defender Antivirus is turned off:</span></span>
 
> <span data-ttu-id="bf4de-182">注册表 (regedit.exe) </span><span class="sxs-lookup"><span data-stu-id="bf4de-182">Registry (regedit.exe)</span></span>
>
> <span data-ttu-id="bf4de-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (十六) 1 (dword) </span><span class="sxs-lookup"><span data-stu-id="bf4de-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span></span>

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a><span data-ttu-id="bf4de-184">如果在服务器映像或 Windows中Windows安全设置</span><span class="sxs-lookup"><span data-stu-id="bf4de-184">If security settings are set in Windows or your Windows Server image</span></span>

<span data-ttu-id="bf4de-185">你虚构的管理员可能已经通过 *GPEdit.exe* *、LGPO.exe* 在本地或通过修改任务序列中的注册表来设置安全策略 **[DisableAntiSpyware。](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**</span><span class="sxs-lookup"><span data-stu-id="bf4de-185">Your imagining admin might have set the security policy, **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, locally via *GPEdit.exe*, *LGPO.exe*, or by modifying the registry in their task sequence.</span></span> <span data-ttu-id="bf4de-186">您可以为[受信任映像标识符配置](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender)Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="bf4de-186">You can [configure a Trusted Image Identifier](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) for Microsoft Defender Antivirus.</span></span>

### <a name="turn-microsoft-defender-antivirus-back-on"></a><span data-ttu-id="bf4de-187">打开Microsoft Defender 防病毒"</span><span class="sxs-lookup"><span data-stu-id="bf4de-187">Turn Microsoft Defender Antivirus back on</span></span>

<span data-ttu-id="bf4de-188">Microsoft Defender 防病毒当前没有处于活动状态的防病毒，将自动打开该防病毒。</span><span class="sxs-lookup"><span data-stu-id="bf4de-188">Microsoft Defender Antivirus will automatically turn on if no other antivirus is currently active.</span></span> <span data-ttu-id="bf4de-189">你需要完全关闭第三方防病毒，以确保Microsoft Defender 防病毒完整功能运行。</span><span class="sxs-lookup"><span data-stu-id="bf4de-189">You'll need to turn the third-party antivirus completely off to ensure Microsoft Defender Antivirus can run with full functionality.</span></span>

> [!WARNING]
> <span data-ttu-id="bf4de-190">建议编辑 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services 中的wdboot、wdfilter、wdnisdrv、wdnissvc 和 *windefend* 的 Windows Defender 开始值的解决方案不受支持，并可能强制你重新映像系统。   </span><span class="sxs-lookup"><span data-stu-id="bf4de-190">Solutions suggesting that you edit the *Windows Defender* start values for *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc*, and *windefend* in  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services are unsupported, and may force you to re-image your system.</span></span>

<span data-ttu-id="bf4de-191">如果你开始将 Microsoft Defender for Endpoint 和第三方防病毒与应用一起使用，则被动Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="bf4de-191">Passive mode is available if you start using Microsoft Defender for Endpoint and a third-party antivirus together with Microsoft Defender Antivirus.</span></span> <span data-ttu-id="bf4de-192">被动模式允许 Microsoft Defender 扫描文件并自行更新，但它不会修正威胁。</span><span class="sxs-lookup"><span data-stu-id="bf4de-192">Passive mode allows Microsoft Defender to scan files and update itself, but it will not remediate threats.</span></span> <span data-ttu-id="bf4de-193">此外，通过实时保护的行为[](configure-real-time-protection-microsoft-defender-antivirus.md)监视在被动模式下不可用，除非部署了 DLP ([终结点](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)) 数据丢失防护。</span><span class="sxs-lookup"><span data-stu-id="bf4de-193">In addition, behavior monitoring via [Real Time Protection](configure-real-time-protection-microsoft-defender-antivirus.md) is not available under passive mode, unless [Endpoint data loss prevention (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) is deployed.</span></span>

<span data-ttu-id="bf4de-194">另一个称为[有限定期](limited-periodic-scanning-microsoft-defender-antivirus.md)扫描的功能在设置为自动关闭Microsoft Defender 防病毒最终用户可用。</span><span class="sxs-lookup"><span data-stu-id="bf4de-194">Another feature, known as [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md), is available to end-users when Microsoft Defender Antivirus is set to automatically turn off.</span></span> <span data-ttu-id="bf4de-195">此功能允许Microsoft Defender 防病毒检测次数有限的第三方防病毒一起定期扫描文件。</span><span class="sxs-lookup"><span data-stu-id="bf4de-195">This feature allows Microsoft Defender Antivirus to scan files periodically alongside a third-party antivirus, using a limited number of detections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf4de-196">不建议在企业环境中进行有限定期扫描。</span><span class="sxs-lookup"><span data-stu-id="bf4de-196">Limited periodic scanning is not recommended in enterprise environments.</span></span> <span data-ttu-id="bf4de-197">与活动模式相比，在此模式下Microsoft Defender 防病毒运行时提供的检测、管理和报告功能会减少。</span><span class="sxs-lookup"><span data-stu-id="bf4de-197">The detection, management and reporting capabilities available when running Microsoft Defender Antivirus in this mode are reduced as compared to active mode.</span></span>

### <a name="see-also"></a><span data-ttu-id="bf4de-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf4de-198">See also</span></span>

* [<span data-ttu-id="bf4de-199">Microsoft Defender 防病毒兼容性</span><span class="sxs-lookup"><span data-stu-id="bf4de-199">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
* [<span data-ttu-id="bf4de-200">Microsoft Defender 防病毒应用中Windows 安全中心</span><span class="sxs-lookup"><span data-stu-id="bf4de-200">Microsoft Defender Antivirus in the Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)